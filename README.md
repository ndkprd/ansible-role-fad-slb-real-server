# ansible-role-fortiadc-slb-real-server

## Description

Ansible role to create/update Fortinet's FortiADC SLB Real Server entries using REST API.

The configuration is kinda opiniated for my needs, which is to make the configuration setups is as simple as possible. In the case of this role, since I'm mainly using direct IPv4 address for the real servers, I'm using those IP address as the name too for simpler management.

Still, those are still *kinda* optional. Since I'm just setting them as a "default" value, you can still overwrite them with your own value by following the "complete" example.

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

See [tests folder](tests/).

### About Tags

Each task is tagged with their task file name, `fad_slb_real_server`.

There's also a some kind of pre-task and post-task that run before and after create/update tasks to compare the value of before and after create/update tasks, tagged with the above tag and an additional `debug` tag.

## Limitation

Only developed and tested against FortiADC 7.0.

## License

MIT, use at your own risk.
