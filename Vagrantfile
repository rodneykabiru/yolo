# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "geerlingguy/ubuntu2004"

  config.vm.hostname = "Host"
  config.vm.network "private_network", ip: "192.168.56.133"

  config.ssh.insert_key = false

  config.vm.synced_folder "." "/vagrant", disabled: true


  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
  end

# Ansible provisioner
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
    end
end
