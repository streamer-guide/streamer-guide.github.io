# Streamer guide website

## What is this

This is a website that collects guides for streamers ranging from how to get started, and how to become professional.


# Virtual machine testing environment

You should check locally what kind of results you get if making changes, before pushing to GitHub.

The VM is using 64-bit [Ubuntu](http://www.ubuntu.com/)
[Trusty (14.04)](http://releases.ubuntu.com/14.04/). 

## What you need

You need to have the following installed:

 * [VirtualBox](https://www.virtualbox.org/)
 * [Vagrant](https://www.vagrantup.com/downloads) 
 

## How to manage the VM

Simply clone this repository, or download the ZIP (look on the right), and 
open your command prompt. Then change to the directory where the files are
 located, so e.g. if you extracted the zip to `C:\streamerguide` you would run 
 `cd \streamerguide`.
 
Then boot up the VM with:
```
vagrant up
```
This will download the base VM and install the latest version of Jekyll on 
it. It will likely take a couple of minutes so give it some time. The 
terminal should give you (sometimes rather technical) details on what's 
going on during that.

There might be a few User Account Control security warning popups as Virtualbox
sets up the networking interfaces for the VM.


Once you are done with the VM, you can shut it down (frees memory and 
other resources):
```
vagrant halt
```

If you want to totally destroy the VM, freeing disk space, run:
```
vagrant destroy
```


## Communication with the VM

To access the files on your computer from the VM, place them under the 
folder with the repository contents in them, and in the VM you can access 
them from under `/vagrant`.
 
To get started, SSH into the machine (not for Windows):
```
vagrant ssh
```

Alternatively (e.g. on Windows) get your favorite SSH client (e.g. [KiTTy]
(http://www.9bis.net/kitty/)) and use it to connect to the VM. You can get 
the connection information via:
```
vagrant ssh-config
```

The username and password are both: `vagrant`


## Using Jekyll on the VM

Jekyll will be installed globally on the system, meaning that you can just 
run `jekyll` anywhere you wish.

What you probably want to do is to be able to access the files from your 
computer, e.g. with your favorite editor, so you'll want to use the shared 
`/vargant` filesystem for that.

So, first thing you'll want to do after SSH-ing in, is switch to the shared 
filesystem:
```
cd /vagrant
```

Next, you should generate the website and tell Jekyll to start a web server
```
jekyll serve
```

The website will be available on your normal browser at http://172.22.2.2:4000/

That's pretty much it. Of course all Jekyll commands are available, so you 
can check the [Jekyll documentation](http://jekyllrb.com/docs/home/) for 
more information. 
