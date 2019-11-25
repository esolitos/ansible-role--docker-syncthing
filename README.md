Ansible Role: Docker Syncthing
=========

Setup and run a docker container for [syncthing](https://syncthing.net/).

Requirements
------------

Only requirement is to have `docker` installed on the system, you can use an existing role. I can reccomend [`geerlingguy.docker`](https://github.com/geerlingguy/ansible-role-docker).

Role Variables
--------------

`syncthing_username`

Specifies the username under which the contaienr will write data (a new user will be created if necessary)

`syncthing_group`

Specifies the user group under which the contaienr will write data

`syncthing_data_dirname`

Directory name in which the docker container will write its data (under user's $HOME)


`syncthing_firewall`

Specifies if the role should update iptables to whitelist syncthing ports

`syncthing_firewall_gui_whitelist_ip`

Must be a list of strings, each IP will be whitelisted to access the Web GUI, use `0.0.0.0` to allow everything.


Dependencies
------------

None.

Soft dependendcy: `geerlingguy.docker` (see **Requirements** section)/

Example Playbook
----------------

    - hosts: all
      roles:
         - geerlingguy.docker
         - esolitos.syncthing

License
-------

MIT

Author Information
------------------

This role was created in 2019 by [Marlon (esolitos) Saglia](https://esolitos.com/) for personal use, Issues and Pull-Requests are welcome.
