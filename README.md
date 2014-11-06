### Vagrant Plugins

```
vagrant plugin install vagrant-digitalocean
vagrant plugin install dotenv
```

### Vagrant Boxes

```
vagrant box add --force digital_ocean 'https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box'
```

### ./.env

```
## https://cloud.digitalocean.com/settings/applications で設定した token を指定
TOKEN          =  'xxxxxxxxxxxxxxxx'

## https://cloud.digitalocean.com/ssh_keys で設定した SSH鍵名 を指定
SSH_KEY_NAME   =  'xxxxxxxxxxxxxxxx'

## SSH でのログインに利用する 秘密鍵のパス を指定
SSH_KEY_PATH   =  '~/.ssh/id_rsa'
```

