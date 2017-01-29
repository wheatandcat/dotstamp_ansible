Vagrant.configure("2") do |config|
    config.vm.provider :virtualbox do |v|
       v.name = "centos7.2"
       v.customize ["modifyvm", :id, "--memory", 3072]
    end

    config.vm.box = "centos7.2"
    config.vm.box_url = "https://github.com/CommanderK5/packer-centos-template/releases/download/0.7.2/vagrant-centos-7.2.box"

    config.vm.network :private_network, ip: "192.168.33.10"
    config.ssh.forward_agent = true

end
