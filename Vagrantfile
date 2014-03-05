# -*- mode: ruby; -*-
Vagrant.configure("2") do |config|
  config.vm.box = "trusty64"
  config.vm.hostname = "maas"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end
  # config.vm.provision :ansible do |ansible|
  #   ansible.playbook = "playbook.yml"
  #   ansible.inventory_path = "ansible_hosts"
  #   ansible.host_key_checking = false
  #   ansible.verbose = false
  # end
end
