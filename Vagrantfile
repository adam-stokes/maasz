Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.synced_folder "salt/roots", "/srv"
  config.ssh.timeout = 300
  config.ssh.max_tries = 300
  config.vm.provider :lxc do |lxc|
    lxc.customize 'cgroup.memory.limit_in_bytes', '1024M'
    lxc.customize 'cgroup.devices.allow', 'b 7:* rwm'
    lxc.customize 'cgroup.devices.allow', 'c 10:237 rwm'
  end
  config.vm.provision :salt do |salt|
    salt.minion_config = "salt/minion"
    salt.run_highstate = true
  end
  config.vm.hostname = "vagrant-maas-lxc-salt"
end
