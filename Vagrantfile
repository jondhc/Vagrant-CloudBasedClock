
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "private_network", ip: "192.168.40.30"
  config.vm.network "public_network"
  config.vm.synced_folder "data/", "/home/vagrant/files"
  config.vm.provision "shell", inline: <<-SHELL
    cd files
    python3 server.py
  SHELL
end
