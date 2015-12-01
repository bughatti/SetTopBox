# SetTopBox
Addons and instructions for a cut the cord set top box

*****Below Instructions are a work in progress, do not use until marked complete *****

Guide to setting up a set top box with pseudo tv and kodi

If Kodi is already installed, start with a clean install.  Uninstall all aspects of Kodi and make sure to clean up the folders.  

We are going to set this up for multi use.
Before getting Kodi setup, lets make sure we have a shared NAS setup with all of our content we want to stream.  I personally use XPenology with 16TB of storage space.  I have my 5 folders setup and shared Movies/Music/TV/Anime/Cartoons.  I have made sure to map all of these drives on my Windows machine (Win 10)

After we know we have our folder structure setup correctly for all of our content the next step is to get our OTA channels for whatever device we are using.  I currently use a Hauppage 950 with the Nextpvr client running on a machine.  I have already gone through setting that up following this guide https://www.youtube.com/watch?v=rMk6BiWCRXM but make sure to stop after scanning channels and verifying you have live tv in the nextpvr app.

After doing some research, I have been told that using Emby as a backend manager for Kodi is the best way to pause content on 1 device and start it back up on another device.  So lets get Emby setup.  Install Emby somewhere accessible inside your network and get your media folders setup.
I followed this guide https://www.youtube.com/watch?v=P_KZHvm_2vc and again, make sure to stop after you add your media librarys.   Mine was pretty big so I let Emby scan almost 8TB of content so I would not have issues just in case.  I also installed the nextpvr app inside Emby and made sure that was operational.


After we have verified NextPVR live channels, made sure Emby has scanned all of our content and setup a recording shared folder we need to sign up for a few sites.

Lets head over to USTVnow and signup for the free plan.  It will allow you to signup with google or facebook, I used the email box because Kodi does not have a way to use google or facebook when setting up ustvnow, it is just easier than trying to figure out.  Next, lets head over to Trakt.tv and signup.  Same thing, lets use email address instead of google or facebook.

Time to get Kodi setup.  I run them on Win 10 boxes in my house, I also just purchased a Intel NUC I3 with 8gb of ram and an SSD.  This may not be viable for most as it is a very expensive setup.  I plan to have 3 of them running in my house running on a LAN cable, most people may like WIFI but as an IT person, I can promise your experiance over WIFI will not be as good as LAN.  I also run Emby on a linux VM and Couchpotato/Sickrage/headphones on a seperate linux vm.  I have all this because I plan to cut the cord soon and saving 120 a month, you can easily pay for a Intel NUC in 3 months savings.

So during my rambling, you should have gotten Kodi installed on whatever platform you plan to use.  First things first.  I like to get a few small but major addons installed first.  
Lets get fusion installed https://seo-michael.co.uk/how-to-install-fusion-for-xbmc/ so we can get the addon installer.  
Now lets get SuperRepo installed https://seo-michael.co.uk/how-to-install-superrepo-for-xbmc/ and get the Isengard all repository installed.  
Now lets get the Emby kodi addon installed https://emby.media/downloads/emby-for-kodi/ download the repo and install from zip, then go to install from repo and select program add ons and install emby server, configure it with the IP of the emby server you setup and the username.  Once connected it will start to scan media, let it scan even if it takes a while.

Now lest go into the settings of Kodi and enable TV, this will scan for a backend PVR and will fail because it is not setup.  When it asks to set one up click ok and select NextPVR, click configure and set the IP to the nextpvr client we setup earlier.  Now click on enable for nextpvr

Install Skin Skin Confluence Hybrid Helix

Now lets go to programs and install some addons before we get Pseudo TV setup.
Open Addon Installer, click on Featured Addons then click on USTVnow Live and install.  Now we want to search for a few others.  Under addon installer click on search and type the below in, 1 at a time exactly as I have them

-plugin.program.super.favourites

-plugin.video.youtube

-plugin.video.vimeo

-for vevo_tv you need to download this repo and install from repo VEVO TV https://code.google.com/p/addonscriptorde-beta-repo/downloads/detail?name=repository.addonscriptorde-beta.zip&can=2&q=

-for my_music_tv same as above, use the testing repo and install MY MUSIC TV

-playonbrowser install this zip https://github.com/sytone/plugin.video.playonbrowser 

-trakt viewer

-artwork downloader mp

now lets exit Kodi and open it back up.  Head over to Programs and click on USTVnow Live and it will ask you to put in your log in credentials and select your plan, hit ok

now lets go back to addons and install from zip this file https://github.com/Lunatixz/XBMC_Addons/raw/master/zips/repository.lunatixz/repository.lunatixz-1.0.zip then go back to install from repo and select Lunatixz repo then porgram addons then pseudo tv live

now before we open pseudo tv we need to set some configurations.  First, if you have a Synology or a like device we will need to set some path substitutions in Emby for our content.  Since I have Ubuntu running Emby I mapped each content folder as a smb share in etc/fstab but that will probably not be playable so I went into the path substitutions tab of emby under library and set for example from: /volume1/anime/anime to: smb://ipaddress/anime/anime  Do this for all folders in Emby Library

