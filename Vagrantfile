# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
    # Configuración de la primera máquina virtual
    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/focal64" 
      web1.vm.hostname = "web1"  
      web1.vm.network "private_network", type: "dhcp" 
  
      # Instalación de Apache y configuración
      web1.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
        sudo systemctl enable apache2
        sudo systemctl start apache2
        echo "Servidor web 1 - Hola Mundo desde Vagrant" | sudo tee /var/www/html/index.html
      SHELL
  

    end
  
    # Configuración de la segunda máquina virtual
    config.vm.define "web2" do |web2|
      web2.vm.box = "ubuntu/focal64" 
      web2.vm.hostname = "web2"     
      web2.vm.network "private_network", type: "dhcp" 
  
      web2.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
        sudo systemctl enable apache2
        sudo systemctl start apache2
        echo "Servidor web 2 - Hola Mundo desde Vagrant" | sudo tee /var/www/html/index.html
      SHELL
  
    end
  
  end
  