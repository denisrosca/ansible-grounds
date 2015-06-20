Vagrant.configure("2") do |config|

    config.vm.define "web_server1" do |web|
        web.vm.box = "ubuntu/vivid64"
    end

    #config.vm.define "haproxy" do |haproxy|
    #    haproxy.vm.box = "ubuntu/vivid64"
    #end
    

    config.vm.provision "ansible" do |ansible|
	ansible.playbook = "provisioning/playbook.yml"
        ansible.groups = {
	    "web_servers" => ["web_server1"],
	    "all_groups:children" => ["web_servers"]
        }
    end

end
