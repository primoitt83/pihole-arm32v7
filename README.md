# pihole-arm32v7

Works both arm32v7 and aarch64.

Tested on Orange Pi 3B Ubuntu 24.04

## How to install?

Disable local dns service:
````
systemctl stop systemd-resolved

systemctl disable systemd-resolved
````

Update local dns on host:
````
cp /etc/resolv.conf /etc/resolv.conf.bkp

cat > /etc/resolv.conf

nameserver 8.8.8.8

nameserver 1.1.1.1
````
Clone this project:
````
cd /opt

git clone https://github.com/primoitt83/pihole-arm32v7.git

cd pihole-arm32v7
````
Change variables below:
````
vim  docker-compose.yml

- FTLCONF_LOCAL_IPV4=myHomeserverIP

- WEBPASSWORD=myPassword

- REV_SERVER_CIDR=192.168.0.0/16 (change to your network)

- REV_SERVER_TARGET=myGateway (usually router's ip)

docker-compose up -d
````

Check logs:
````

(...)
````