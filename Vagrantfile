# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/wily64"
  # If you want to use this box with the Kafka Connect Twitter input, please use the following base box instead
  #config.vm.box = "ubuntu/vivid64"

  # Configure forwarded ports
  config.vm.network "forwarded_port", guest: 2181, host: 2181 # Zookeeper
  config.vm.network "forwarded_port", guest: 9092, host: 9092 # Kafka
  config.vm.network "forwarded_port", guest: 8081, host: 8081 # Schema registry
  config.vm.network "forwarded_port", guest: 9021, host: 9021 # Confluent Control Center

  # Configure VM Ram usage
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.cpus = "2"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "ansible/playbook.yml"
  end
end
