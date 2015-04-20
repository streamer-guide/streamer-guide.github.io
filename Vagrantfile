# -*- mode: ruby -*-
# vi: set ft=ruby :

# Provisioning script
$script = <<SCRIPT
sudo apt-get update
sudo apt-get -y install ruby2.0 ruby2.0-dev make gcc nodejs git zlib1g-dev build-essential libyaml-dev libxml2-dev
sudo gem2.0 install github-pages --no-rdoc --no-ri
SCRIPT

Vagrant.configure(2) do |config|

	config.vm.box = "ubuntu/trusty64"
	config.vm.provision "shell", inline: $script

	config.vm.define :streamerguide do |dev|
		dev.vm.network :private_network, ip: "172.22.2.2"
		dev.vm.hostname = "streamerguide"
	end
end
