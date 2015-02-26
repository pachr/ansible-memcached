# ansible-memcached

The playbook install memcached with a custom /etc/memcached.conf

## Vars

- hosts : hosts groupname
 * No default, it must be specifiy in cmd

- remote_user : the remote user on AWS
 *  Type : string
 *  Default : ubuntu

- listen : the listening ip address
 *  Type : string
 *  Default : 127.0.0.1

- user : the user who launch the memcached deamon
 *  Type : string
 *  Default : root

- memory : the maximum memory used (Mb)
 *  Type : integer
 *  Default : 64

- max_connections : the maximum simultaneous connections
 *  Type : integer
 *  Default : 1024

## group_vars

Variables which can be configure (group_vars/all) => for the when condition (default : true)

## Usage

###With default vars :
```
ansible-playbook -i hosts  memcached.yml --extra-vars "hosts=launched remote_user=ubuntu" --private-key=~/.ssh/pac-vm-keypair.pem 

```

###With extra_vars :
```
ansible-playbook -i hosts  memcached.yml --extra-vars "hosts=launched remote_user=ubuntu listen=127.0.0.1 user=root memory=66 max_connections=1026" --private-key=/path/to/keypair

```



