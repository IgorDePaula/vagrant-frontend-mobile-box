Vagrant NG Box
=============================


Vagrant NG Box is a ready-to-go hybrid development environment for building mobile apps with Ionic, Cordova, and Android based in Ionic Box, with some modifications. Vagrant NG Box was built to make it easier for developers to build Android versions of their app, and especially for Windows users to get a complete dev environment set up without all the headaches.

For iOS developers, Vagrant NG Box won't do much for you right now unless you are having trouble installing the Android SDK, and Vagrant NG Box cannot be used for iOS development for a variety of legal reasons (however, the `ionic package` command in beta will soon fix that).


### Default packages installed

Packages installeds by default:

- Git;
- Java;
- "PT_BR" Package Language;
- Android SDK;
- Sass;
- Compass;


#### CLI

Was installed some functions and aliases for use in this box. The files `.functions` and `.aliases` are installed for `vagrant` user root folder and loaded in user login.


#### NodeJS

This vagrant box is using NVM (https://raw.github.com/creationix/nvm) with setup:

- NodeJS (Version 0.10.33);
- NPM (Version 2.2.0);
- cordova;
- ionic;
- yeoman;
- bower;
- grunt-cli;
- gulp;
- jshint;
- protractor;
- karma;


### Provision

This box is provisioned via shell script. If you would like to modify the package for your use, please take a look in [bootstrap.sh file](bootstrap.sh file)


### Installation

To install, download and install [Vagrant](https://www.vagrantup.com/downloads.html) for your platform, then download and install [VirtualBox](http://virtualbox.org/).

Once Vagrant and VirtualBox are installed, you can download the latest release of this GitHub repo, and unzip it. `cd` into the unzipped folder and run:

```bash
$ vagrant up
$ vagrant ssh
```

The username for vagrant is `vagrant` and the password is `vagrant`.

This will download and install the image, and then go through the dependencies and install them one by one. `vagrant ssh` will connect you to the image and give you a bash prompt. Once everything completes, you'll have a working box to build your apps on Android.

### Connected Android Devices

The installation create an `adb` alias for use in CLI environment more easily. The image also has support for connected USB Android devices. To test whether devices are connected, you can run (from the box):

```bash
$ sudo /home/vagrant/android-sdk-linux/platform-tools/adb devices
# or
$ sudo adb devices
```

If that does not work, or shows `????? permissions`, then run:

```bash
sudo /home/vagrant/android-sdk-linux/platform-tools/adb kill-server
sudo /home/vagrant/android-sdk-linux/platform-tools/adb start-server
# or
$ sudo adb kill-server
$ sudo adb start-server
```
