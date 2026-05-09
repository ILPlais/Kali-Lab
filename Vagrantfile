# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	# Official rolling Kali Linux image from Vagrant Cloud.
	config.vm.box = "kalilinux/rolling"
	# Hostname inside the guest (visible in prompts and tooling).
	config.vm.hostname = "kali-lab"

	# Provision the VM with Ansible (runs playbook on first boot and on `vagrant provision`).
	config.vm.provision "ansible" do |ansible|
		ansible.limit = "all"
		ansible.playbook = "provision-kali.yaml"
	end

	# VirtualBox-specific settings (other providers would use their own blocks).
	config.vm.provider "virtualbox" do |vb|
		vb.name = "kali-lab"
		vb.gui = true

		vb.memory = 4096
		vb.cpus = 4
	end
end
