# Graphical devbox

## Description

My graphic devbox.

Setup:

- Users from GitHub (see group_vars/local to change users)
- SSH
- Docker and Docker Compose
- OpenJDK 8
- Intellij IDEA 14 Community
- XFCE 4
- Chromium
- Virtual Box Additions

## Prerequisite

1. [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
2. [Vagrant](https://docs.vagrantup.com/v2/installation/index.html)
3. Install vagrant proxy conf plugin (if you are behind a corporate proxy)
  ```
  vagrant plugin install vagrant-proxyconf
  ```
  Edit your global Vagrantfile (located in the .vagrant.d directory of your home directory):

  ```
  Vagrant.configure("2") do |config|
    if Vagrant.has_plugin?("vagrant-proxyconf")
      config.proxy.http     = "http://proxy-internet.localnet:3128/"
      config.proxy.https    = "http://proxy-internet.localnet:3128/"
      config.proxy.no_proxy = "localhost,.priv.corp.com"
    end
  end
  ```

## Usage

Start the VM with Vagrant:

```
vagrant up
```

> Note: The VM is provisioned with Ansible.

Done.
