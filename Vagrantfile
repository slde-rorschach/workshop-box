# -*- mode: ruby -*-
# vi: set ft=ruby :

# settings
box_name            = "ubuntu/trusty64"
box_ip              = "192.167.3.5" 
host_name           = "drupal8.local"

synced_folder_host  = "../drupal8"
synced_folder_guest = "/home/vagrant/share"

box_memory          = "4096"
nfs                 = true
gui                 = false

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = box_name
    config.vm.network "private_network", ip: box_ip
    config.vm.host_name = host_name

    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"

    config.vm.provider :virtualbox do |virtualbox|
        virtualbox.gui = gui
        virtualbox.customize ["modifyvm", :id, "--name", host_name]
        virtualbox.customize ["modifyvm", :id, "--memory", box_memory]
        virtualbox.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        virtualbox.customize ["setextradata", :id, "--VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
    end

    config.vm.synced_folder synced_folder_host, synced_folder_guest, id: "vagrant-share", :nfs => nfs

end
