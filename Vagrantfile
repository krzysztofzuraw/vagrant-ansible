# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false

  config.vm.hostname = "vagrant-ansible"
  config.vm.network :private_network, ip: "192.168.33.27"

  config.vm.provision "ansible" do |ansible|
   ansible.playbook = "playbooks/vagrant.yaml"
   ansible.inventory_path = "inventory/vagrant/hosts.ini"
   ansible.sudo = true
   ansible.verbose = "v"
   ansible.limit = "all"
 end

end
