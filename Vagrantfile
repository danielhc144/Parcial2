Vagrant.configure("2") do |config|
 if Vagrant.has_plugin? "vagrant-vbguest"
 config.vbguest.no_install = true
 config.vbguest.auto_update = false
 config.vbguest.no_remote = true
 config.vm.box_download_insecure=true
 end
 config.vm.define :clienteFw do |clienteFw|
 clienteFw.vm.box = "danielhc144/firewall"
 clienteFw.vm.box_version = "0.0.1"
 clienteFw.vm.network :private_network, ip: "209.191.100.2"
 clienteFw.vm.hostname = "clienteFw"
 end
 config.vm.define :firewall do |firewall|
 firewall.vm.box = "danielhc144/firewall"
 firewall.vm.box_version = "0.0.1"
 firewall.vm.network :private_network, ip: "209.191.100.3"
 firewall.vm.network :private_network, ip: "192.168.100.3"
 firewall.vm.hostname = "firewall"
 end
 config.vm.define :servidor2 do |servidor2|
 servidor2.vm.box = "danielhc144/firewall"
 servidor2.vm.box_version = "0.0.1"
 servidor2.vm.network :private_network, ip: "192.168.100.4"
 servidor2.vm.hostname = "servidor2"
 config.vm.synced_folder "C:/document","/vagrant", type: "rsync"
 end
 config.vm.define :dnstest do |dnstest|
 dnstest.vm.box = "bento/ubuntu-20.04"
 dnstest.vm.network :private_network, ip: "192.168.20.2"
 dnstest.vm.hostname = "dnstest"
 config.vm.provision :shell, path: "provisionamiento.sh", run: "alwways"
 end
end