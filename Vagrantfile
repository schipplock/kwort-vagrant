Vagrant.configure("2") do |config|
  config.ssh.shell = "/bin/bash"
  config.vm.box = "schipplock/kwort"
  config.vm.box_version = "4.3.2"
  config.vm.guest = :linux
  # uncomment the next two lines if you are testing the box you created with packer
  #config.vm.box = "kwort/4"
  #config.vm.box_url = "packer_virtualbox-iso_virtualbox.box"
  config.vm.network "public_network"

  config.vm.provider "virtualbox" do |v|
    v.name = "kwort-dev"
    v.memory = 1024
    v.cpus = 2
    v.gui = false
  end

  # this will be executed once when the vm is being set up
  config.vm.provision "shell", inline: <<-SHELL
    echo "Kwort Vagrant v4.3.2"
  SHELL

  # this will be executed everytime you "up" the vm
  config.vm.define "kwort" do |kwort|
    kwort.vm.provision "shell", run: "always", inline: <<-SHELL
        echo "Welcome to Kwort 4.3.2!"
    SHELL
  end

end
