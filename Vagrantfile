# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.hostname = "myhost.local"
  # config.vm.network "private_network", type: "dhcp"
  config.vm.network "private_network", ip: "192.168.56.10", hostname: true

  # config.ssh.username = 'local'
  config.vm.box = "bento/ubuntu-20.04"
  # config.vm.box_version = "1.0.282"

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell" do |s|
    ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
    s.inline = <<-SHELL

      echo #{ssh_pub_key} >> ~/.ssh/authorized_keys
    SHELL
  end

  # touch /root/.ssh/authorized_keys
  # echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
end
