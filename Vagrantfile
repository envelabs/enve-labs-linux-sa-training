# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"
  config.vm.hostname = "enve-labs-linux-sa-vm"
  config.vm.network :public_network, bridge: ''
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 3306, host: 3306 

  config.vm.synced_folder "./shared", "/home/vagrant/shared"

  config.vm.provider :virtualbox do |vb|
    vb.name = "enve-labs-linux-sa-vm"
  end

  config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update && sudo apt-get install -y apt-transport-https ca-certificates software-properties-common curl jq
  SHELL

end
