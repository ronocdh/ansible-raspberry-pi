# Provisioning a new Raspberry Pi #

This playbook does the following things:

1. Installs a bunch of common tools that I use on each new [Raspberry Pi](http://www.raspberrypi.org/)
2. Changes the hostname of the new Raspberry Pi to something I choose
3. Makes [zsh](http://www.zsh.org/) the default shell and installs [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
4. Installs [an awesome bash version of rmate](https://github.com/aurora/rmate), which is [TextMate](http://macromates.com/)'s remote text editor

## Running the Playbooks ##

Once you've decided what your new Raspberry Pi is going to be called, navigate to the file `roles/common/vars/main.yml` and change the line: `hostname: YOUR-CHOICE-HERE` to reflect your choice.

If you would like to use a different theme than the default in oh-my-zsh, navigate to the file `roles/oh/my-zsh/vars/main.yml` and replace the line `zsh_theme: philips` to reflect the name of the theme you would like to use.

You will need to update the `hosts` file so that it has the IP address of your Raspberry Pi, rather than the IP address of my Raspberry Pi!

Once you've made these changes, you can run the playbooks by using the following command:

        ansible-playbook -i hosts site.yml

 And that should be all you will need to have your Raspberry Pi setup in a basic working state.