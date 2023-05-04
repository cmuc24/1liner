fast snippets

```shell script
#!/bin/bash
apt update && apt upgrade -y
sudo apt update && sudp apt upgrade -y

apt install curl -y
```

```shell script
#!/bin/bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
rm get-docker.sh
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
sudo usermod -aG docker $(whoami)
su - $(whoami)
groups $(whoami)
```

Testing VOLTA

https://docs.volta.sh/guide/getting-started

```shell
curl https://get.volta.sh | bash
```

or usable: nvm: npm & yarn
```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```