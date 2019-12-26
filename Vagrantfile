$script = <<-SCRIPT
# disable ipv6
echo "net.ipv6.conf.all.disable_ipv6 = 1" >> /etc/sysctl.conf
echo "net.ipv6.conf.default.disable_ipv6 = 1" >> /etc/sysctl.conf

# reload sysctl
sysctl -p

# install k3s
curl -sfL https://get.k3s.io | sh -
SCRIPT

Vagrant.configure("2") do |config|

  config.vm.box = "bento/centos-7"

  config.vm.provider "virtualbox" do |v|
    v.memory = 6144
  end

  config.vm.provision "shell", inline: $script
end
