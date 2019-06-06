Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/bionic64"

  config.ssh.forward_agent = true
  config.ssh.forward_x11 = true

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    # vb.gui = true
    vb.name = "virt-manager"
    vb.memory = "512"
    vb.customize ["modifyvm", :id, "--vram", "128"]
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt update
    sudo apt install -y xorg virt-manager ssh-askpass
  SHELL
end
