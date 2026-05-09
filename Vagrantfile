# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	# Official rolling Kali Linux image from Vagrant Cloud.
	config.vm.box = "kalilinux/rolling"
	# Hostname inside the guest (visible in prompts and tooling).
	config.vm.hostname = "kali-lab"

	# Provision the VM with Ansible (runs playbook on first boot and on `vagrant provision`).
	config.vm.provision "ansible" do |ansible|
		# Run the playbook on all VMs
		ansible.limit = "all"
		# The playbook to run
		ansible.playbook = "provision-kali.yaml"
	end

	# VirtualBox-specific settings (other providers would use their own blocks).
	config.vm.provider "virtualbox" do |vb|
		# Name of the VM in VirtualBox
		vb.name = "kali-lab"
		# Show the VirtualBox GUI
		vb.gui = true
		# 8GB of memory
		vb.memory = 8192
		# 4 CPU cores
		vb.cpus = 4
	end
end
