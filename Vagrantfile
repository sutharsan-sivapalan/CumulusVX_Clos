##################################
##  Ansible Inventory Definitions #
###################################
      
groups = {
  "spine" => ["spine1", "spine2"], 
  "leaf" => ["leaf1", "leaf2", "leaf3", "leaf4"],
  "servers" => ["host1", "host2"],
  "networking:children" => ["spine", "leaf"]
}


##################################
#   Vagrant Machine Definitions  #
##################################
      
Vagrant.configure(2) do |config|

	config.vm.define "spine1" do |spine1|
		spine1.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		spine1.vm.hostname = "spine1"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l1"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l2"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l3"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l4"
		spine1.vm.network "private_network", virtualbox__intnet: "s1s21"
		spine1.vm.network "private_network", virtualbox__intnet: "s1s22"

		spine1.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end
		
		spine1.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111111"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
		end
	end

    config.vm.define "spine2" do |spine2|
        spine2.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

        spine2.vm.hostname = "spine2"
        spine2.vm.network "private_network", virtualbox__intnet: "s2l1"
        spine2.vm.network "private_network", virtualbox__intnet: "s2l2"
        spine2.vm.network "private_network", virtualbox__intnet: "s2l3"
        spine2.vm.network "private_network", virtualbox__intnet: "s2l4"
        spine2.vm.network "private_network", virtualbox__intnet: "s1s21"
        spine2.vm.network "private_network", virtualbox__intnet: "s1s22"

        spine2.vm.provision "ansible" do |ansible|
          ansible.playbook = "provisioning/playbook.yml"
          ansible.groups = groups
        end

        spine2.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--macaddress1", "000000111112"]
          v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
        end
    end

	config.vm.define "leaf1" do |leaf1|
		leaf1.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		leaf1.vm.hostname = "leaf1"
		leaf1.vm.network "private_network", virtualbox__intnet: "s1l1"
		leaf1.vm.network "private_network", virtualbox__intnet: "s2l1"
		leaf1.vm.network "private_network", virtualbox__intnet: "l1h1"
		leaf1.vm.network "private_network", virtualbox__intnet: "l1l21"
		leaf1.vm.network "private_network", virtualbox__intnet: "l1l22"
		
		leaf1.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		leaf1.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111121"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		end
	end

	config.vm.define "leaf2" do |leaf2|
		leaf2.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		leaf2.vm.hostname = "leaf2"
		leaf2.vm.network "private_network", virtualbox__intnet: "s1l2"
		leaf2.vm.network "private_network", virtualbox__intnet: "s2l2"
		leaf2.vm.network "private_network", virtualbox__intnet: "l2h1"
		leaf2.vm.network "private_network", virtualbox__intnet: "l1l21"
		leaf2.vm.network "private_network", virtualbox__intnet: "l1l22"
		
		leaf2.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		leaf2.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111122"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		end
	end

	config.vm.define "leaf3" do |leaf3|
		leaf3.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		leaf3.vm.hostname = "leaf3"
		leaf3.vm.network "private_network", virtualbox__intnet: "s1l3"
		leaf3.vm.network "private_network", virtualbox__intnet: "s2l3"
		leaf3.vm.network "private_network", virtualbox__intnet: "l3h2"
		leaf3.vm.network "private_network", virtualbox__intnet: "l3l41"
		leaf3.vm.network "private_network", virtualbox__intnet: "l3l42"

		leaf3.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		leaf3.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111123"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		end
	end

    config.vm.define "leaf4" do |leaf4|
        leaf4.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

        leaf4.vm.hostname = "leaf4"
        leaf4.vm.network "private_network", virtualbox__intnet: "s1l4"
        leaf4.vm.network "private_network", virtualbox__intnet: "s2l4"
        leaf4.vm.network "private_network", virtualbox__intnet: "l4h2"
        leaf4.vm.network "private_network", virtualbox__intnet: "l3l41"
        leaf4.vm.network "private_network", virtualbox__intnet: "l3l42"

        leaf4.vm.provision "ansible" do |ansible|
          ansible.playbook = "provisioning/playbook.yml"
          ansible.groups = groups
        end

        leaf4.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--macaddress1", "000000111124"]
          v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
          v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
        end
    end

	config.vm.define "host1" do |host1|
		host1.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host1.vm.hostname = "host1"
		host1.vm.network "private_network", virtualbox__intnet: "l1h1", auto_config: false
		host1.vm.network "private_network", virtualbox__intnet: "l2h1", auto_config: false
	  
		host1.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		end

		host1.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end

	config.vm.define "host2" do |host2|
		host2.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host2.vm.hostname = "host2"
		host2.vm.network "private_network", virtualbox__intnet: "l3h2", auto_config: false
		host2.vm.network "private_network", virtualbox__intnet: "l4h2", auto_config: false
	  
		host2.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		end

		host2.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end
end
