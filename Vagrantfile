# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false
    config.vm.synced_folder '.', '/vagrant', type: 'nfs'
  
    # VirtualBox.
    # `vagrant up virtualbox --provider=virtualbox`
    
    config.vm.define "s2" do |virtualbox|
      virtualbox.vm.hostname = "s2"
      virtualbox.vm.box = "consulserver2"
      virtualbox.vm.network :private_network, ip: "192.168.2.11"
  
      config.vm.provider :virtualbox do |v|
        v.gui = false
        v.memory = 512
        v.cpus = 1
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
      end
  
    end
  
    config.vm.define "s3" do |virtualbox|
      virtualbox.vm.hostname = "s3"
      virtualbox.vm.box = "consulserver2"
      virtualbox.vm.network :private_network, ip: "192.168.2.12"
  
      config.vm.provider :virtualbox do |v|
        v.gui = false
        v.memory = 512
        v.cpus = 1
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
      
      end
  
    end
  
    config.vm.define "s1" do |virtualbox|
      virtualbox.vm.hostname = "s1"
      virtualbox.vm.box = "consulserver2"
      virtualbox.vm.network :private_network, ip: "192.168.2.10"
  
      config.vm.provider :virtualbox do |v|
        v.gui = false
        v.memory = 512
        v.cpus = 1
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--ioapic", "on"]   
      end
  
    end
  
    config.vm.define "client" do |virtualbox|
      virtualbox.vm.hostname = "client"
      virtualbox.vm.box = "consulserver2"
      virtualbox.vm.network :private_network, ip: "192.168.2.13"
    config.vm.provider :virtualbox do |v|
        v.gui = false
        v.memory = 512
        v.cpus = 1
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
      end
    end
  end