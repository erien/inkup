inkup
=====

*inkup* is an attempt to write a Vagrantfile capable of building a
virtual machine, which in turn can build Inkscape Trunk from sources.


Why?
====
I've been interested in contributing to the great Inkscape open source project for years.

However, every time I've started reading the build instructions, I've nearly fainted :).
The project is built in both C and C++, and it's got a huge list of intricate build dependencies,
not only direct dependencies but also build system dependencies.

After years of building up courage -- I spent a weekend making Inkscape compile, modified
the rectangle tool to always place the result rectangle at (0, 0). What a feeling seeing
the Inkscape built locally!

Also during that weekend, I developed this Vagrantfile in parallell, so the effort could be re-used
for someone else and lower the threshold to build Inkscape from sources, thus hopefully lowering the
threshold for more developers to contribute to Inkscape.

It also means starting development of inkscape on a new computer, or a re-installed computer,
is a breeze.

inkup was inspired by [this forum thread](http://inkscape.13.x6.nabble.com/Inkscape-with-Vagrant-Test-Inkscape-with-only-3-commands-td4969224.html|this thread).


The VM
------
The base VM O/S is Lubuntu Desktop 14.04-64 bit, which means you can log in and run your home-brewn Inkscape 


Dependencies
------------
You need [Vagrant](https://www.vagrantup.com/) and [VirtualBox](https://www.virtualbox.org/).

Tested on VirtualBox 4.3.10, 4.3.26 in combination with Vagrant 1.7.2 on Windows 7 and Ubuntu 14.04.


To build Inkscape Trunk
-----------------------

1. git clone `repo url`
2. cd inkup
3. vagrant up

The provision-script is written inline inside the Vagrantfile, and
basically adds the PPA for Inkscape Trunk to the VM, followed by
installing all packages necessary to build Inkscape from sources,
and finally builds Inkscape.


To run Inkscape Trunk
---------------------

Once the build is finished (this will take at least 15 minutes, or
more if you do not have the VM base image to start with), you can
log into the VM using username 'vagrant' and password 'vagrant'.

The inkscape binary will be found at `/home/vagrant/inkscape/src/inkscape`.

