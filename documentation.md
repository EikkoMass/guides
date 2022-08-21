# Turning on the computer with Alexa (Linux Guide)

This repository has the objective to guide how to initialize a linux computer with Alexa.

To start with the tests, was used the video: https://www.youtube.com/watch?v=rYfXbCR3HFQ&ab_channel=AdrianM%C3%BCller (but the video shows how to do on Windows).

______________________________________________

**\[1]** **Config PCI-E on BIOS:**

To initialize the computer with Alexa, needs to enable the 'Magic Packet' config, also named as 'Wake-on-LAN' (WOL) on some cases, to use that you will need to enable remote access to your pc by network.

The motherboard tested was 'ASUS PRIME B450M-GAMING II', who will be used to follow the steps.

When you turn on the computer, open the BIOS configuration (DEL // F2 // Etc), go to:

*Advanced Settings >> Advanced >> APM Configuration >> Power On By PCI-E*

if this option has turned off, just enable it and save. 

______________________________________________

**\[2]** **Install ethtool:**

**sudo apt install ethtool**

______________________________________________

**\[3]** **Config Wake-On-LAN:**
>https://wiki.archlinux.org/title/Wake-on-LAN


>**your-network-name:**
>Name that your computer define to network connection, example:
>**enp2s0**, **enp5n0**, etc...

>How check if your 'Wake-On' config is enabled: 
>**ethtool *your-network-name* | grep Wake-on**


Enable the 'Magic Packet' as a remote command receiver

**ethtool -s *your-network-name* wol g**


**\[3.1]** **Make the 'Magic Packet' config persistent:**

Will be necessary to create a new file named as **50-wired.link**:

**sudo nano /etc/systemd/network/50-wired.link**


>You can identify your MAC address with the command: 
>
>**ifconfig** your-network-name **| grep -o -E '([[:xdigit:]]{1,2}:){5}[[:xdigit:]]{1,2}'**

paste the config below on file and add your MAC address:

>\[Match]
>
>MACAddress=*your:mac:address:here*
>
>
>\[Link]
>
>NamePolicy=kernel database onboard slot path
>
>MACAddressPolicy=persistent
>
>WakeOnLan=magic

...and restart the computer.

______________________________________________

**\[4] Set the computer on Wake-on-LAN website**

Access the website below:

>https://www.wolskill.com/

Login and sync your Amazon Account.

Next that you scroll down the website to 'Device Panel', it's where you will add the **Name** and **MAC**.

The **Name** will be the command name used by Alexa identify when turn on the device.


example:

**Name:** PC

**Command will be used:** *Alexa, start **PC**!*


The **MAC** will be the device's MAC Address, the same address used before (*your:mac:address:here*).

save the command with the device name.

______________________________________________

**\[5] Install WOL Skill on your Alexa App**

Open the Alexa App on your smartphone and add the Wake-on-LAN (WOL) Skill, Alexa will search devices connected by WOL and sync.