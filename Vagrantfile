# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  #Define VM ubuntu-22.04 and install Docker by scripting sheel
  config.vm.define "docker-server" do |docker|

    docker.vm.box = "bento/ubuntu-22.04"
    docker.vm.network "private_network", ip: "192.168.33.10"
    docker.vm.synced_folder "./docker-data", "/vagrant_data"
    docker.vm.hostname = "docker-server"

    #provider using virtualbox
    docker.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
      vb.gui = false
      vb.name = "docker-server"
    end

    #provision by sheel to install docker
    docker.vm.provision "shell", path: "install-docker.sh"
  end

  #Define VM ubuntu-22.04 and install Ngnix by scripting sheel
  config.vm.define "ngnix-server" do |ngnix|

    ngnix.vm.box = "bento/ubuntu-22.04"
    ngnix.vm.network "private_network", ip: "192.168.33.11"
    ngnix.vm.network "forwarded_port", guest: 80, host: 82
    ngnix.vm.synced_folder "./ngnix-data", "/vagrant_data"

    #provider using virtualbox
    ngnix.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
      vb.gui = false
      vb.name = "ngnix-server"
    end

    #provision by sheel to install ngnix
    ngnix.vm.provision "shell", path: "install-ngnix.sh"
  end
end
