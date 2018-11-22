# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  (1..3).each do |i|
    config.vm.define "node-#{i}" do |node|
      node.vm.box = "centos/7"
    end
    config.vm.provider :libvirt do |libvirt|
      libvirt.graphics_type = "none"
      libvirt.memory = 2048
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
    ansible.compatibility_mode = '2.0'
    ansible.limit = 'all'
  end

end
