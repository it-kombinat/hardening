# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  #config.ssh.username = 'root'
  #config.ssh.password = 'vagrant'
  #config.ssh.insert_key = 'true'
  config.vm.box = "centos/7"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 22, host: 8022
  #config.vm.network "public_network", ip: "192.168.0.17"
  config.vm.network "public_network", bridge: "wlp3s0"
  #config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "/root/.ssh/authorized_keys"
  #config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "Playbook.yml"
  end
end
