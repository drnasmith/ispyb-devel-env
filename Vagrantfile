# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |v|
  # Give this more resources
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.network "forwarded_port", guest: 3306, host: 3306
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 9990, host: 9990
  config.vm.network "private_network", ip: "192.168.30.11"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbooks/standalone.yml"
  end
end
