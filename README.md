# Arch Linux installation

A set of Ansible playbooks to help set up a basic workstation.

## Installation

First create an inventory file containing something like this:

```ini
[arch]
1.2.3.4 ansible_python_interpreter=/usr/bin/python2
```

Note the `ansible_python_interpreter` config which needs to point to the
Python2 interpreter for certain Ansible tasks to work.

Once the inventory file is set up, use `ansible-playbook` to configure a new
system.

```sh
ansible-playbook --inventory-file=arch --ask-pass setup.yml
```

All tasks are idempotent, it should be safe to run the above command against an
existing system.

## Securing the system

After installation, the root password shoul be changed and the password for the
`attila` user should be set. Additionally, password authentication should be
disabled over SSH.
