#### Inhaltsverzeichnis

- [Firewall](#firewall)
- [Reverse Proxy](#reverse-proxy)
- [Benutzer und Rechtevergabe](#benutzer-und-rechtevergabe)
- [SSH Tunnel](#ssh-tunnel)
- [LDAP](#ldap)

# Firewall
Um mehr Sicherheit zu garantieren, habe ich eine Firewall hinzugefügt.
```Shell 
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.10.10"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--natpf1", "guestapache,tcp,,8080,,80"]
  end
  config.vm.provision "shell", inline: <<-SHELL
    echo 'vagrant:vagrant' | chpasswd
    sudo apt-get update
    apt-get install -y ufw
    ufw allow 80
    ufw allow 8080
    ufw --force enable
    sudo apt-get -y install apache2
    sudo service apache2 restart
  SHELL
end
```
# Reverse Proxy

# Benutzer und Rechtevergabe

# SSH Tunnel

# LDAP

[⇧ **Nach oben**](#inhaltsverzeichnis)