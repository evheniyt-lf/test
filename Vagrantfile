Vagrant.configure("2") do |config|
  config.vm.define "prometheus" do |prometheus|
    # config.disksize.size = '10GB'
    prometheus.vm.box = "debian9.4.box"
    prometheus.vm.hostname = "devsandbox"
    prometheus.vm.box_url = "file:///media/evheniyt/Other/debian9.4.box"

    prometheus.vm.network :private_network, ip: "172.28.128.110"
    prometheus.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"

    prometheus.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 2096]
      v.customize ["modifyvm", :id, "--name", "prometheus"]
    end
  end
end
