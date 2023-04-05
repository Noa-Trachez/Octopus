# { Epitech } Octopus

This document specifies the different variables that must be present in `group_vars/all.yml`.

To launch the playbook, you do not need to take any additional steps, as everything (from the inventory file to the roles) is configured by these variables.

## !! Important !!

**All your host machines must run under Debian 10 (buster) !!**

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
To create this file, you can either write it as plain text, or encrypt it using ansible vault.

### Using ansible vault:
```bash
ansible-vault create group_vars/all.yml
```

### Content of the file (wether it's encrypted or raw):
```yml
variable1: value

# Some comment
variable2: some_random_val
```

---

If you've created the `group_vars/all.yml` file with ansible vault, consider adding the `--ask-vault-pass` argument to the previous command, or issue the following commands:

```bash
echo <your_password> > /path/to/some/file
export ANSIBLE_VAULT_PASSWORD_FILE=/path/to/some/file
```
