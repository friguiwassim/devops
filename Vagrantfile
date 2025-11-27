# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Choix de l'image de base (Ubuntu 22.04)
  config.vm.box = "bento/ubuntu-22.04"

  # Configuration réseau
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 80, host: 8081
 #config.ssh.username = 'admin'
 #config.ssh.password = 'c6ceec452a5a49c7a419efd4f33fe699'


  # Configuration matérielle
  config.vm.network "public_network", bridge: "Realtek RTL8723DE 802.11b/g/n PCIe Adapter"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4000"
    vb.cpus = "2"
  end

  # Provisioning (installation automatique de logiciels)
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get install -y gedit
  SHELL

end
