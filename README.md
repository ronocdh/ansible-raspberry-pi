# My Raspberry Pi Ansible Playbooks #

These playbooks will help you setup, provision, tinker and otherwise interfere with your [Raspberry Pi](http://www.raspberrypi.org/)!

Obviously to make use of these playbooks you will need to install [Ansible](http://ansible.com/), which is a commandline tool which enables simple provisioning of remote servers.  

Ansible doesn't require anything to be installed on your remote servers like similar tools such as [Puppet](http://puppetlabs.com/) and [Chef](http://www.getchef.com/chef/) do, as all that is needed for configurations is that you have key based [ssh](http://en.wikipedia.org/wiki/Secure_Shell) access to the remote server.

This makes it the perfect choice for when you just plugged a new [SD card](https://www.sdcard.org/) into your shiny Raspberry Pi.

Also, I think this tool might be used in some enterprise environments for like datacentres and junk but pfft… It was clearly designed for interfering with Raspberry Pi's!

## The Playbooks ##

This is a brief rundown of what each of the Playbooks and roles do:

* __new-raspberry__: This is the first playbook I run on any new Raspberry Pi.  It installs a bunch of standard software packages such as [git](http://git-scm.com/), configures a new hostname and installs the [excellent bash version](https://github.com/aurora/rmate) of [TextMate](http://macromates.com/)'s [rmate](https://github.com/textmate/rmate).

## Running the Playbooks ##

Inside each playbooks folder you will need to update the hosts file, you will need to replace the IP address in that file with the IP address of your Raspberry Pi or Pi's.

To run the playbooks, change into the correct folder and issue the following command in your Terminal:

        ansible-playbook -i hosts site.yml

 And that should be all you will need to run the playbook, if all goes well your Raspberry Pi will now be configured!