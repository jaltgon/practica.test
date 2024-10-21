# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "master" do |master|
    master.vm.box = "debian/bullseye64"
    master.vm.network "private_network", ip: "192.168.57.103"
    master.vm.hostname = "tierra.sistema.test"
    master.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    master.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9 bind9utils bind9-doc
      # Add your DNS configuration here
    SHELL
  end

  config.vm.define "slave" do |slave|
    slave.vm.box = "debian/bullseye64"
    slave.vm.network "private_network", ip: "192.168.57.102"
    slave.vm.hostname = "venus.sistema.test"
    slave.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    slave.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9 bind9utils bind9-doc
      # Add your DNS configuration here
    SHELL
  end
end
