
# Win-Desktop

This repo installs some basis tools on a Windows 10 Vagrant machine
intended to help developers of OCaml get started on Windows.

```shell=
apt install virtualbox ansible rdesktop
```

Install the latest version of Vagrant.  Usually this is later than the
one packaged by the distribution and the latest version is required to
work properly with WinRM.  Certainly, `apt install vagrant` didn't work
for me on Ubuntu 22.04.

The installation details can be found
[here](https://developer.hashicorp.com/vagrant/downloads), and for Ubuntu
they are:

```shell=
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install vagrant
```

Install with WinRM helpers for Ruby

```shell=
sudo gem install -r winrm              # needed for Windows connectivity
sudo gem install -r winrm-elevated     # needed for Windows connectivity
```

Edit `Vagrantfile` and set appropriate figures for memory and CPU.
The values I have put probably represent the minimums but don't set
these too more than your physical machine has.

Create the VM:

```shell
VAGRANT_DEFAULT_PROVIDER=virtualbox vagrant up
```

