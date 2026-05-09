# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	config.vm.box = "kalilinux/rolling"
	config.vm.hostname = "kali-lab"

	config.vm.provision "ansible" do |ansible|
		ansible.limit = "all"
		ansible.playbook = "provision-kali.yaml"
	end

	config.vm.provider "virtualbox" do |vb|
		vb.name = "kali-lab"
		vb.gui = true

		vb.memory = 4096
		vb.cpus = 4
	end
end
