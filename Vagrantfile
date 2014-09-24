# -*- mode: ruby -*-
# vi: set ft=ruby :

hosts = {
  "host0" => "192.168.33.10",
  "host1" => "192.168.33.11"
}

Vagrant.configure("2") do |config|
  
  config.vbguest.auto_update = false

  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/trusty32"
      #machine.vm.box_url = "http://files.vagrantup.com/trusty64.box"
      machine.vm.hostname = "%s.example.org" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 200]
      end
    end
  end
end