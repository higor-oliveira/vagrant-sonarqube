Vagrant.configure("2") do |config|
    config.vm.define "db" do |db|
        db.vm.box = "ubuntu/focal64"
        db.vm.provider "virtualbox" do |vb|
            vb.memory = "1024"
        end

        db.vm.provision "ansible" do |ansible|
            ansible.playbook = "provisioning/postgres.yaml"
        end
        db.vm.network "private_network", ip: "192.168.10.10"
    end

    config.vm.define "sonarqube" do |sonar|
        sonar.vm.box = "ubuntu/focal64"
        sonar.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
        end

        sonar.vm.provision "ansible" do |ansible|
            ansible.playbook = "provisioning/sonarqube.yaml"
        end
        sonar.vm.network "private_network", ip: "192.168.10.20"
    end
end