Ansible Skeleton
================

A Skeleton for Ansible role development.

Making sure all roles have a consistent template that eases development.

Conventions
-----------

An explanation of conventions used in roles can be found in the [docs](./docs).

* [Coding Conventions](./docs/CONVENTIONS_ROLE.md)

Requirements
------------

* [virtualenv](https://virtualenv.pypa.io/en/stable)


Installation
------------

Install from [GitHub](https://github.com/kirikae/ansible-skeleton)
```bash
git clone https://github.com/kirikae/ansible-skeleton.git
```

Usage
-----

### Install Ansible

The recommended and portable way to install [Ansible](https://docs.ansible.com/)
is via [virtualenv](https://virtualenv.pypa.io/en/stable/).

```bash
# Create a new virtualenv
virtualenv $env_name
# Activate virtualenv
source $env_name/bin/activate
# Install Ansible
pip install ansible
```

### Configure Ansible

[Ansible](https://docs.ansible.com/) configuration can be done in multiple
files, depending on your needs by configuring your `ansible.cfg` file.

You have to add the following lines to your `ansible.cfg`:

```ini
[galaxy]
role_skeleton = <path to git repo for ansible-skeleton>/role
skeleton_ignore = ^.git$,^.*/.git_keep$
```

### Install Molecule

[Molecule](https://molecule.readthedocs.io/en/stable/) must be installed in the
same [virtualenv](https://virtualenv.pypa.io/en/stable/) (see above).

```bash
# Activate virtualenv
source $env_name/bin/activate
# Install molecule and docker support
pip install molecule
```

### Create Ansible Role

To ensure you are developing and testing your role for Ansible Galaxy, some manual steps are required for a fresh role:

```bash
# Create Directory from skeleton
ansible-galaxy init $role_name
mv $role_name <github username>.$role_name
```

### Add Tests to the role

Testing is an important part of creating a new role, and good practice for updating existing ones. Details on this can be found in [Ansible Tests](./docs/TESTING_ROLE.md)

License
-------

MIT

Author
------

* Kirikae <kirikae@cs-network.org>
