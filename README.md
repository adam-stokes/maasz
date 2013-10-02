vagrant-maas
============

Quickly get up and running with [MAAS][2]. Maybe you are a developer wanting to test latest MAAS bits or you are presenting MAAS to a potential client? This should get you to the point where you just import boot images and attach nodes.

In the pipeline:
- Checkout personal bazaar repos and build MAAS from source to see your latest code changes.
- Quickly build MAAS from source and run unittests within a container.
- Add nodes from kvm, virtualbox, and other virtualization images.

# Pre-reqs

* Needs [ansible][1] installed
* Use the default vagrant box show in the install instructions or [build your own lxc enabled vagrant box][3].

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
 [3]: https://github.com/fgrehm/vagrant-lxc/blob/master/BOXES.md
