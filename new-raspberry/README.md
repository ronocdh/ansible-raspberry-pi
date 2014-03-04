# Provisioning a new Raspberry Pi #

This playbook does the following things:

1. Installs a bunch of common tools that I use on each new [Raspberry Pi](http://www.raspberrypi.org/)
2. Changes the hostname of the new Raspberry Pi to something I choose
3. Makes [zsh](http://www.zsh.org/) the default shell and installs [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
4. Installs [an awesome bash version of rmate](https://github.com/aurora/rmate), which is [TextMate](http://macromates.com/)'s remote text editor

You will need to decide what you would like your Raspberry Pi to be called, then open the file `roles/common/vars/main.yml` and change `hostname: YOUR-CHOICE-HERE`.

You will need to change the `zsh_theme` in the oh-my-zsh role to reflect the theme you would like to use.