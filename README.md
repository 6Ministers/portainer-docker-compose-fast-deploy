# Installing Portainer with docker-compose.

## Quick Installation

**Before starting the instance, direct the domain (subdomain) to the ip of the server where Portainer will be installed!**

## 1. Portainer Server Requirements
From and more
- 1 CPUs
- 1 RAM 
- 10 Gb 

Run for Ubuntu 22.04

``` bash
sudo apt-get purge needrestart
```

Install docker and docker-compose:

``` bash
curl -s https://raw.githubusercontent.com/6Ministers/portainer-docker-compose-fast-deploy/master/setup.sh | sudo bash -s
```

Download Portainer instance:


``` bash
curl -s https://raw.githubusercontent.com/6Ministers/portainer-docker-compose-fast-deploy/master/download.sh | sudo bash -s portainer
```

If `curl` is not found, install it:

``` bash
$ sudo apt-get install curl
# or
$ sudo yum install curl
```

Go to the catalog

``` bash
cd portainer
```

To change the domain in the `Caddyfile` to your own

``` bash
https://portainer.your-domain.com:443 {
    reverse_proxy :9000
	# tls admin@example.org
	encode zstd gzip
	file_server

...	
}
```

**Run Portainer:**

``` bash
docker-compose up -d
```

Then open `https://portainer.your-domain.com:` to access Portainer


## Portainer container management

**Run Portainer**:

``` bash
docker-compose up -d
```

**Restart**:

``` bash
docker-compose restart
```

**Restart**:

``` bash
sudo docker-compose down && sudo docker-compose up -d
```

**Stop**:

``` bash
docker-compose down
```

## Documentation

https://docs.portainer.io/advanced/reverse-proxy/traefik

https://www.portainer.io/
