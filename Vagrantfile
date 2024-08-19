Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-22.04"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git llvm clang gcc-multilib libbpf-dev linux-headers-$(uname -r)

    if [ ! -f go1.23.0.linux-amd64.tar.gz ]; then
      curl -sLO https://go.dev/dl/go1.23.0.linux-amd64.tar.gz
       rm -rf /usr/local/go && tar -C /usr/local -xzf go1.23.0.linux-amd64.tar.gz
       echo export PATH=$PATH:/usr/local/go/bin >> .profile
    fi
  SHELL
end
