---
layout: post
title: Yerel Ağda Ipleri Görmek
category: linux
tags: fping ping
---


`fping` çok windows ile birlikte gelen `ping` programı gibi, bir konsol programıdır.

#### Kurulum

	sudo apt-get install fping

Yerel ağda olan ip'leri öğrenmek önce kendi ip'mizi öğreniyoruz:

	ifconfig
	eth0      Link encap:Ethernet  HWaddr 00:23:5a:f7:e4:0a  
	      UP BROADCAST MULTICAST  MTU:1500  Metric:1
	      RX packets:0 errors:0 dropped:0 overruns:0 frame:0
	      TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
	      collisions:0 txqueuelen:1000 
	      RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)
	      Interrupt:45 Base address:0x2000 

	lo        Link encap:Local Loopback  
	      inet addr:127.0.0.1  Mask:255.0.0.0
	      inet6 addr: ::1/128 Scope:Host
	      UP LOOPBACK RUNNING  MTU:16436  Metric:1
	      RX packets:3403 errors:0 dropped:0 overruns:0 frame:0
	      TX packets:3403 errors:0 dropped:0 overruns:0 carrier:0
	      collisions:0 txqueuelen:0 
	      RX bytes:530191 (530.1 KB)  TX bytes:530191 (530.1 KB)

	wlan0     Link encap:Ethernet  HWaddr 00:1e:65:05:50:68  
	      inet addr:192.168.2.3  Bcast:192.168.2.255  Mask:255.255.255.0
	      inet6 addr: fe80::21e:65ff:fe05:5068/64 Scope:Link
	      UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
	      RX packets:31891 errors:0 dropped:0 overruns:0 frame:0
	      TX packets:22148 errors:0 dropped:0 overruns:0 carrier:0
	      collisions:0 txqueuelen:1000 
	      RX bytes:22100624 (22.1 MB)  TX bytes:3247277 (3.2 MB)

İp'miz **192.168.2.x** olarak gözüküyor, o halde şu komutla yerel ağdaki ip'leri öğreniyoruz.

	fping -g 192.168.2.1/24 2> /dev/null | grep alive
