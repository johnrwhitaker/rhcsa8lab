Vagrant.configure("2") do |config|
    config.vm.box = "generic/rhel8"

    config.vm.define 'server1' do |node|
        node.vm.hostname = 'server1.local'
        node.vm.provision "ansible" do |ansible|
            ansible.playbook = "server1.yml"
        end
    end
end