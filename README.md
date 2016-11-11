# puppet-blueprint

Available Resources in Puppet: https://docs.puppet.com/puppet/4.8/reference/type.html

## Reverse Engineering

### Packages
```bash
aptitude search '~i !~M' -F %p | tr -d ' \t\r\f' > packages.list
cat packages.list | xargs -d '\n' -n1 puppet resource package > packages.pp
```
### Users
```bash
grep "/bin/bash" /etc/passwd | cut -d: -f1 > users.list
cat users.list | xargs -d '\n' -n1 puppet resource user > user.pp
```
