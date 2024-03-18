`jengsala.minio_server`
=========

Repository ini digunakan untuk menginstall `minio` server untuk Linux

Support platform

- Debian
- Ubuntu
- CentOS


Ansible - User Guide
------------

- Option 1 :

```sh
mkpasswd --method=sha-512
```

```sh
---
# vars/main.yml
minio_password: $6$qyRtExjisttJM1yo$umeOJKzFvL1AdCLIvhJzbaBJFiddrA0I47To3jDvdaDeSy
```


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


| Variable name                 | Example value     | Description |
| :---                          | :---              | :---        |
| `minio_access_key`            | `-`               | Set user credential for minio server |
| `minio_secret_key`            | `-`               | Set password credential for minio server |
| `minio_volume_bind`           | `/var/lib/minio`  | Set data to store ini minio object storage |
| `minio_ports_api`             | `9000`            | Set port to access api s3 |
| `minio_ports_console`         | `9664`            | Set port to access web console |


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
      - { role: jengsala.minio_server }
```
License
-------

MIT

[https://digitastuces.com/](https://digitastuces.com/)
