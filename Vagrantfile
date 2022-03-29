# -*- mode: ruby -*-
# vi: set ft=ruby :

#CONFIG VAGRANT
Vagrant.configure("2") do |config|
  #DEFINE BOX NGINX
  config.vm.define "nginx" do |nginx|
    #DEFINE BOX OS
    nginx.vm.box = "ubuntu/bionic64"
    #DEFINE BOX IP (PREFERABLY ON 192.168.56.0/21 RANGE)
    nginx.vm.network "private_network", ip: "192.168.56.56"
    #DEFINE PATH TO THE ANSIBLE PLAYBOOK
    nginx.vm.provision "ansible", playbook: "provisioning/nginx.yml"
  end
  #DEFINE BOX APACHE
  config.vm.define "apache" do |apache|
    #DEFINE BOX OS
    apache.vm.box = "ubuntu/bionic64"
    #DEFINE BOX IP (PREFERABLY ON 192.168.56.0/21 RANGE)
    apache.vm.network "private_network", ip: "192.168.56.57"
    #DEFINE PATH TO THE ANSIBLE PLAYBOOK
    apache.vm.provision "ansible", playbook: "provisioning/apache.yml"
  end
end
