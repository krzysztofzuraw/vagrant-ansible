# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.ssh.insert_key = false
  # uncomment if you have problems with virtualbox
  # config.vm.provider "virtualbox" do |vb|
  #  vb.gui = true
  # end

  config.vm.hostname = "vagrant-ansible"
  config.vm.network "private_network", ip: "192.168.33.10"


  config.vm.provision "ansible" do |ansible|
   ansible.playbook = "playbooks/vagrant.yaml"
   ansible.inventory_path = "inventory/vagrant/hosts.ini"
   ansible.sudo = true
   ansible.verbose = "v"
   ansible.limit = "all"
 end

end
