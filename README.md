# ansible-prometheus.io
```diff
# Project maturity (- Dev|@ Staging|+ Prod):
- Dev
```
**NOTE**: This is a fun project that serves little purpose for the general public. There is far less involved ways of
getting started with prometheus than manual scraping of their website.

This is an [Ansible](https://www.ansible.com/)-role which installs and configures `prometheus`. [Links to additonal documentation](https://prometheus.io/docs/prometheus/latest/installation/).


## Requirements
### 1. Linux
This role is tested and expected to perform on the following Linux-distributions:
- None

The role *might* work on the following distributions with no guarantees:
- None

### 2. Ansible
You need Ansible for a control-node. Either as a seperate computer/VM or on the intended target. You need the Ansible module-collection `community general` (which often is pre-installed with your Ansible-distribution). This is the basis of any Ansible-control node, additionally to operate this role you need  the `community docker` module.
I maintain a [script at Github](https://raw.githubusercontent.com/harahauk/ansible-help/refs/heads/main/install_ansible.sh) which can automate this in a way that do not interfere with system stability. The script installs the two module-packs as well.

On most systems these commands will lead to a working control node and is maintainable without the use of the script:
```
dnf install ansible-core
ansible-galaxy collection install community.general
```
**Note**: Replace `dnf` with your package manager like `apt` for Ubuntu/Debian-based OS.


## Role Variables
| Variable        | Mandatory | Description |
| --------------- | --------- | ----------- |
| | | |


## Ansible-dependencies
Roles needed to support this role, needs be executed prior to the execution of this role.

- None


## Example Playbook
    - hosts: prometheus_servers    # Define a group or a hostname as a target
      roles:
      - this_folder                # Change to the folder you checked this role out as
      vars:
        docker_user: "my_unprivileged_user"


## License

[MIT](./LICENSE)


Author Information
------------------

[Harald Hauknes](https://github.com/harahauk)
