{{ ansible-role-template-name }}
================================
```diff
# Project maturity (- Dev|@ Staging|+ Prod):
- Dev
```
This is an [Ansible](https://www.ansible.com/)-role which installs and configures `something` and `something-more` on the target host. [Links to additonal documentation](htts://www.google.com).

Requirements
------------
## Linux
This role is tested and expected to perform on the following Linux-distributions:
- Debian 12 "Bookworm"
- Red Hat Linux 9
- AlmaLinux 9
- Fedora 38

The role *might* work on the following distributions with no guarantees:
- RHEL-based (RockyLinux, AlmaLinux)
- Debian-based (Kali, Debian, Ubuntu)  

## Ansible
You need ansible [optional install script](https://raw.githubusercontent.com/harahauk/ansible-help/refs/heads/main/install_ansible.sh), and the module 'community general' (which often is pre-installed with your ansible-distribution) and the "community docker" module.
I maintain a [script at Github](./install_ansible.sh) which can automate this.

On most systems these commands will do the same as the installation-script:
```
dnf install ansible-core
ansible-galaxy collection install community.general
ansible-galaxy collection install community.docker     # Only needed if you plan to automate Docker-deployments.
```
**Note**: Replace `dnf` with your package manager like `apt` for Ubuntu/Debian-based OS.


Role Variables
--------------
| Variable        | Mandatory | Description |
| --------------- | --------- | ----------- |
| docker_user     | no        | Defines a user that you want to given access to docker, defaults to the user running the playbook if not set |
| role_name_debug | no        | Display debug-info during role execution |

A description of the modifiable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

- [docker](https://github.com/harahauk/ansible-docker)

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------
    - hosts: docker_hosts    # Define a group or a hostname as a target
      roles:
      - ansible-docker       # Change to the folder you checked this role out as
      vars:
        docker_user: "my_unprivileged_user"


License
-------

[The Unlicense](./LICENSE)


Author Information
------------------

[Harald Hauknes](https://github.com/harahauk)
