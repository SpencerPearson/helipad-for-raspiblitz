# helipad-for-raspiblitz
Install Podcast Index's [Helipad app](https://github.com/Podcastindex-org/helipad) on your [Raspiblitz](https://github.com/rootzoll/raspiblitz/) node!

## A WORK IN PROGRESS
This install script is part of a larger project to make Helipad an installable service in Raspiblitz's "Additional Services" menu. For now, since podcasters are eager to have a way to read their boostagrams ASAP, we have decided to release this current stable version of the app. Below we will walk you through the setup step-by-step, but these steps should become simpler over time and the front-end interface you see in the browser will also improve.

## This README is written for complete beginners
There are many ways to execute this simple shell script and install Helipad. If you're a Raspiblitz user you may already be familiar with the steps. Just get the shell script onto your Raspiblitz (preferably in /home/admin/configs.scripts, although it should work from anywhere) and execute it. However, this guide is intended to be exhaustive and makes no assumptions as to user's prior knowledge.

## 1. Navigate to your Raspiblitz cli

To connect to your Raspiblitz, run the following command in a terminal on the same local network:
`ssh admin@<Raspiblitz.Local.IP.Address>`
You will be asked for your Raspiblitz Password A

Once you're in, you'll be greeted by the Raspiblitz main menu:
![Raspiblitz main menu](https://github.com/rootzoll/raspiblitz/raw/v1.7/pictures/ssh5-mainmenu.png)
We'll need to exit the main menu and enter the cli. To do this, select <Exit> or ctrl C

## 2. Add the Helipad install script to your config.scripts directory
In Raspiblitz, all the install scripts for special tools live in the config.scripts directory. We'll add our bonus.helipad.sh file to that directory like this:
