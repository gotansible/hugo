# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANT_VERSION = 2
Vagrant.configure(VAGRANT_VERSION) do |config|
	config.vm.define "hubot" do |server|
		server.vm.box = "hashicorp/precise64"
		server.vm.hostname = "hubot"
		server.vm.provision :ansible do |ansible|
			ansible.playbook = "development.yml"
			ansible.extra_vars = {
				verbose: 'vvvv'
			}
		end
	end
end
