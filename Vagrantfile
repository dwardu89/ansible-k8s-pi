# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"


  config.ssh.insert_key = false

  config.vm.synced_folder ".", "/vagrant", disabled: true


  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false
    vb.cpus = 2
    # Customize the amount of memory on the VM:
    vb.memory = "2048"

    # Use a linked Clone
    vb.linked_clone = true
    vb.customize ['modifyvm', :id, '--audio', 'none']

  end

  
  # Master
  config.vm.define "master" do |v|
    v.vm.hostname = "master"
    v.vm.network :private_network, ip: "192.168.60.4"
  end
  # Node 1
  config.vm.define "node1" do |v|
    v.vm.hostname = "node1"
    v.vm.network :private_network, ip: "192.168.60.5"
  end
  # Node 2
  config.vm.define "node2" do |v|
    v.vm.hostname = "node2"
    v.vm.network :private_network, ip: "192.168.60.6"
  end
  # Node 3
  config.vm.define "node3" do |v|
    v.vm.hostname = "node3"
    v.vm.network :private_network, ip: "192.168.60.7"
  end
  # Node 4
  config.vm.define "node4" do |v|
    v.vm.hostname = "node4"
    v.vm.network :private_network, ip: "192.168.60.8"
  end
end
