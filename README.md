# OpenLDAP Lab

## Usage

- Run `docker-compose up -d`
- Run `. seed.sh`

## Information

This bare bones docker-compose setup will create an ephemeral OpenLDAP lab environment with the following:

- Access port: `2389`
- Everything under `dc=example, dc=com`
- Users in `ou=users`
- Groups in `ou=groups`
- Users are
  - `cn=user1,ou=users,dc=example,dc=com`
  - `cn=user2,ou=users,dc=example,dc=com`
  - `cn=adminuser1,ou=users,dc=example,dc=com`
  - `cn=adminuser2,ou=users,dc=example,dc=com`
- Passwords match usernames.  eg.
  - `user1` password is `user1`
- Groups:
  - `cn=usergroup,ou=groups,dc=example,dc=com`
    - `user1`
    - `user2`
  - `cn=admingroup,ou=groups,dc=example,dc=com`
    - `adminuser1`
    - `adminuser2`
- Groups are `groupOfNames`
  - If you require groups setup as groupOfUniqueNames, delete the container and run with `. seed-unique.sh`