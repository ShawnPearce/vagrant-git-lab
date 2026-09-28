Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-24.04"
  config.vm.network "private_network", ip: "192.168.56.10"
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provision "shell", inline: <<-SHELL
    set -e
    apt-get update
    apt-get install -y apache2
    echo "Hello from Vagrant" > /var/www/html/index.html
    systemctl enable --now apache2
  SHELL
end
