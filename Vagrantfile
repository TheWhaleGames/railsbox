# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.ssh.forward_agent = true

  # Forward the Rails server default port to the host
  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provision :chef_solo do |chef|
    chef.version = "12.3.0"
    chef.cookbooks_path = ["cookbooks"]

    chef.add_recipe 'apt'
    chef.add_recipe 'nodejs'
    chef.add_recipe 'ruby_build'
    chef.add_recipe 'rbenv::user'
    chef.add_recipe 'rbenv::vagrant'
    chef.add_recipe 'vim'
    chef.add_recipe 'mysql::server'
    chef.add_recipe 'mysql::client'
    chef.add_recipe 'sqlite'

    chef.json = {
      rbenv: {
        user_installs: [{
          user: 'vagrant',
          rubies: ['2.2.1'],
          global: '2.2.1',
          gems: {
            '2.2.1' => [
              { name: 'bundler' }
            ]
          }
        }]
      },
      mysql: {
        server_root_password: ''
      }
    }
  end
end
