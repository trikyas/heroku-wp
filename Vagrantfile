# -*- mode: ruby -*-
# vi: set ft=ruby :

VM_IP  = "192.168.50.100"

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.synced_folder ".", "/app"

  # Manage our hostfile for us
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true

  # Keep it simple; just 1 VM for db and web
  config.vm.define "herokuwp" do |herokuwp|
    herokuwp.vm.hostname = "herokuwp.local"
    herokuwp.vm.provision :shell, :path => "support/vagrant/install.sh"
    herokuwp.vm.network :private_network, ip: VM_IP
  end

end
