Example of Cisco image upgrade with Ansible
============================================

This repo contains examples of playbooks and roles that upgrade an image on a switch using the [ios_command  module][1] and [ansible-network.network_engine][3].

One of the use cases for Ansible and the [networking modules][2] is to grab information in real time from the network. These tasks will do just that, including verify available disk space as well as which files the device currently has on flash.

![Cisco 4500-X][6]


Copy Role
--------------

![copy_flow][8]


Install Role
--------------

![install_flow][9]


4500_roles.yml
------------

```
---
- name: UPGRADE 4500X FIRMWARE
  hosts: all
  connection: network_cli
  gather_facts: no
  roles:
    - ansible-network.network-engine
    - 4500_copy_image
    - 4500_install_image

```
---------------


[1]:https://docs.ansible.com/ansible/latest/modules/ios_command_module.html#ios-command-module
[2]: http://docs.ansible.com/ansible/latest/list_of_network_modules.html
[3]: https://github.com/ansible-network/network-engine
[4]: http://docs.ansible.com/ansible/latest/ios_facts_module.html
[5]: http://docs.ansible.com/ansible/latest/template_module.html
[6]: readme_pics/4500-X.jpg
[7]: https://github.com/ansible/ansible-lint
[8]: readme_pics/copy_flow_chart.jpg
[9]: readme_pics/install_flow_chart.jpg
