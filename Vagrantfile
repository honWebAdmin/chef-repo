# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "opscode-ubuntu-14.10"
  config.vm.box_url = "https://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.10_chef-provisionerless.box"
  config.omnibus.chef_version = :latest
  config.vm.provision :shell, :inline => "ulimit -n 4048"
  config.berkshelf.enabled = true

  config.vm.provision :chef_client do |chef|
    chef.provisioning_path = "/etc/chef"
    chef.chef_server_url = "https://api.chef.io/organizations/crystalint" 
    chef.validation_key_path = ".chef/crystalint-validator.pem"
    chef.validation_client_name = "crystalint-validator"
    chef.node_name = "server"
  end

end
