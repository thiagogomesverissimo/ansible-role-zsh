ansible-role-zsh
================
[![Build Status](https://travis-ci.org/vaulttec/ansible-role-zsh.svg?branch=master)](https://travis-ci.org/vaulttec/ansible-role-zsh)

Ansible role to install [zsh](https://www.zsh.com/3) and [Oh My ZSH](http://ohmyz.sh).


Requirements
------------

None.


Role Variables
--------------

Available variables are listed below, along with default values:

```yaml
zsh_user:
  - "{{ ansible_ssh_user }}"

zsh_debug_startup_time: false

zsh_ohmy_theme: pygmalion

zsh_ohmy_custom_plugins:
  - name: zsh-syntax-highlighting
    repo: "git://github.com/zsh-users/zsh-syntax-highlighting.git"
  - name: zsh-autosuggestions
    repo: "git://github.com/zsh-users/zsh-autosuggestions.git"

zsh_ohmy_plugins:
  - git
  - git-flow
  - docker
  - zsh-syntax-highlighting
  - zsh-autosuggestions

zsh_ohmy_disable_auto_update: true
```


Dependencies
------------

None.


Example Playbook
----------------

Install zsh and oh-my-zsh with default settings:

```yaml
- hosts: server
  roles:
     - vaulttec.zsh
```

Install zsh and oh-my-zsh with random theme and different plugins:

```yaml
- hosts: desktop
  roles:
     - { role: vaulttec.zsh, zsh_ohmy_theme: random, zsh_ohmy_plugins: [git, git-extras] }
```


Testing
-------

```bash
cd tests && vagrant up
```


License
-------

MIT
