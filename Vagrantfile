Vagrant.configure("2") do |config|
    (1..2).each do |i|
        if i <= 1
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
               
        config.vm.provision "shell", inline: <<-SHELL
       apt update -y
       apt install ansible -y
       apt install sshpass -y
	sudo su
       sed -i 's!\[defaults\]!\[defaults\]\nhost\_key\_checking\ = false!' /etc/ansible/ansible.cfg
        SHELL
            end
            end
	else 
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
    end
end
end
end

