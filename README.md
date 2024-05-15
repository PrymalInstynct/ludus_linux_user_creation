# Ansible Role: Linux User Creation ([Ludus](https://ludus.cloud))

An Ansible Role that will create users on linux hosts in a Ludus Cyber Range

## Requirements

- community.general

## Role Variables

```yaml
ludus_linux_user_creation:
  users:
    - user1
    - user2
    - user3
  admins:
    - admin1
    - admin2
  # the default password is password hashed with `mkpasswd --method=sha-512`
  password: '$6$DtCZ/a.46h/Ld7la$IJe.4Tt5lH0FMCiOil4l2ZwSu8fy0jR2e/lGWIJ7r4liQxtFBWiiRoGJGtMYyZJ2vyC/tPDgOVKcdkP31O1cm.'
ludus_linux_user_creation_initial_host: false
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: hosts
  roles:
    - PrymalInstynct.ludus_linux_user_creation
```

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-debian12-server"
    hostname: "{{ range_id }}-debian12-server"
    template: debian-12-x64-server-template
    vlan: 20
    ip_last_octet: 1
    ram_gb: 8
    cpus: 4
    linux: true
    roles:
      - PrymalInstynct.ludus_linux_user_creation
```

## License

GPLv3

## Author Information

This role was created by [PrymalInstynct](https://github.com/PrymalInstynct), for [Ludus](https://ludus.cloud/).
