# Simple drupal devbox

## requirements

- [Vagrant](http://vagrantup.com/)
- [VirtualBox](http://virtualbox.org/)
- [Ansible](http://www.ansible.com/)
- [sshpass](https://gist.github.com/arunoda/7790979)

## how to use

On your host system:

- add `192.167.4.21 workshop.box` to your `/etc/hosts`

```bash
# in the cloned repo directory
mkdir share # needed for shared folder
vagrant up
ansible-playbook -i ansible/hosts ansible/site.yml
```

The directory `share` in this repository is shaared to `home/vagrant/share` in the box.

## MySQL info

MySQL ist not configured, so the username is `root` without a password.
Use `localhost` or `127.0.0.1` as host.

## Want to use git inside the box?

You can edit `ansible/group_vars/all.yml` to your needs.
There a two keys `git_username` and `git_usermail`, where you can place your own values.
Do not forget to run ansible ;)
