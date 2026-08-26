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
