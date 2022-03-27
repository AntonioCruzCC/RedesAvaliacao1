# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.define "nginx" do |nginx|
    nginx.vm.box = "ubuntu/bionic64"
    nginx.vm.network "private_network", ip: "192.168.1.100"
    nginx.vm.provision "ansible", playbook: "provisioning/nginx.yml"
  end
  config.vm.define "apache" do |apache|
    apache.vm.box = "ubuntu/bionic64"
    apache.vm.network "private_network", ip: "192.168.1.101"
    apache.vm.provision "ansible", playbook: "provisioning/apache.yml"
  end
end
