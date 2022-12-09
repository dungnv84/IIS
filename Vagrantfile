Vagrant.configure("2") do |config|
    (1..2).each do |i|
        if i <=2 
            config.vm.define "fnb-linux-node-#{i}" do |node|
                node.vm.box = "bento/ubuntu-20.04"
                node.vm.hostname = "fnb-linux-node-#{i}"
                # Bridged network
                node.vm.network "private_network", ip:"192.168.58.11#{i}"
                # Provider-specific configuration
                node.vm.provider "vmware_workstation" do |vb|
                    # Customize the amount of memory on the VM
    		    vb.memory = "1024"
                    # Specify machine name
                    #vb.name = "fnb-linux-node-#{i}"
                end
        config.vm.provision "shell", inline: <<-SHELL
       apt update -y
       apt install ansible -y
       apt install sshpass -y

       sed -i 's!\[defaults\]!\[defaults\]\nhost\_key\_checking\ = false!' /etc/ansible/ansible.cfg
        SHELL

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

