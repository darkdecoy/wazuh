# To-Do List

* Keep Agents from upgrading
  * echo "wazuh-agent hold" | dpkg --set-selections
* Update the adding of repos

```yaml
- name: Install - Add wazuh repository into sources list
  ansible.builtin.deb822_repository:
    name: wazuh
    state: present
    types: [deb]
    uris: "https://packages.wazuh.com/4.x/apt/"
    suites: ["{{ ansible_facts['distribution_release'] | lower }}"]
    components:
      - main
      - stable
    signed_by: "{{ wazuh_agent_config.repo.gpg }}"
    enabled: true
    trusted: true
  become: true
  tags: always
```

* wazuh repo keys fail to get added to keyring

```bash
TASK [darkdecoy.wazuh.agent : Debian/Ubuntu | Import Wazuh GPG key] ************************************************************************************************************************************************
[ERROR]: Task failed: Module failed: Error executing command: [Errno 2] No such file or directory: b'gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import /tmp/WAZUH-GPG-KEY'
Origin: /home/darkdecoy/.ansible/collections/ansible_collections/darkdecoy/wazuh/roles/agent/tasks/Debian.yml:52:3

50     - not wazuh_custom_packages_installation_agent_enabled
51
52 - name: Debian/Ubuntu | Import Wazuh GPG key
     ^ column 3

fatal: [pcvh01]: FAILED! => {"changed": false, "cmd": "'gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import /tmp/WAZUH-GPG-KEY'", "msg": "Error executing command.", "rc": 2, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}
fatal: [pop01]: FAILED! => {"changed": false, "cmd": "'gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import /tmp/WAZUH-GPG-KEY'", "msg": "Error executing command.", "rc": 2, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}
```
