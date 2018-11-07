# Easy UBNT
A collection of tools to make managing UBNT software easier!

## Who would benefit from this project?
* System administrators who are experienced with Linux but would prefer a "cheatsheet" so they don't have to learn or re-learn the recommended way to install UBNT software whenever they need to deploy or re-deploy servers.
* System administrators with limited Linux experience.
* End-users who want an easy way to install UBNT software.

## UniFi Installer
This script guides you, using the wisdom of the UBNT community, through installing and upgrading the UniFi Controller software from UBNT, along with it's dependencies. In addition it will install basic software such as OpenSSH and UFW and configure them to secure access to your controller. Let's Encrypt setup for trouble-free SSL connections to your controller is also a built-in option with this script.

### How to Begin
Download the script then execute the script using bash. Be sure to use `sudo` if not logged in as root.
```console
wget https://raw.githubusercontent.com/sprockteam/easy-ubnt/master/unifi-installer.sh -O unifi-installer.sh
sudo bash unifi-installer.sh
```

Optionally you can make the script executable and then run it.
```console
chmod +x unifi-installer.sh; sudo ./unifi-installer.sh
```

### Script Options
You can automatically accept the license by using the -a option.
```console
sudo bash unifi-installer.sh -a
```

You can accept all the default answers to the question prompts using the -q option.
```console
sudo bash unifi-installer.sh -q
```

**Pro Tip:** It is recommended to run the script through once and answer all of the prompts. After that, running the script again is fast and easy using the -a and -q options together.
```console
sudo bash unifi-installer.sh -aq
```

You can get verbose output of commands during script run by using the -v option.
```console
sudo bash unifi-installer.sh -v
```

You can trace each command of the script to see what it's doing by using the -x option.
```console
sudo bash unifi-installer.sh -x
```

### Script Logging
Version 0.5.0 introduced a logging mechanism to the script. The last 5 logs are saved in `/var/log/easy-ubnt` and the latest script log is symlinked as `unifi-installer-latest.log`.
```console
cat /var/log/easy-ubnt/unifi-installer-latest.log | more
```
