Vagrant.configure("2") do |config|

  if Vagrant.has_plugin? "vagrant-vbguest"
     config.vbguest.no_install = true
     config.vbguest.auto_update = false
     config.vbguest.no_remote = true
  end
  config.vm.define :streama do |streama|
    streama.vm.provision "shell", path: "streama.sh"
    streama.vm.box = "bento/centos-7.9"
    streama.vm.network :private_network, ip: "192.168.100.2"
    streama.vm.hostname = "streama"
    streama.vm.provider "virtualbox" do |v|
      v.cpus = 3 
    end
  end
  config.vm.define :firewall do |firewall|
    firewall.vm.provision "shell", path: "firewall.sh"
    firewall.vm.box = "bento/centos-7.9"
    firewall.vm.network :public_network, ip: "192.168.20.131"
    firewall.vm.network :private_network, ip: "192.168.100.3"
    firewall.vm.hostname = "firewall"
    firewall.vm.provider "virtualbox" do |v|
      v.cpus = 2 
    end
  end

end