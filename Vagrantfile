Vagrant.configure("2") do |config|
  config.vm.box = "maas"
  config.vm.hostname = "maas"
  config.vm.provider :lxc do |lxc|
    lxc.customize 'network.ipv4', '10.0.3.100'
    lxc.customize 'cgroup.memory.limit_in_bytes', '1024M'
    lxc.customize 'cgroup.devices.allow', 'b 7:* rwm'
    lxc.customize 'cgroup.devices.allow', 'c 10:237 rwm'
    lxc.customize "aa_profile", "lxc-container-default-with-loops"
  end
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = false
  end
end
