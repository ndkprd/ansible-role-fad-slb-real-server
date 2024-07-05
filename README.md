# ansible-role-fortiadc-slb-real-server

## Description

Ansible role to create/update Fortinet's FortiADC SLB Real Server entries using REST API.

## Usage

### Install Role

```
ansible-galaxy install ndkprd.fad_slb_real_server
```

### Hosts Example

```
[fortiadc]
fad-01 ansible_host=fad-01.infra.ndkprd.com ansible_connection=local fad_apitoken=mysupersecrettoken fad_vdom=root
```

### Playbook Example

```
---

- name: Update/create FortiADC resources.
  hosts: all
  become: false
  gather_facts: false
  connection: local
  vars:
    # load-balance real-server entries
    fad_slb_real_server:
      - name: dc0.ndkprd.com
        location: ID
      - name: dc1.ndkprd.com
        location: ID
      - name: dc2.ndkprd.com
        location: ID

  roles:
    - ndkprd.fad_slb_real_server

```

### About Tags

Each task is tagged with their task file name, `fad_slb_real_server`.

There's also a some kind of pre-task and post-task that run before and after create/update tasks to compare the value of before and after create/update tasks, tagged with the above tag and an additional `debug` tag.

## Limitation

Only developed and tested against FortiADC 7.0.

## License

MIT, use at your own risk.
