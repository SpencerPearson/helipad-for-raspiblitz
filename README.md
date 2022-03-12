# helipad-for-raspiblitz
Install Podcast Index's [Helipad app](https://github.com/Podcastindex-org/helipad) on your [Raspiblitz](https://github.com/rootzoll/raspiblitz/) node!

## UPDATED AS OF RASPIBLITZ v1.7.2:
This install script was part of a larger project to make Helipad an installable service in Raspiblitz's "Additional Services" menu. That particular mission has been accomplished, and now you can install Helipad directly from the UI. For those still interested in installing Raspiblitz manually, below we will walk you through the setup step-by-step.

## This README is written for complete beginners
There are many ways to execute this simple shell script and install Helipad. If you're a Raspiblitz user or familiar with Debian in general you may already be comfortable with the process. Just get the shell script onto your Raspiblitz (preferably in /home/admin/configs.scripts, although it should work from anywhere) and execute it. At the risk of being redundant, this guide is written to be exhaustive and makes no assumptions as to user's prior knowledge.

## 1. Navigate to your Raspiblitz command line interface

To connect to your Raspiblitz, run the following command in a terminal on the same local network:

`ssh admin@<Raspiblitz.Local.IP.Address>`

You will be asked for your Raspiblitz Password A

Once you're in, you'll be greeted by the Raspiblitz main menu:

![Raspiblitz main menu](https://github.com/rootzoll/raspiblitz/raw/v1.7/pictures/ssh5-mainmenu.png)

We'll need to exit the main menu and enter the cli. To do this, select < Exit > or ctrl C

## 2. Add the Helipad install script to your config.scripts directory
In Raspiblitz, all the install scripts for special tools live in the config.scripts directory. We'll cd to config.scripts and add our bonus.helipad.sh file to that directory using wget like this:

`cd config.scripts`

`wget https://raw.githubusercontent.com/SpencerPearson/helipad-for-raspiblitz/master/bonus.helipad.sh`

We'll need to make sure we can execute this script:

`chmod +x bonus.helipad.sh`

if you want to make sure the script is ready, call:

`ls -l`

you should see your bonus.helipad.sh script in green with -rwxr-xr-x as the permissions:

![config.scripts directory](https://i.ibb.co/dLmSxdp/Screenshot-2021-12-16-160543.png)

## 3. Install Helipad
Go back to your root directory and call the Helipad script passing the "on" option:

`cd ~`

`./config.scripts/bonus.helipad.sh on`

Now sit back and wait, the script will now start installing Helipad!

## 4. Pull up Helipad in your browser

For now, you'll still need to be connected to the local network in order to see your Boostagrams. Navigate to your Raspiblitz's local IP at port 2112. 

![Helipad working in the browser](https://i.ibb.co/5B5J3bh/Screenshot-2021-12-16-163651.png)

If you're having trouble finding the specific web address you can call the menu function of the helipad script from the root directory like this:

`./config.scripts/bonus.helipad.sh menu`

This will display the HTTP address. HTTPS and TOR hidden service support will be coming soon!

Your Raspiblitz should be building a SQLite database of all your boost history, so you might have to wait for your database to finish building before the boosts are displayed.

## NOTES:

This script installs Helipad and sets it up to run constantly on your node as a systemd service. Helipad checks your node for invoices every 9 seconds and adds new boost acitivity to its database. This means once you have Helipad installed, you can open it from any browser on any device on your local network and see boosts land in real time.

Test it out! New boostagrams AND boosts should appear in 30 seconds or less. For podcasters with live shows, you can keep Helipad opened to listen for the "pew" sound as boosts come in.

For questions specific to the installation on a Raspiblitz, feel free to [open an issue](https://github.com/SpencerPearson/helipad-for-raspiblitz/issues) in this repository. For more info about the underlying Helipad code and its implementation on systems outside of Raspiblitz please see the [official Helipad repo](https://github.com/Podcastindex-org/helipad) from Podcast Index.
