# -*- mode: ruby; -*-
Vagrant.configure("2") do |config|
  config.vm.box = "trusty64"

  # MaaS Server
  config.vm.define "maas", primary: true do |maas|
    config.vm.hostname = "maas"
    config.vm.network :private_network, ip: "192.168.150.10"
  end

  # nodes
  config.vm.define "node1" do |node1|
    config.vm.hostname = "node1"
  end

  config.vm.define "node2" do |node2|
    config.vm.hostname = "node2"
  end

  config.vm.define "node3" do |node3|
    config.vm.hostname = "node3"
  end

  config.vm.define "node4" do |node4|
    config.vm.hostname = "node4"
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.host_key_checking = false
    ansible.verbose = false
  end
end
