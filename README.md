`dimmaryanto93.minio_server`
=========

Repository ini digunakan untuk menginstall `minio` server untuk Linux

Support platform

- Debian
- Ubuntu
- CentOS


Ansible - User Guide
------------

Persiapan yang harus di lalukan, diantaranya

1. Create new user on your server, Recomend using **very-very Strong Password** or using password generator. 
  ```bash
  adduser <username>
  ```

2. Granted to sudoers with NOPASSWD, using `visudo`
  ```ini
  username    ALL=(ALL) NOPASSWD:ALL
  ```

3. Authenticate with private-key for login ssh, generate ssh key on your local machine then use `ssh-copy-id user@your-ip-server` to copy public key to your server.


Requirements
------------

None

Role Variables
--------------

Ada beberapa variable yang temen-temen bisa gunakan untuk setting docker daemon, diantaranya seperti berikut:

| Variable name                 | Example value     | Description |
| :---                          | :---              | :---        |
| `minio.access_key`            | `-`               | Set user credential for minio server |
| `minio.secret_key`            | `-`               | Set password credential for minio server |
| `minio.volume_bind`           | `/var/lib/minio`  | Set data to store ini minio object storage |
| `minio.ports.api`             | `9000`            | Set port to access api s3 |
| `minio.ports.console`         | `9664`            | Set port to access web console |


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  become: true
  roles:
      - { role: dimmaryanto93.minio_server }
```
License
-------

MIT
