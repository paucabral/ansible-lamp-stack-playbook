# Installation and Basic Configuration of LAMP (Linux, Apache, PHP, and MariaDB) stack using Ansible (for Ubuntu and CentOS)

**Author:** Pau Cabral

This is an Ansible playbook that executes the installation and basic configuration of LAMP (Linux, Apache, PHP, and MariaDB) stack written for Ubuntu and CentOS.

## Prerequisites
* Ansible (installed on the control node)
* SSH (installed on both the control node and remote machine/s)
* Sudoer account with passwordless `sudo` (setup on remote machine/s, ensure that the remote user for all machines are the same or modify the inventory file to specify the respective remote user for each)

## Tested On
* Ubuntu 20.04 LTS
* CentOS 8

## Directions
1. Modify the `ansible.cfg` file and replace the value of the `remote_user` variable with your remote username (or replace the file itself with your own configuration file).
2. Edit the `inventory` file and replace the IP addresses under the `lamp` group with the IP address/es of your remote machine/s.
3. Run the playbook using the command: `ansible-playbook playbook.yaml`.

***Note:*** *This playbook disables the firewall of remote machines solely for demonstration purposes. Modify the respective roles to selectively allow service ports instead of turning off the firewall completely if needed.*

## Directory Structure
```
.
├── README.md
├── ansible.cfg
├── config.yaml
├── files
│   └── index.html
├── inventory
├── playbook.yaml
└── roles
    ├── apache_php_ubuntu
    │   ├── README.md
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   │   └── config.j2
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
    ├── httpd_php_centos
    │   ├── README.md
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   │   └── config.j2
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
    ├── mariadb_centos
    │   ├── README.md
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
    └── mariadb_ubuntu
        ├── README.md
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── tasks
        │   └── main.yml
        ├── templates
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml

38 directories, 40 files
```
