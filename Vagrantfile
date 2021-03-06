# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise32"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

  # Assign this VM to a host-only network IP, allowing you to access it
  # via the IP. Host-only networks can talk to the host machine as well as
  # any other machines on the same network, but cannot be accessed (through this
  # network interface) by any external networks.
  config.vm.network :hostonly, "192.168.33.190"

  # More Memory for the CF Monster
  config.vm.customize [
    "modifyvm", :id, 
    "--memory", "1024",
    "--name", "cf9"
  ]

  # Assign this VM to a bridged network, allowing you to connect directly to a
  # network using the host's network device. This makes the VM appear as another
  # physical device on your network.
  # config.vm.network :bridged

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  # config.vm.forward_port 80, 8080

  # Map additional folders into the webroot
  # config.vm.share_folder "somesite", "/vagrant/somesite", "~/Sites/somesite"


  # Enable provisioning with chef solo, specifying a cookbooks path, roles
  # path, and data_bags path (all relative to this Vagrantfile), and adding 
  # some recipes and/or roles.
  #
  config.vm.provision :chef_solo do |chef|

    chef.cookbooks_path = "./cookbooks"
    chef.add_recipe "coldfusion902::default"
    chef.add_recipe "coldfusion902::jws"

    # If you'd like to do addition configuration via chef.json, add the following recipe
    # chef.add_recipe "coldfusion902::configure"

    # Here's a sample DB config, uncomment and adjust accordinly
    # chef.json = {
    #   "cf902" => {
    #     "config_settings" => {
    #       "datasource" => {
    #         "MSSql" => [
    #           {
    #             "name" => "MYDSN",
    #             "host" => "mydbserver",
    #             "database" => "mydb",
    #             "username" => "dbuser",
    #             "password" => "dbpassword",
    #             "sendStringParametersAsUnicode" => true,
    #             "disable_clob" => false,
    #             "disable_blob" => false,
    #           }
    #         ]
    #       }
    #     }
    #   }
    # }

  end

end
