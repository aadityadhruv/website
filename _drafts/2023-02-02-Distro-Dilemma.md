---
layout: post
title:  "Distro Dilemma"
---
Choosing a Linux Distro is hard, and sticking to one is even harder. I hopped between several distros before landing on Fedora Linux. Many of the distros I tried made me feel that it would be the final distro I would stick to, but in the end my distro hopping ended with Fedora. 


### About Distrohopping

For the uninitiated, Linux itself isn't an operating system, it's just the kernel. When the kernel is bundled with other packages and programs, you get a Linux Distribution, or a Distro. Since the kernel is open source, and so are a lot of the packages, people and communities are free to customize and ship their own flavors of Linux as their Distros. Most people think of Ubuntu when they hear about Linux, but Ubuntu is just a Distro. 


With so many options to choose from, a Linux user always ends up going through a Distrohopping phase. They try a distro, use it for a while, then nuke the partition and start all over again with another distro. This cycle is repeated several times, until the user finds the distro they are the most comfortable with. 

However, a lot of Distrohoppers find that they aren't satisfied with ANY distro. This leads to a never ending cycle of installing and nuking distros on their machine, without actually doing any work. 


I had this problem for the longest time, until I had to mentally tell myself to stop hopping and choose a distro once and for all.



### Starting Distrohopping


Before my active hopping, I had only extensively used Ubuntu, both in a VM and as a part of WSL. I ended up choosing Arch Linux as my first dive into Distrohopping. 

#### Arch Linux

Arch Linux was a huge learning step for me. With its manual installation process to its "build it yourself" philosophy, there were a lot of things to learn. And it was a lot of fun learning these things. I have to credit Arch Linux for teaching me a lot of Linux skills. The Arch Wiki was the biggest learning resource here, since there is an article on pretty much every topic or problem.


Arch was great during the time I used it. Quick updates, rolling release, and great support. 

I initially started with the KDE Desktop environment, then switched to GNOME. After finding out about r/unixporn, I had no choice but to end up customizing my distro with tiling window managers, widgets and status bars. I initially used i3, but ended up on BSPWM for the longest time. This setup was working great for me. I had a minimalistic setup and everything was just a keyboard stroke away. 

In fact, I still use that setup (I'll come to that later), and the dotfiles are available on my GitHub. 


#### From Arch to Others


While Arch was great, I was having problems with the Distro. I was getting tired of living on the bleeding edge. Frequent updates got tiring, minimalism led to connectivity issues, and I frankly was spending more time customizing my desktop than actually using it. 

This led me to try out various other Distros. I'll just gloss over some of the many distros I used, since the specifics aren't important. 

Here is a whole list of Distros I tried and a little short note about it:
- Elementary - Interesting design, but too much extra stuff for me
- EndeavourOS - Fun twist on Arch, was a great experience, but had the same shortcomings as Arch
- Ubuntu - Decent Distro, but I despise the direction Canonical is headed towards
- Pop!_OS - Very polished distro, great HDR support, but Ubuntu based dissuaded me
- Garuda - Too much focus on "gaming", unnecessary animations and "bloat"
- Manjaro - Buggy to install, same shortcomings as Arch, and https://manjarno.snorlax.sh/
- NixOS - Very cool concept with a config file install, but I didn't find it comfortable to use on a day to day basis
- OpenSUSE Tumbleweed - While I didn't like it at first, I grew to like it, though `zypper` wasn't my most favorite package manager
- Solus - While a pretty distro, it seemed like there were a lot of development issues to warrant using the distro



#### Void Linux replaces Arch

From hop to hop, I ended up on Void Linux, which was a distro I hadn't heard of. It used `runit` as its init system, which was also new to me. I gave Void a shot and felt the same excitement as Arch. It was the same enjoyment of customizing a minimal distro, building it from scratch. Void also used much lower memory than Arch and was much faster to boot too. It was great. However, the shortcomings of Arch crept up, especially spending a large chunk of time customizing my distro rather than working in it. 


#### Fedora Finale

After a couple of months, I got tired with Void, and went to Fedora. I had actually used it before, but I didn't find it any special. Coming back to it, I realized that it worked really well for me. 

Firstly, the Fedora philosophy aligned with ideas. 

1. Commitment to being open source
2. Using Libre software
3. Stable and fast updates

Fedora also had a pretty clean GNOME setup and had the packages I needed pre-installed. While I was initially against "bloat", I realized that as long as my system works, I can do all my work productively. 

Fedora also worked pretty well with my Steam library, so gaming was good to go. 

Fedora was also really polished, being a Red Hat derivative, and also the upstream source for RHEL. 


After using Fedora for a couple of months, I didn't find the urge to Distrohop at all. I was getting all my work done, I didn't need the minimalistic work environment or cut down on bloat. Fedora was just great. 

With this, I ended up sticking to Fedora, till today! The only qualm I have with Fedora is the slow package manager, but it isn't like I need to update anything daily so it's just a minor gripe. 




#### Asahi Linux Stuff

While the above saga covers my Distrohopping journey, I do use a different distro on my M1 Mac - Asashi Linux. This runs Arch, and since I am familiar with it, it isn't a problem. Well, technically I can boot up Fedora on the M1 with the Asahi bootloader, but that is a lot of work which I'm currently not willing to undertake. The default Arch Asahi works just fine. Once the Asahi patches are upstreamed to the kernel, I'll probably get Fedora up and running on the M1, but for now, this will do!
