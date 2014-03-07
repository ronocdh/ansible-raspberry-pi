#  Raspberry Pi Tor Enabled Wi-Fi Hotspot.

After installing ansible run the following command to find out which radio chipset you using:

``` bash discover Raspberry Pi radio chipset  
ansible YOUR-PI -a "lsusb"
```
This command will return a list of the USB device is connected to your Raspberry Pi, at the bottom of the list will usually be your Wi-Fi adapter and the response will look something like this:


    Bus 001 Device 002: ID 0424:9512 Standard Microsystems Corp.         
    Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub      
    Bus 001 Device 003: ID 0424:ec00 Standard Microsystems Corp.        
    Bus 001 Device 004: ID 0951:1665 Kingston Technology        
    Bus 001 Device 005: ID 0bda:8176 Realtek Semiconductor Corp. RTL8188CUS 802.11n WLAN Adapter

I've tested this setup using two different Wi-Fi adapters, if you get the output above telling you that you have the `RTL8188CUS 802.11n` adapter there are a number of changes you need to make.

However if the output of the command contains `Atheros Communications, Inc.AR9271 802.11n` then you should be able to run this playbook without any problems.[^1]

So, for those of you using the `RTL8188CUS` chipset you need to open the file `/roles/hotspot/vars/main.yml` and change the line: `chipset: nl80211` to `chipset: rtl871xdrv`

You then need to open the file `/roles/hotspot/tasks/main.yml`and find this section of code and comment it in:

    # - name: Workaround for IP address not persisting across reboots.
    #   copy: src=hostapd dest=/usr/sbin/hostapd
    #   sudo: yes



 [^1]:   Hopefully!