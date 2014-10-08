# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "trusty64"

  config.vm.provision "shell", privileged: false, inline: <<SCRIPT
    if ! which go; then
      curl -sL j.mp/godeb | tar xz
      ./godeb install
      rm godeb
    fi

    grep '^export GOPATH' ~/.bashrc || echo export GOPATH=~/go >> ~/.bashrc
    grep '^export PATH' ~/.bashrc || echo export PATH=\$PATH:~/go/bin >> ~/.bashrc

    mkdir -p ~/go/src/github.com
    [[ -L ~/go/src/github.com/lmars ]] || ln -nfs /vagrant ~/go/src/github.com/lmars
    grep ^cd ~/.bashrc || echo cd ~/go/src/github.com/lmars >> ~/.bashrc
SCRIPT
end
