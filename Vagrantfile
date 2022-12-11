Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04-arm64"

  config.vm.provider "parallels" do |prl|
    prl.linked_clone = false

    prl.name   = "monitoring"
    prl.memory = 1024
    prl.cpus   = 1
  end

  config.vm.network "forwarded_port", guest: 9090, host: 9090
  config.vm.network "forwarded_port", guest: 9091, host: 9091
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  config.vm.provision "shell", path: "setup.sh"
end
