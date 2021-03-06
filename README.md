# Highway Three Solutions - Vagrant Setup

This is for setting up a new project using [Vagrant][2] and [Scotch Box][3].

1. Install [VirtualBox][1].

2. Install [Vagrant][2].

3. Change directory to project location.

4. ```git clone https://github.com/scotch-io/scotch-box <project name>```

5. ```cd <project name>```

6. ```vagrant up```

7. ```cd public```

8. Copy project files into this directory and run any project-specific configuration steps required.

9. Access the project from [http://192.168.33.10](http://192.168.33.10).

## Optional Configuration

### Multiple Vagrants

If running multiple Vagrant instances, the IP address should be changed.  Edit the `Vagrantfile` and change the following line:

```
    config.vm.network "private_network", ip: "192.168.33.10"
```

Change ```192.168.33.10``` to a different IP address.

After modifying the IP address, reload the Vagrant instance with:

```
vagrant reload
```

### Virtual Hosts

If preferred, virtual hosts (e.g. ```http://projectname.dev```) can be used instead of IP addresses.  Edit your `hosts` file (usually found in `/etc/hosts`) and add:

```
192.168.33.10 projectname.dev
```

Access the project from the new URL.  Additional steps may be required per project to fully support the new virtual host.

Note: The IP address `192.168.33.10` is the default IP address for a new Vagrant instance.  Use the IP address inside the `Vagrantfile`.


[1]: https://www.virtualbox.org/wiki/Downloads
[2]: https://www.vagrantup.com/downloads.html
[3]: https://github.com/scotch-io/scotch-box
