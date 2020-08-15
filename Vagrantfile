Vagrant.configure("2") do |config|
    config.vm.box_check_update = false
    
    # Server 1 Configuration
    config.vm.define "server1" do |server1|
        config.vm.box = "generic/rhel8"
        server1.vm.network "private_network", ip: "192.168.77.2"
        server1.vm.provider :virtualbox do |server1|
            server1.customize ['modifyvm', :id,'--memory', '2048']
        end

        server1.vm.provision "ansible" do |ansible|
            ansible.playbook = "server1.yml"
            ansible.install = false
        end

        server1.vm.provision :shell, :inline => "reboot", run: "always"
    end

    # Server 2 Configuration
    config.vm.define "server2" do |server2|
        config.vm.box = "generic/rhel8"
        server2.vm.network "private_network", ip: "192.168.77.3"
        server2.vm.provider :virtualbox do |server2|
            server2.customize ['modifyvm', :id,'--memory', '2048']
        end

        server2.vm.provision "ansible" do |ansible|
            ansible.playbook = "server2.yml"
            ansible.install = false
        end

        server2.vm.provision :shell, :inline => "reboot", run: "always"
    end
end