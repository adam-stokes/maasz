Vagrant.configure("2") do |config|
  config.vm.box = "trusty64"
  config.vm.hostname = "maas"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network :private_network, ip: "88.88.88.88"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "ansible_hosts"
    ansible.host_key_checking = false
    ansible.verbose = false
  end
end
