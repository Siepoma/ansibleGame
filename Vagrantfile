Vagrant.configure("2") do |config|
  config.vm.define "docker1" do |docker1|
    docker1.vm.box = "jasonc/centos7-32bit"
    docker1.vm.hostname = 'docker1'
    docker1.vm.provision :shell, path: "bootstrap.sh"
    docker1.vm.network :private_network, ip: "192.168.56.101"

    docker1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "docker1"]
    end
  end

  config.vm.define "docker2" do |docker2|
    docker2.vm.box = "jasonc/centos7-32bit"
    docker2.vm.hostname = 'docker2'
    docker2.vm.provision :shell, path: "bootstrap.sh"
    docker2.vm.network :private_network, ip: "192.168.56.102"

    docker2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "docker2"]
    end
  end
end
