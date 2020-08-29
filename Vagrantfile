# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.disksize.size = "20GB"
  config.vm.synced_folder "../anki", "/anki/anki"
  config.vm.synced_folder "../add-ons", "/anki/add-ons"
  # config.vm.synced_folder "../pytest-anki", "/anki/pytest-anki"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = 3036
    vb.customize ["modifyvm", :id, "--vram", "16"]
    vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.ask_become_pass = false
    ansible.playbook = "playbook.yml"
    # ansible.verbose = "vvvv"
    ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
  end
end

###################################################################################

  # config.ssh.forward_x11 = true
  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

###################################################################################
