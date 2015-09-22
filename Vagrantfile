# -*- mode: ruby -*-
# vi: set ft=ruby :
#
# call like:
# MODE='dev' vagrant up
#
VAGRANT_VERSION = 2
Vagrant.configure(VAGRANT_VERSION) do |config|
	config.vm.define "hubot" do |server|
		server.vm.box = "hashicorp/precise64"
		server.vm.hostname = "hubot"
		server.vm.provision :ansible do |ansible|
			if ENV['MODE'] == "dev"
				ansible.playbook = "development.yml"
			else
				ansible.playbook = "test.yml"
			end
			ansible.extra_vars = {
				verbose: 'vvvv'
			}
		end
	end
end
