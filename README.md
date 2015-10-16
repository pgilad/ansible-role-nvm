# ansible-role-nvm

> An Ansible role to install and setup nvm

[![Build Status](http://img.shields.io/travis/pgilad/ansible-role-nvm.svg?style=flat)](https://travis-ci.org/pgilad/ansible-role-nvm)

## Requirements

None

## Role Variables

- `nvm_version` - `nvm` git version tag. Can be any valid git ref tag. Defaults to `master`.
- `nvm_repository` - `nvm` git repository. Defaults to `https://github.com/creationix/nvm.git`
- `nvm_install_path` - path to install nvm. Defaults to `/home/{{ ansible_ssh_user }}/.nvm`.
- `nvm_set_aliases` - array of aliases for nvm to set. Defaults to `{ source: default, target: stable }`
- `nvm_install_versions` - array of versions to install with `nvm`. Defaults to `["stable"]`

## Dependencies

None

## Example Playbook

```yml
- hosts: servers
    roles:
      - pgilad.ansible-role-nvm
```

## License

MIT ©[Gilad Peleg](http://giladpeleg.com)
