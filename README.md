# Cornerstone

http://rackerlabs.github.io/cornerstone/

HarpJS application to house custom CSS framework

## Quickstart

CSS files ready for use:

http://rackerlabs.github.io/cornerstone/css/main.css
http://rackerlabs.github.io/cornerstone/css/responsive.css
http://rackerlabs.github.io/cornerstone/css/tooltips.css

## Basic usage

1. [Install HarpJS](http://harpjs.com/docs/quick-start)
2. Checkout this repo
3. Run `harp server public`

## HarpJS Container setup

1. [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. [Install Vagrant](http://downloads.vagrantup.com/)
3. Set `FORWARD_DOCKER_PORTS` env variable (See [Vagrantfile](https://github.com/rackerlabs/cornerstone/blob/master/Vagrantfile#L88))
4. `vagrant up` (Will take a cople of minutes to boot first time)
5. `vagrant ssh`
6. Navigate to `/vagrant` (should map to cloned repo directory)
7. `sudo docker build -t cornerstone .`

## HarpJS Container usage

*From within Vagrant Box*

### Interactive Server

```bash
sudo docker run -i -t -p 49000:9000 -v /vagrant/:/mnt/cornerstone:rw cornerstone
```
    
### Interactive Compile

```bash
sudo docker run -i -t -p 49000:9000 -v /vagrant/:/mnt/cornerstone:rw cornerstone compile /mnt/cornerstone/public
```

### Daemon Mode Server

```bash
sudo docker run -d -p 49000:9000 -v /vagrant/:/mnt/cornerstone:rw cornerstone
```
