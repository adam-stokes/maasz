Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.provider :lxc do |lxc|
    lxc.customize 'cgroup.memory.limit_in_bytes', '1024M'
    lxc.customize 'cgroup.devices.allow', 'b 7:* rwm'
    lxc.customize 'cgroup.devices.allow', 'c 10:237 rwm'
  end
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = false
  end
  config.vm.hostname = "vagrant-maas-lxc-salt"
end
