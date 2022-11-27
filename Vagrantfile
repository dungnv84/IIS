Vagrant.configure("2") do |config|
    (10..13).each do |i|
        if i <= 12
            config.vm.define "fnb-linux-node-#{i}" do |node|
                node.vm.box = "bento/ubuntu-20.04"
                node.vm.hostname = "fnb-linux-node-#{i}"
                # Bridged network
                node.vm.network "private_network", ip:"192.168.58.#{i}"
                # Provider-specific configuration
                node.vm.provider "virtualbox" do |vb|
                    # Customize the amount of memory on the VM
    			 vb.customize ["modifyvm", :id, "--memory", 1500]
    			 vb.customize ["modifyvm", :id, "--cpus", 1]

                    # Specify machine name
                    vb.name = "fnb-linux-node-#{i}"
                end
            end
	else 
            config.vm.define "win-#{i}" do |node|
                node.vm.box = "StefanScherer/windows_2016"
                node.vm.hostname = "win-#{i}"
                # Bridged network
                node.vm.network "private_network", ip:"192.168.58.#{i}"
                # Provider-specific configuration
                node.vm.provider "virtualbox" do |vb|
                    # Customize the amount of memory on the VM
                    vb.memory = "2048"
                    # Specify machine name
                    #vb.name = "win-#{i}"
        end
    end
end
end
end

