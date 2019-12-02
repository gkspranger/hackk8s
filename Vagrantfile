Vagrant.configure("2") do |config|

  config.vm.box = "bento/centos-7"

  config.vm.provider "virtualbox" do |v|
    v.memory = 8192
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.install_mode = "pip"
  end
end
