Install and configure kopia
=========

Install and configure a kopia server for my server

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Example Playbook
----------------

```yaml
    - hosts: servers
      vars:
        kopia_clients:
          - username: tychob
            hostname: desktop-tycho
            password: password123
          - username: tychob
            hostname: nobara-laptop
            password: password123

      roles:
         - { role: kopia, kopia_server_control_password: password123, kopia_repository_password: password123,
             kopia_path: /mnt/backups }
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
