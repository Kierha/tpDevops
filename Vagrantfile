# -*- mode: ruby -*-
# vi: set ft=ruby :

# Configuration de la machine virtuelle
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  
  # Configuration de la première VM Serveur web
  config.vm.define "web" do |web|
    web.vm.hostname = "web"
    web.vm.network "private_network", ip: "192.168.56.3"
    web.vm.provider "virtualbox" do |vb|
      vb.name = "Serveur web"
    end
    web.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/playbook.yml"
      ansible.inventory_path = "ansible/hosts"
    end
  end
  
  # Configuration de la deuxième VM Serveur Database
  config.vm.define "db" do |database|
    database.vm.hostname = "db"
    database.vm.network "private_network", ip: "192.168.56.4"
    database.vm.provider "virtualbox" do |vb|
      vb.name = "Serveur Database"
    end
    database.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/playbook.yml"
      ansible.inventory_path = "ansible/hosts"
    end
  end
end
