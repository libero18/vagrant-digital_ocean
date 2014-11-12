### Vagrant Plugins をインストールする

```
vagrant plugin install vagrant-digitalocean
vagrant plugin install dotenv
```

### Vagrant Boxes を登録する

```
vagrant box add --force digital_ocean 'https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box'
```

### ./.env を作成する

```
## https://cloud.digitalocean.com/settings/applications で設定した token を指定
TOKEN             =   'xxxxxxxxxxxxxxxx'

## https://cloud.digitalocean.com/ssh_keys で設定した SSH鍵名 を指定
SSH_KEY_NAME      =   'xxxxxxxxxxxxxxxx'

## SSH でのログインに利用する 秘密鍵のパス を指定
SSH_KEY_PATH      =   '~/.ssh/id_rsa'

## SSH でのログインに利用する ユーザー を指定
SSH_USER_NAME     =   'vagrant'

## 作成する Droplets の ホスト名 を指定
VM_HOSTNAME       =   'VM001'

## 作成する Droplets の OSイメージ を指定
VM_IMAGE          =   '7.0 x64'

## 作成する Droplets の リージョン を指定
VM_REGION         =   'sgp1'

## 作成する Droplets の サイズ を指定
VM_SIZE           =   '512mb'
```

### 複数の Droplets を扱う場合

###### ./VM001/.env
```
TOKEN             =   'xxxxxxxxxxxxxxxx'
SSH_KEY_NAME      =   'xxxxxxxxxxxxxxxx'
SSH_KEY_PATH      =   '~/.ssh/id_rsa'
SSH_USER_NAME     =   'vagrant'

VM_HOSTNAME       =   'VM001'
VM_IMAGE          =   '7.0 x64'
VM_REGION         =   'sgp1'
VM_SIZE           =   '512mb'
```


###### ./VM002/.env
```
TOKEN             =   'xxxxxxxxxxxxxxxx'
SSH_KEY_NAME      =   'xxxxxxxxxxxxxxxx'
SSH_KEY_PATH      =   '~/.ssh/id_rsa'
SSH_USER_NAME     =   'vagrant'

VM_HOSTNAME       =   'VM002'
VM_IMAGE          =   '14.04 x64'
VM_REGION         =   'sfo1'
VM_SIZE           =   '512mb'
```

###### ./VM003/.env
```
TOKEN             =   'xxxxxxxxxxxxxxxx'
SSH_KEY_NAME      =   'xxxxxxxxxxxxxxxx'
SSH_KEY_PATH      =   '~/.ssh/id_rsa'
SSH_USER_NAME     =   'vagrant'

VM_HOSTNAME       =   'VM003'
VM_IMAGE          =   'Docker 1.3.1 on 14.04'
VM_REGION         =   'nyc1'
VM_SIZE           =   '1024mb'
```


### Droplets を起動する

```
cd [起動したい Droplets の .env ファイルが存在するディレクトリ]
vagrant up --provider=digital_ocean --provision
```
