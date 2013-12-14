$ROLE for Ansible
=================

A role for deploying and configuring [$ROLE](http://$role.com) and extensions on unix hosts using [Ansible](http://www.ansibleworks.com/).

It can additionally be used as a playbook for quickly provisioning hosts.

Vagrant machines are provided to produce a boxed install of $ROLE or a VM for integration testing.


Supports
--------

Supported $ROLE versions:

- $ROLE 1.0
- ...

Supported targets:

- Ubuntu 12.04 "Precise Pangolin"
- ...

Installation methods:

- Binary packages from the official repositories at [$application](http://$application.com/repo/)
- Official sources from [$application](https://$application.com/sources/)

Available extensions (under a switch):

- Extension - `$role_extension`
- ...


Usage
-----

Clone this repo into your roles directory:

    $ git clone https://github.com/user/ansible-$role.git roles/$role

And add it to your play's roles:

    - hosts: ...
      roles:
        - $role
        - ...

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `$role_`.

You can also use the role as a playbook. You will be asked which hosts to provision, and you can further configure the play by using `--extra-vars`.

    $ ansible-playbook -i inventory --extra-vars='{...}' main.yml

To provision a standalone $ROLE box, start the `boxed` VM, which is a Ubuntu 12.04 box:

    $ vagrant up boxed

You will find $ROLE listening on the VM's `$port` port on address `192.168.33.20` in the private network. You can then connect to it as any user. Please note that this is highly insecure, so if you're going to publish this VM you'll want to provide actual authentication.

Run the tests by provisioning the appropriate VM:

    $ vagrant up test-ubuntu-precise

At the moment, `ubuntu-precise` is the only test VM available.


Still to do
-----------

- Write the role itself, for one


Changelog
---------

### 0.1

Initial version.
