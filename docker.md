Install Docker for Pi


## Docker
######################################

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

## may skip
sudo add-apt-repository "deb [arch=armhf] https://download.docker.com/linux/ubuntu bionic test"

sudo apt-get update && sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

# may already been added
sudo groupadd docker

sudo usermod -aG docker $USER
sudo reboot
```

## Docker Compose
######################################

```
sudo apt-get install -y libffi-dev libssl-dev
sudo apt-get install -y python3 python3-pip
sudo apt-get remove python-configparser

sudo pip3 -v install docker-compose
```

# watch temp

```
watch -n 5 vcgencmd measure_temp
```

# ram
```
free -m
```

# disk space
```
df -m
```


pi@raspberrypi:~ $ cat ~/.bash_aliases

```
alias check_temp='watch -n 5 vcgencmd measure_temp'
alias check_ram='free -m'
alias check_diskspace='df -m'

alias docker-reset='docker system prune --force --volumes && docker container ls -aq | xargs docker container rm -f'

```


