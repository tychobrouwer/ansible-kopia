Install and configure kopia
=========

Install and configure a kopia server for my server

Role Variables
--------------

The ```kopia_server_control_password``` has to be set to the password used for the server control user.

The ```kopia_repository_password``` has to be set to the password used for the repository.

The ```kopia_path``` has to be set to the path where the Kopia repository will be stored.

The ```kopia_clients``` variable is a list of clients that will be backed up, in the format shown below.

```kopia_port``` can be set to the port used by the Kopia server.

```kopia_control_username``` can be set to the control user for the server

The ```kopia_user_uid``` and ```kopia_user_gid``` can be set to the uid and gid used by Kopia to set the owner of the repository.

Example Playbook
----------------

```yaml
- hosts: servers
  vars:
    kopia_server_control_password: password123
    kopia_repository_password: password123
    kopia_path: /mnt/backups

    kopia_clients:
      - username: tychob
        hostname: desktop-tycho
        password: password123
      - username: tychob
        hostname: nobara-laptop
        password: password123

  roles:
    - role: tychobrouwer.kopia

    - role: tychobrouwer.kopia
      kopia_port: 51515
      kopia_control_username: control
      kopia_user_uid: 0
      kopia_user_gid: 0
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
