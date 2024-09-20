---

title: 'My experiences with Linux so far'
description: "Thinking of trying Linux? It's... something"
date: '06-08-2024'
id: 4
tags: 'Tech'

---

I've given Linux a few goes in the past but its only this attempt over the last month or so where i think everything is in a state that i'll be happy too stay on the platform for the foreseeable future. Id like to use this post to talk about my experience so far with Linux as a whole and how i think Linux is shaping up as a competitor to windows at this time.

## Unsuccessful Experiences
### Raspbian
My first experience with Linux was years ago with with [Raspbian](https://www.raspbian.org/) on a [Raspberry Pi Model B+ (1st gen)](https://www.raspberrypi.com/products/raspberry-pi-1-model-b-plus/), In case you haven't heard of them before Raspberry Pi's are extremely bare-bone computers that prioritise being very small and super inexpensive ($50-$100 AUD depending on the model)

With half a gigabyte of ram and a 0.7Ghz processor its hardly a surprise to find out that this device can barely handle a desktop operating system, performance was extremely slow and it was ultimately quite unpleasant to use.

I suspect that Raspbian is probably quite fine as a distribution of Linux but on this hardware it just doesn't work, maybe the newer raspberry pi models resolve this? Either way, I ended up switching to Raspbian Lite which has no desktop environment to just use the device as a simple server for various tasks and testing
### NixOS
Back earlier this year i heard about [NixOS](https://nixos.org/) which did catch my curiosity due to its unorthodox approach to system management. Rather than starting with a basic install and installing packages and changing configuration over time through normal methods. NixOS defines everything in a special nix configuration file. This means that, in theory, your configuration file is everything you need to build and load an exact copy of your setup. It's a very interesting idea but has quite a few caveats that hold it back:

- Finding the identifiers for configuration options is a slow process and changing these options in the desktop environment (ie: settings app) means your changes wont propagate to your configuration file, losing some of the benefits of using nix in the first place
- When making changes to your config, if anything is wrong when you try to build it, you'll get an incredibly hard to understand error where often he only solution is to systematically comment out lines of your config to find the offending lines
- As I'll talk about later, troubleshooting Linux issues is already much harder than windows. Using a niche Linux distribution with such a different way of doing things only compounds this problem

In case it was unclear, _NixOS is not a beginner friendly distribution_. Regardless, even with my inexperience, I had a lot of fun playing around with NixOS and learnt a lot more about using Linux as a whole. Something I especially liked is the reversibility of changes. Because of the nix config system, its super easy to go back to a previous version of your system if you change your settings in a way that ends up breaking things:  
For example. at one point i foolishly attempted to **downgrade** my systems kernel, to the surprise of no Linux veterans this but my machine into a state where it could not reach the desktop environment. On any other Linux distribution this would be really hard to recover from but on NixOS i could just pick the previous option on boot to get things back to a usable state

While it was fun, I ultimately switched back due to multiple issues i just didn't have the skills to fix

## The Current Attempt
This time I'm using Kubuntu on both my Laptop and my Desktop with Windows still on another partition available for if i really need it.

I chose this distro since it appears to be one of the most stable and well supported options available. Additionally i quite enjoy the Plasma KDE because of its clean modern design and its responsiveness. This is perhaps the biggest factor keeping me on Linux at the moment, Everything just feels faster without the overhead of Windows

### Other cool things
- no bloatware preinstalled on Linux - and if i don't need a system app, i can just remove it!
- Bluetooth support is way better, especially with controllers which was super painful on Windows since devices needed to removed and re-paired every time they went to sleep
- package management is way smoother for development purposes
- you can actually play pretty much any "Windows only" game through Proton with pretty much no issues - the only things that don't work at all are games with kernel level anti-cheat but I'm not really a fan of competitive/e-sports games so that's not an issue for me
- really nice customise-ability - super easy to set my "Start Menu" icon to be a little trans flag cat :3
![[Pasted image 20240806231836.png]]
### Random little things that are not so cool
- the compositor is weird - its the thing that makes windows fancy: Shadows, Transparent windows, animations across the system. Unfortunately i found it increased latency on everything just by a little bit, so it was quite noticeable in games. There are setups you can do to make it automatically switch off when you enter a game but its a hassle so I've just kept it off completely with no real issues (use Ctrl + Shift + F12 to toggle it in Kubuntu!)
- Various apps break when the computer returns from sleep mode: Discord shows a completely black screen and the graph view in obsidian breaks. At least both can be fixed by reloading
- I get screen tearing when using... Firefox? i think this has something to do with the compositor being disabled, its a bit annoying and something i haven't gotten around to fixing yet
- Animated/video wallpapers and lock screens are either super difficult or just impossible
- snaps are cringe and bad - still trying to get my Firefox to update, i should really just remove it and get the apt package...
- no native GitHub desktop for Linux, there's a couple Flatpaks you can try but i haven't had any luck with them, I've been liking [GittyUp](https://murmele.github.io/Gittyup/) as an alternative though

## The Current State of Linux as a competitor to Windows
With all the poor decisions Microsoft is making lately (More ads, AI Stuff, Bad windows 11 changes) there has been an increase in the amount of people looking to move away from Windows and the Microsoft ecosystem as a whole, but unfortunately there are currently compromises and challenges to overcome for someone to switch over to Linux, Here's a look at some of them:

### Nvidia GPU Support (and hardware in general)

One of the biggest issues with Linux at the moment is the lack of proper Nvidia support, Unfortunately Nvidia does not open source their drivers like their competitors and this means that the proprietary drivers they provide for Linux are often buggy

Case in point, my laptop is unable to sleep while it is running in Dedicated GPU Mode or Hybrid Mode. If i attempt to send it to sleep then it will never wake up and I have to force restart it.

Worst of all, because they are proprietary drivers, there's nothing the Linux community can do - if they were open source then contributors would be able to go i and fix the bugs

Hardware support in general is also a hassle since most manufacturers wont develop their products with linux in mind. When buying things like Headsets and Webcams you have to spend extra time researching to make sure that the device you're looking at will work with Linux

### Troubleshooting and Support

In my experience, Windows and Linux are equally buggy but its much easier to solve windows issues because about 3/4 of the world uses it and so you're almost always not the first person to run into it

However on Linux, you may very well have run into a unique bug but even if you haven't it could be much harder for you to fix because everyone Linux systems can be wildly different from one another and with so many different parts working together it can be very hard to pin down what exactly is causing the issue. This is why i feel like it is generally a good idea to go with a bigger, better supported distro with a large community hub tat can help out when these issues arise


## Thinking of switching to Linux
There's quite a bit to consider if you want to switch to Linux, and at the moment, there are definitely sacrifices you have to make but that can be reduced by doings things carefully and getting used to alternatives in advance

### Reasons to Switch
- You dislike Microsofts' tracking
- You don't want to switch to windows 11 (which is something you will kind of have to do when [security updates end for Windows 10 on 14th October 2025](https://www.microsoft.com/en-au/windows/end-of-support) - just over a year away)
- You want more customisation
- You wanna give Linux a go out of curiosity

### Reasons you should consider not switching
- You need your system to be reliable and don't have time to fix random bugs if when they pop up
- You don't currently have the time do do all the initial setup
- You haven't found alternative programs to what you need for your work

#### Alternative Programs 
A number of programs cannot be run on Linux, this is quite bad and likely a deal-breaker if you need them for your work. Luckily in most cases there are alternatives and often they are pretty good and far cheaper than their proprietary competitors

- Microsoft Office -> LibreOffice or Google Suite
	- LibreOffice is a complete office suite and my opinion is its "not bad", I've personally found it to be more comfortable to just use the google suite but i recommend you try LibreOffice, coming from Microsoft office i highly recommend you switch to the Ribbon toolbar so it feels more familiar
- Photoshop -> Krita, Gimp
	- Both a really nice image editors, Kirita is more artistic while gimp is more functional
- Premire Pro -> KDenLive
	- Solid video editor, does everything i need it to. However doesn't have quite as advanced effects as Premiere
- Github Desktop -> GittyUp
	- Weird that GitHub didn't make a native client but maybe they just think we'll use CLI? anyway GittyUp is a pretty nice alternative if you'd like a GUI like I do
	- For purely code based projects Visual Studio Code also has a great built in version control system!
- Minecraft Launcer -> Prism Launcher
	- Honestly its just better, even on Windows. its got inbuilt support for managing mod packs from Curseforge, Modrinth and Technic without down loading 3 additional launchers. Only downside is you cant run bedrock edition

All of these programs are available on windows, so if you'd like to start getting used to them before you switch, download them and give them a go!

### What to do if you want to try Linux
1. First of all, backup anything you value. Sometimes installs go wrong and a drive can be corrupted, its rare but lets be careful
2. I recommend you also install Linux in an additional partition since this will mean you can switch back to windows if things aren't working out. Honestly i recommend this even if you're switching between Linux distros too - Once you're happy and things are stable then you can delete windows or your previous distro

## System corruption
Between the time i finished writing and editing this post i decided I wanted to expand the partition I had Linux installed on. The steps for this are fairly simple: Boot into a live media USB, shrink the windows partition, expand the Linux partition. 

What i did not realise was how touchy the system was while this process was happening. When i got bored i started playing around with the colour scheme settings, just basic changes. Unfortunately this caused the partition manger to crash halfway through a move operation, corrupting my Linux drive.

With the help of a friend, I was able to recover the partition with `fsck.ext4` so i could get the small amount of files i store locally of the partition but i ended up having to completely reinstall Kubuntu which was quite the hassle.

Its a shame that this kind of instability exists and could potentially ruin a less experienced user who stores the bulk of their files locally, for a lot of people there needs to be no risk of this happening for them to be comfortable to switch

## Final thoughts
Please dual boot so you have something to go back to if its not working, and keep backups in-case something goes really wrong.

Otherwise, good luck! 💜

---

## Update 20/9/2024
Ive decided to switch my desktop computer back to windows 😔, Unfortuantely its was just too stressful for me to keep ontop of linux maintenance in addition to all of my other commitments.

I've kept it on my laptop for now because it is genuinly better there, I get 2-3 more hours compared to windows which is big considering tis never had particularly good battery life. On my desktop it only caused issues and (minor) performance losses...

At some point I hope to return~ When I was in a good headspace where I could deal with linux issues it was alot of fun, and i really dont want to be forced onto windows 11 when 10 is discontinued.