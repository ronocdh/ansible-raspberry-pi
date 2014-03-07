# New Raspberry Pi #

I'm new to using [Ansible](http://ansible.com/) so please forgive any basic errors, but if you do need any help just get interaction and I'll be happy to help!

This playbook does the following things:

1. Installs a bunch of common tools that I use on every new [Raspberry Pi][1].
2. Changes the hostname of the new Raspberry Pi from its default of `raspberrypi` to something of our choosing.
3. Makes [zsh][2] the default shell and installs [oh-my-zsh][3],  which makes [zsh][2] much more awesomer.  And junk.
4. Installs [an awesome bash version of rmate][4], which enables you to use your local copy of [TextMate][5] whilst editing a file on a remote server.

## Running the Playbooks ##

### Copying your SSH Keys to the Raspberry Pi ###

Before you can run any of your playbooks you should first copy over your ssh keys to your Raspberry Pi with: 

        ssh-copy-id pi@your-raspberry-pi-ip-address

### Choosing your Hostname ###

Once you've decided what your new Raspberry Pi is going to be called, navigate to the file `roles/common/vars/main.yml` and change the line: `hostname: raspberrypi` to reflect your choice.

### Choosing your Oh-My-ZSH Theme ###

If you would like to use a different theme than the default in oh-my-zsh, navigate to the file `roles/oh/my-zsh/vars/main.yml` and replace the name philips in the line `zsh_theme: philips` to reflect the name of the theme you would like to use.

If you would like to get an idea of some of the themes available, you can look at the many themes available me [oh-my-zsh wiki][6].

You will need to update the `hosts` file so that it has the IP address of your Raspberry Pi, rather than the IP address of my Raspberry Pi!

Once you've made these changes, you can run the playbooks by using the following command:

        ansible-playbook -i hosts site.yml


And that's all I normally do to get a completely blank Raspberry Pi into a working, and somewhat usable state.

[1]: http://www.raspberrypi.org/
[2]: http://www.zsh.org/
[3]: https://github.com/robbyrussell/oh-my-zsh
[4]: https://github.com/aurora/rmate
[5]: http://macromates.com/
[6]: https://github.com/robbyrussell/oh-my-zsh/wiki/Themes