# https://github.com/smdahlen/vagrant-digitalocean#configure
# vagrant up --provider=digital_ocean --provision

Dotenv.load
Vagrant.configure('2') do |config|
  config.vm.provider :digital_ocean do |provider, override|

    ## Personal Access Token
    provider.token                =   "#{ENV['TOKEN']}"

    ## SSH
    provider.ssh_key_name         =   "#{ENV['SSH_KEY_NAME']}"
    override.ssh.private_key_path =   "#{ENV['SSH_KEY_PATH']}"
    override.ssh.username         =   "#{ENV['SSH_USER_NAME']}"

    ## Vagrant Box (Dummy)
    override.vm.box               =   'digital_ocean'
    override.vm.box_url           =   'https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box'

    ## Droplets
    config.vm.hostname            =   "#{ENV['VM_HOSTNAME']}"
    provider.image                =   "#{ENV['VM_IMAGE']}"
    provider.region               =   "#{ENV['VM_REGION']}"
    provider.size                 =   "#{ENV['VM_SIZE']}"

  end
end
