# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.gui = false
  end

  config.vm.box = "hashicorp/bionic64"
  config.vm.network "public_network", ip: "192.168.0.100"
  config.vm.network "forwarded_port", guest: 8080, host: 8080, auto_correct: true

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "ansible-playbook.yml"
    ansible.inventory_path = "inventory"
  end

end
