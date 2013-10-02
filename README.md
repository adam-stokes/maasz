vagrant-maas
============

Quickly get up and running with [MAAS][2]

# Pre-reqs

Needs [ansible][1] installed

# Install

```
% git clone git://github.com:battlemidget/vagrant-maas.git
% cd vagrant-maas
% vagrant plugin install vagrant-lxc
% vagrant box add precise64 http://bit.ly/vagrant-lxc-precise64-2013-09-28
% vagrant up --provider=lxc --provision-with ansible
```

# Provisioning

The previous installer step should've run ansible after image was loaded. If not just run the below command

```
% vagrant provision
```

# Accessing

Whatever your IP is assigned to the vagrant image `vagrant ssh && ip addr show eth0 scope global` "inet" is the ip you'll use to access the MAAS web ui

`http://vagrant.ip/MAAS`

Default login and password: `admin` `pass`

 [1]: http://ansibleworks.com/docs/gettingstarted.html#ubuntu-and-debian
 [2]: http://maas.ubuntu.com
