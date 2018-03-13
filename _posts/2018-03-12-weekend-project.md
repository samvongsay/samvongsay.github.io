---
layout: post 
title: Weekend Project 
permalink: /blog/
---

First a background. Long story short, my dad is cheap and our family does not do a lot of printing. I have a printer that has no network capabilities. 
So both ethernet and wireless connections would not work. This got me thinking about how can I connect the printer to my desktop in another room. 
My idea is to connect another computer with network capabilities to the printer. Therefore, my desktop is connected to the router which also connects
the computer with the printer. 

Coincidently, my family has gone through a few personal built desktops which are not being used since they are well dated. On a hardware level, I had everything.

Checklist:
<ul>
    <li>Computer</li>
    <li>Printer</li>
    <li>Router</li>
</ul>

My first problem I ran into is installing a new operating system. All my computers that I use are Linux distributions (Fedora) and I liked the "simplicity."
One of the computer doesn't allow me to boot into the BIOS so I can change the boot order. This prevented me from running Fedora on my usb drive which was my
method of installation. My conjecture is that it does not allow USB input on boot which is how my keyboard is connected. I think if I had a PS/2 adapter, this
would have worked out. However, I have long since thrown it out because it is 2018 and who uses PS/2? Instead, I sucessfully installed Fedora on another computer.  

Since my goal is to only turning on the computer in order to use its printing services, I would need to keep it on suspend/hibernate mode. I cannot afford to
keep it on all day everyday because my printing services are rare at best and my family isn't rich. My solution is to send a network signal to the computer so it 
can wake up. This is where I came to a giant wall. The hardware is so old, it does not have a "Wake-On-Lan" option on the BIOS which is needed for my plan to work.
After searching for hours, I learned this:

<b>It is impossible to send packets to a computer that does not have Wake-On-Lan enabled.</b>

Thus, my weekend was pretty much wasted. 

What did I learn through this? 
<ul>
    <li>Always do research first before starting</li>
    <li>It never hurts to keep things even if you do not need it at the moment</li>
</ul>

<b>Afterthought</b>
<br>
I might revisit this project sometime later once I have calmed down. Although, I do not think I will be using it for printing services since I plan to invest in 
a printer that has network capabilities. Instead I will use it as a backup storage so I can do daily/weekly backups. I found out that the computer could be 
powered on by the system time so I can set a certain time that I am not using it to run a backup program. 

There are a few solutions I have not tried. One is related to the "Power on by Ring" feature in the BIOS. It wakes the computer when a ring occurs. You may remember
it as a phone call which would disconnect you from the internet along with an excruciating painful sound. Or if you were not part of this era, a fax also does this.
My plan is to get a microprocessors like an Arduino or a Raspberry Pi and mimic the signal when I send a packet to it. Another option is to use the "Power on by PME#"
feature on the BIOS. I would need to do more research on how to generate a signal to trigger the event.

Overall, I feel like I wasted an entire weekend. I did learn many things from the hardware aspect and the Linux environment. I hope for better things to run smoothly
in the future.
