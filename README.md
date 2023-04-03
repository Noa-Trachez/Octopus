# { Epitech } Octopus

This document specifies the different variables that must be present in `group_vars/all.yml`.

To launch this playbook, you do not need to take any additional steps, as everything (from the inventory file to the roles) is configured by these variables.

---

## General variables
- `ssh_user` - The username with which you want to establish ssh connections

- `redis_host`, `postgresql_host`, `poll_host`, `result_host`, `worker_host` - The different IP addresses for the corresponding hosts (**redis**_host -> IP address of your **redis** host, etc...). Please specify each one of these variables.

## Redis config
- `redis_bind` - List of IP addresses on which redis has to listen, separated by spaces (example: 127.0.0.1 56.34.12.3)
- `redis_database` - Number of redis databases.

Redis will always listen on its default port (6379), so make sure your redis host does not already use this port.

## PostgreSQL config
- `postgresql_user_name` - Username of a non-privilged user
- `postgresql_user_password` - Password for this user
- `postgresql_db_name` - Name of the database to create
- `postgresql_db_port`- Port on which the database has to listen

## Result config
- `result_port` - The port on which the result client must listen

Once you've correctly created each one of these variables, you should be able to launch the ansible playbook by running `ansible-playbook -i my-inventory playbook.yml`.

---

## Note
If you've created the `group_vars/all.yml` file with ansible vault, consider adding the `--ask-vault-pass` argument to the previous command, or put your password in some file, and set the `ANSIBLE_VAULT_PASSWORD_FILE` to be the absolute path to this file.
