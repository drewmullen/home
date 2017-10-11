# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # setup proxy
    if Vagrant.has_plugin?("vagrant-proxyconf")
      config.proxy.http      = "http://PITC-Zscaler-Americas-Alpharetta3PR.proxy.corporate.ge.com:80"
      config.proxy.https     = "http://PITC-Zscaler-Americas-Alpharetta3PR.proxy.corporate.ge.com:80"
      config.proxy.no_proxy  = "localhost,127.0.0.1"
    end
  config.vm.define "acs" do |acs|
    acs.vm.box = "ubuntu/trusty64"
    acs.vm.hostname = "acs"
    acs.vm.network "private_network", ip: "192.168.33.10"
  end

  config.vm.define "web" do |web|
    web.vm.box="nrel/CentOS-6.5-x86_64"
    web.vm.hostname = "web"
    web.vm.network "private_network", ip: "192.168.33.20"
    web.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.define "db" do |db|
    db.vm.box = "nrel/CentOS-6.5-x86_64"
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.33.30"
  end


end