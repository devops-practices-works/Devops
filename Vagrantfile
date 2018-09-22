# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
	config.vm.define "jenkinsmaster" do |jenkinsmaster|

		jenkinsmaster.vm.box = "bento/centos-7.2"
		jenkinsmaster.vm.network "private_network", ip: "192.168.33.100"
		 jenkinsmaster.vm.network :forwarded_port, guest: 22, host: 10022, id: "ssh"
		jenkinsmaster.vm.hostname = "jenkinsmaster"
		
		jenkinsmaster.vm.provider :virtualbox do |vb|
		  vb.customize ["modifyvm", :id, "--memory", "4096"]
		  vb.customize ["modifyvm", :id, "--cpus", "2"]
	end
    end

    config.vm.define "jenkinsslave" do |jenkinsslave|

      jenkinsslave.vm.box = "bento/centos-7.2"
      jenkinsslave.vm.network "private_network", ip: "192.168.33.101"
	   jenkinsslave.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"
      jenkinsslave.vm.hostname = "jenkinsslave"
	  
      jenkinsslave.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "4096"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
      end
	end
end