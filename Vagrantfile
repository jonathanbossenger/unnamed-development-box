# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "bento/ubuntu-16.04"

    config.vm.hostname = "localbox"

    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "private_network", ip: "192.168.33.10"

    config.vm.synced_folder ".", "/var/www/public", :mount_options => ["dmode=777", "fmode=666"]

    config.vm.provider "virtualbox" do |vb|
         vb.memory = "2048"
         vb.name = "localbox"
    end

    config.ssh.insert_key = false

    config.vm.provision "shell", path: "install.sh", privileged: false

end