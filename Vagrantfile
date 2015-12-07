# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network :forwarded_port, guest: 80, host: 8088, auto_correct: true
  config.vm.boot_timeout = 300
  config.ssh.forward_agent = true

  config.vm.provider :virtualbox do |v|
    v.name = "development_base"
    v.memory = 1024
  end

  config.vm.provision :shell, :inline => <<-EOS
    apt-get install -y software-properties-common
    apt-add-repository ppa:ansible/ansible
    apt-get update
    apt-get install -y ansible
    apt-get install -y git
    apt-get install -y bash
    apt-get install -y ctags
    git clone https://github.com/m3y/dotfiles.git /home/vagrant/.ghq/github.com/m3y/dotfiles
    git clone https://github.com/m3y/playbooks.git /home/vagrant/.ghq/github.com/m3y/playbooks
    chown -R vagrant /home/vagrant/.ghq
  EOS
end
