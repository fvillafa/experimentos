Vagrant.configure("2") do |config|

  #config.vm.box = "debian/buster64"
  
  config.vm.define "haproxy" do |proxy|
    proxy.vm.box = "debian/buster64"
    proxy.vm.network "private_network", ip:"192.168.100.10"
    proxy.vm.provider :virtualbox do |vb|
        vb.memory = 512
        vb.cpus = 1
    end
    proxy.vm.provision "shell", inline: <<-SHELL
      hostname haproxy.local
      apt-get update
      apt-get install -y haproxy
    SHELL
    
  end

  config.vm.define "app1" do |app1|
    app1.vm.box = "debian/buster64"
    app1.vm.network "private_network", ip:"192.168.100.20"
    app1.vm.provider :virtualbox do |vb|
        vb.memory = 512
        vb.cpus = 1
    end
  end
  
  config.vm.define "app2" do |app2|
    app2.vm.box = "debian/buster64"
    app2.vm.network "private_network", ip:"192.168.100.21"
    app2.vm.provider :virtualbox do |vb|
        vb.memory = 512
        vb.cpus = 1
    end
  end

  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # config.vm.network "private_network", ip: "192.168.33.10"

  # config.vm.network "public_network"

  # config.vm.synced_folder "../data", "/vagrant_data"

  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
