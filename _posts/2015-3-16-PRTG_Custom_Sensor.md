---
layout: post
title: The advantage of PRTG custom sensors. 
---

One of the things that makes [PRTG](http://www.paessler.com/prtg) really awesome is the fact that it supports Custom sensors. Custom sensors are basicly executable programs you use to do "something". The program is then sending back data in the proper XML format that PRTG understands. With these custom sensors you are able to do about absolutely anything!.

A great language I found to use with custom sensors in PRTG is Powershell, mostly because:

+ A) I am able to actually write Powershell properly
+ B) Powershell integrates nicely into windows without any external tools.
+ C) Powershell is fast in a lot of things it does, a LOT faster then a lot of PRTG's own sensors. 

The performance issues are mostly noticable when using larger installations. I've noticed that PRTG's own sensors for a lot of things. (SQL, Exchange connectors, Active Directory) come close to a grinding halt when the system is under some workload. (1000+ sensors).

The main advantage of custom sensors is that it allows PRTG to read out data from other sources then defined by the included sensors by default. 
In the next post, I will show  you how to write a custom sensor for PRTG and use it to read something from a database. 






