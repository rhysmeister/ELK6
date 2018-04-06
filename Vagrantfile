Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  # Add 8GB RAM
  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "awx",
      "--memory", "8192"
    ]
  end

  config.vm.hostname = "elk"
  config.vm.network "private_network", ip: "192.168.4.243"
  config.vm.network "forwarded_port", guest: 9200, host: 9200

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "elk.yml"
  end

end
