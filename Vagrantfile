VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = 'ubuntu/trusty64'
    config.ssh.insert_key = false
    config.vm.network :private_network, type: "dhcp"

    config.vm.provider :virtualbox do |v|
        v.name = 'nvm_dev'
        v.memory = 1000
        v.cpus = 2
        v.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
        v.customize ['modifyvm', :id, '--ioapic', 'on']
    end

    config.vm.define 'nvm' do |machine|
        machine.vm.provision :ansible do |ansible|
            ansible.playbook = 'tests/test.yml'
        end
    end
end
