# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box_check_update = false
  #config.vm.box = "centos/7"
  #config.vm.network "forwarded_port", guest:80, host: 8080, auto_correct: true

  # configure Time
  #config.vm.provider 'virtualbox' do |vb|
  # vb.customize [ "guestproperty", "set", :id, "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold", 1000 ]
  #end
    
  $num_instances = 1

    (1..$num_instances).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.box = "centos/7"
    end
  end
  # Uncomment this if you want to link to a shared folder (e.g. if you are running source control and want to link it to Vagrant)
  # config.vm.synced_folder "./", "/var/www", create: true, group: "www-data", owner: "www-data"

  config.vm.provision "shell", path: "provision/setup.sh"

end
