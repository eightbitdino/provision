# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  # config.vm.box = "centos/7"
  # config.vm.box = "addle/windows-server-2012-r2"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
    config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
    config.vm.provider "vmware_workstation" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
      vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
    end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
    (1..15).each do |i|
      config.vm.define "web#{i}" do |web|
          web.vm.box = "centos/7"
	  web.vm.provision "shell",
		  inline: "echo ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDe2H+h4daATHIlZe6OhiFw9+Q9tQd08bhvwPZdB4B7/M+apARwoGi4ziLwGU7YmiujjydxLNf/Ggjem3KHYDSdgwOvcH7zgvqhcsXvtCAWjeAeCsFCyhse5FaS+eGfud1sIKlg8m4oXjFIAVapE/Yyaho6W/VDlUtgayGbtaVzaUBxYwwjTlefaTLAoeLmLU0DIp8IzK+A3FKm/VioT4FbW5gB5khHN3T6GfORa7NLJxTYNO8JHLN/CMDVwurajqGnd4HQPoclYpHorpucA9JdUL+g2XvbLgRUKI9M4MpXdajVk0mEHHnx4hBeFmHoCJB9nHcwnQH+TjbQTT2pvqe/ htfenner@DESKTOP >> /home/vagrant/.ssh/authorized_keys"
      end
    end
    
    (1..4).each do |j|
      config.vm.define "db#{j}" do |db|
          db.vm.box = "centos/7"
	  db.vm.provision "shell",
		  inline: "echo ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDe2H+h4daATHIlZe6OhiFw9+Q9tQd08bhvwPZdB4B7/M+apARwoGi4ziLwGU7YmiujjydxLNf/Ggjem3KHYDSdgwOvcH7zgvqhcsXvtCAWjeAeCsFCyhse5FaS+eGfud1sIKlg8m4oXjFIAVapE/Yyaho6W/VDlUtgayGbtaVzaUBxYwwjTlefaTLAoeLmLU0DIp8IzK+A3FKm/VioT4FbW5gB5khHN3T6GfORa7NLJxTYNO8JHLN/CMDVwurajqGnd4HQPoclYpHorpucA9JdUL+g2XvbLgRUKI9M4MpXdajVk0mEHHnx4hBeFmHoCJB9nHcwnQH+TjbQTT2pvqe/ htfenner@DESKTOP >> /home/vagrant/.ssh/authorized_keys"
      end
    end

    (1..2).each do |k|
      config.vm.define "dns#{k}" do |dns|
          dns.vm.box = "addle/windows-server-2012-r2"
      end
    end
end
