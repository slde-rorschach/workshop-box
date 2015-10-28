# Simple sulu devbox

## requirements

- [Vagrant](http://vagrantup.com/)
- [VirtualBox](http://virtualbox.org/)
- [Ansible](http://www.ansible.com/)
- [Ant](http://ant.apache.org/)
- [sshpass](https://gist.github.com/arunoda/7790979)

## how to use

On your host system:

- add `192.168.19.21 sulu.local` to your `/etc/hosts`

```bash
git clone https://github.com/slde-rorschach/snb.git
mkdir neos # needed for shared folder
cd snb
vagrant up
ant ansible
```

in your box (`vagrant ssh`):

```bash
cd ~/share
```

Then follow the [Sulu installation guide](docs.sulu.io/en/latest/book/getting-started/installation.html)

## MySQL info

MySQL ist not configured, so the username is `root` without a password.
Use `localhost` or `127.0.0.1` as host.

## Want to use git inside the box?

You can edit `ansible/host_vars/neos.local.yml` to your needs.
There a two keys `git_username` and `git_usermail`, where you can place your own values.
Do not forget to run `ant ansible` ;)

## Questions?

Ask me! lukas.sadzik@ext.chefkoch.de
