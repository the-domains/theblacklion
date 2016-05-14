---
inFeed: true
hasPage: true
inNav: false
inLanguage: null
keywords: []
description: Last week I ran into an issue when I wanted to install PowerDirector 13 on my PC. The setup program aborted with a message that I need Windows Media Player 9 or above although I have Windows Media Player 12 installed on my Windows 10.
datePublished: '2016-05-14T07:46:31.571Z'
dateModified: '2016-05-14T07:46:27.245Z'
title: Cyberlink PowerDirector 13 installation missing Windows Media Player issue workaround
author: []
sourcePath: _posts/2016-05-09-cyberlink-powerdirector-13-installation-missing-windows-medi.md
authors: []
publisher:
  name: null
  domain: null
  url: null
  favicon: null
starred: false
url: cyberlink-powerdirector-13-installation-missing-windows-medi/index.html
_type: Article

---
# Cyberlink PowerDirector 13 installation missing Windows Media Player issue workaround

Last week I ran into an issue when I wanted to install PowerDirector 13 on my PC. The setup program aborted with a message that I need Windows Media Player 9 or above although I have Windows Media Player 12 installed on my Windows 10\.

With a little googling I found out that this issue also appears on older Windows versions but seems to be related to having a a newer Windows Media Player version. The problem is in the installer and you can get a fixed installer from Cyberlink, but you have to contact support for that.

I found a workaround by changing two registry values temporarily. Actually, I think only one needs to be changed, but I did not play around to figure out all the details. This is how it works:

1) Open regedit

2) Go to HKEY\_LOCAL\_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\App Paths\\wmplayer.exe

3) You should see something like this - I used a German Windows, so depending on your language it will be slightly different for you:
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/4a01a37e-675a-470a-8389-d64c3888213b.png)

I think the PowerDirector installer cannot handle the quotes but maybe it also cannot handle the ProgramFiles(x86) variable. Also it is probably enough to change the value of (Standard) - (Default) in English. But what I did and worked is this:

4) To undo the changes after installing PowerDirector 13, it is good to export the current entries. You find the export function by right-clicking on wmplayer.exe on the tree in the left.

5) Then change both values to use hard coded absolute paths and no quotes. Most likely you installed Windows and your programs on C: so it should look like this:
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/5dddf500-54d4-4ad4-ba90-6cbb9a0f5f7d.png)

6) Then run the PowerDirector 13 installer again and it should work just fine. 

7) After the installation is done, just undo the registry changes by double-clicking the previously exported reg-file. It should ask you for confirmation and if you proceed, your registry entries should be back to normal. Or you can just do it by hand.