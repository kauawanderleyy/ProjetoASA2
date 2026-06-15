# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end
  config.vm.box = "debian/bookworm64"
  config.vm.hostname = "kaua.pedro"
  config.ssh.insert_key = false
  config.vm.network "public_network", bridge: "eno2"
  config.vm.network "private_network", ip: "192.168.56.120"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.gui = false
    vb.name = config.vm.hostname
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook_ansible.yml"
    ansible.verbose = "v"
  end
end
