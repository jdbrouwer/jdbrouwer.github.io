---
layout: post
title: Writing a custom sensor for PRTG.  
---

So, i'm finally able to write another post, Sadly i've been very busy with exams and the like so i haven't been able to write much documentation and not being able to expand this blog at all. Hopefully that will change soon!

In this post we are going to create a custom sensor in powershell for PRTG. If you are not familair with powershell i suggest you read the excellent book titled  
["Powershell in a month worth of lunches"](http://www.amazon.com/Learn-Windows-PowerShell-Month-Lunches/dp/1617290211).

So, the first thing we must understand is that PRTG reads its sensor data from a custom XML Structure which looks like this: 

```XML
"<prtg>"
       "<result>"
         "<channel>ChannelName</channel>"
         "<value>ExampleValue</value>"
       "</result>"
"</prtg>"
```
in PRTG channels are the smallest "object" to store data in. Channels are the thing that contain actual monitoring values. Channels are grouped in a sensor. As we are creating a custom sensor with a script, we ourselves can define what data is contained in the channel and how it is used. 

Take an example at this Powershell code:

```Powershell

$pathcount = (Get-ChildItem -Path D:\).Count

#returning PRTG XML data
"<prtg>"
       "<result>"
       "<channel>Amount of files in D: Folder:</channel>"
       "<value>$pathcount</value>"
       "</result>"
"</prtg>"



``` 

This will get all folders and files under the D: drive, count them and then return that data to the PRTG sensor by using the XML format.


In the next part we will do something more complex and I will show you how to get actually use the script inside PRTG. 

