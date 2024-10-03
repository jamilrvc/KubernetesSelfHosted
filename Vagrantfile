 Vagrant.configure("2") do |config|
   config.ssh.insert_key = false
   config.vm.provision :ansible do |ansible|
      ansible.playbook = "playbooks/cluster-k8s.yml"
    end
   config.vm.define :master01 do |master01|
     master01.vm.box = "debian/bookworm64"
     master01.vm.hostname = "master01"
     master01.vm.provider :libvirt do |libvirt|
       libvirt.memory = 6048
       libvirt.cpus = 2
    end
     master01.vm.network :private_network, :libvirt_network_name => "red1", :libvirt_dhcp_enabled => false, :ip => "10.0.0.10", :libvirt_forward_mode => "none"
     #master01.vm.network :private_network, :netmask=>"255.255.255.0", :type => "dhcp", :libvirt__network_address => '192.168.200.0', :libvirt_forward_mode => "none"

  end
  config.vm.define :master02 do |master02|
    master02.vm.box = "debian/bookworm64"
    master02.vm.hostname = "master02"
    master02.vm.provider :libvirt do |libvirt|
      libvirt.memory = 6048
      libvirt.cpus = 2
   end
    master02.vm.network :private_network, :libvirt_network_name => "red1", :libvirt_dhcp_enabled => false, :ip => "10.0.0.11", :libvirt_forward_mode => "none"
    #master01.vm.network :private_network, :netmask=>"255.255.255.0", :type => "dhcp", :libvirt__network_address => '192.168.200.0', :libvirt_forward_mode => "none"

 end
 
  config.vm.define :worker01 do |worker01|
    worker01.vm.box = "debian/bookworm64"
    worker01.vm.hostname = "worker01"
    worker01.vm.provider :libvirt do |libvirt|
      libvirt.memory = 2048
      libvirt.cpus = 2
    end
    worker01.vm.network :private_network, :libvirt_network_name => "red1", :libvirt_dhcp_enabled => false, :ip => "10.0.0.21", :libvirt_forward_mode => "none"
    #worker01.vm.network :private_network, :netmask=>"255.255.255.0",:type => "dhcp", :libvirt__network_address => '192.168.200.0', :libvirt_forward_mode => "none"
  end
  config.vm.define :worker02 do |worker02|
    worker02.vm.box = "debian/bookworm64"
    worker02.vm.hostname = "worker02"
    worker02.vm.provider :libvirt do |libvirt|
      libvirt.memory = 2048
      libvirt.cpus = 2
    end
    #worker02.vm.network :private_network, :netmask=>"255.255.255.0",:type => "dhcp", :libvirt__network_address => '192.168.200.0', :libvirt_forward_mode => "none"
    worker02.vm.network :private_network, :libvirt_network_name => "red1", :libvirt_dhcp_enabled => false, :ip => "10.0.0.22", :libvirt_forward_mode => "none"
  end
 end
