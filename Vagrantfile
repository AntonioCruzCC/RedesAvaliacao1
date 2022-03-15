# -*- mode: ruby -*-
# vi: set ft=ruby :

$scriptNginx = <<EOF
sudo apt update
sudo apt install nginx -y 
sudo cp /tmp/index.html /var/www/html/
EOF

$scriptApache = <<EOF
sudo apt update
sudo apt install apache2 -y
sudo cp /tmp/index.html /var/www/html
EOF

Vagrant.configure("2") do |config|
  config.vm.define "nginx" do |nginx|
    nginx.vm.box = "ubuntu/bionic64"
    nginx.vm.network "private_network", ip: "10.10.10.11"
    nginx.vm.provision "file", source: "./index.html", destination: "/tmp/index.html"
    nginx.vm.provision "shell", inline: $scriptNginx
  end
  config.vm.define "apache" do |apache|
    apache.vm.box = "ubuntu/bionic64"
    apache.vm.network "private_network", ip: "10.10.10.12"
    apache.vm.provision "file", source: "./index.html", destination: "/tmp/index.html"
    apache.vm.provision "shell", inline: $scriptApache
  end
end
