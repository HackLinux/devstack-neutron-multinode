VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.define :controller do |controller_config|
        controller_config.vm.box = "trusty64_devstack"
        controller_config.vm.host_name = "controller.example.com"
        controller_config.vm.network :private_network, ip:"192.168.100.10"
        controller_config.vm.network :private_network, ip:"192.168.200.10"
		config.vm.provider :virtualbox do |vb|
		    vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
            vb.customize ["modifyvm", :id, "--memory", "3000"]
            vb.customize ["modifyvm", :id, "--cpus", "2"]
			# vb.gui = true
        end
    end

    config.vm.define :compute1 do |compute1_config|
        compute1_config.vm.box = "trusty64_devstack"
        compute1_config.vm.host_name = "compute1.example.com"
        compute1_config.vm.network :private_network, ip:"192.168.100.30"
        compute1_config.vm.network :private_network, ip:"192.168.200.30"
        config.vm.provider :virtualbox do |vb|
		    vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
            vb.customize ["modifyvm", :id, "--memory", "1500"]
            vb.customize ["modifyvm", :id, "--cpus", "2"]
			# vb.gui = true
        end
    end

    config.vm.define :access do |access_config|
        access_config.vm.box = "trusty64"
        access_config.vm.host_name = "access.example.com"
        access_config.vm.network :private_network, ip:"192.168.100.40"
        access_config.vm.network :private_network, ip:"192.168.200.40"
        config.vm.provider :virtualbox do |vb|
            vb.customize ["modifyvm", :id, "--memory", "256"]
            vb.customize ["modifyvm", :id, "--cpus", "1"]
			# vb.gui = true
        end
    end

end
