# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
  # config.vm.network "private_network", ip: "192.168.68.8"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.cpus = 4
    vb.memory = "2048"
    # vb.name = "tdd-with-python"
  end

  #config.vm.synced_folder "/local/path", "/vm/path"
  config.vm.hostname = "superlists"
  # config.vm.define "tdd-wih-python"

  ####### Provision #######
  config.ssh.forward_agent = true
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/provision.yml"
    ansible.verbose = true
    # ansible.inventory_path = "ansible/hosts.ini"
    ansible.extra_vars = {
    host: "localhost",
    # ansible_ssh_user: "root"
    }
  end
end
