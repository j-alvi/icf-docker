# Installation

## Using Vagrant (Recommended)

### Prerequisites:

* Ensure Oracle VirtualBox is installed: https://www.virtualbox.org/wiki/Downloads
* Ensure Vagrant is installed and correctly configured: https://www.vagrantup.com/downloads.html
* Ensure Vagrant vb-guest plugin is installed: `vagrant plugin install
  vagrant-vbguest`

### Instructions

Video:

[![asciicast](https://asciinema.org/a/o3TGQ8U09nv5NnwhWp5WkLGxc.png)](https://asciinema.org/a/4wL2mMh22qSWsHPsDdBZAopkC)

Text:

```
mkdir ~/Developer/ICF
cd ~/Developer/ICF
git clone https://github.com/faraazkhan/icf-docker.git
cd icf-docker
vagrant up
```

### Verification

SSH into each vagrant box and verify docker engine is available

```
vagrant ssh master
docker run hello-world
exit
```

```
vagrant ssh node0
docker run hello-world
exit
```

## Without Vagrant

Install two Ubuntu 16.04 VMs using your preferred mechanism.

Then follow instructions below for each VM.

Video:

[![asciicast](https://asciinema.org/a/HySLvDdZ6HvHw3scRuaCAZFTj.png)](https://asciinema.org/a/HySLvDdZ6HvHw3scRuaCAZFTj)

SSH into the VM (ensure you have root/sudo access).

Then download the provision script as follows:

```
curl https://raw.githubusercontent.com/faraazkhan/icf-docker/master/provision.sh > provision.sh
```

Once you have made the appropriate modifications, you can run the script on each node as follows:

```
sudo bash provision.sh
```

Log out of the VM, and log back in, then verify your installation with:

`docker run hello-world`

