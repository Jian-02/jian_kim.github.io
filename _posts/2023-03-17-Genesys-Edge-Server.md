---
layout: post
title: Genesys Edge Server
subtitle: Middle server of Hardphone
categories: AICC, Daily
tags: [AICC, Daily]
---

## Genesys Edge Server
Genesys Edge Server is Middle server of Hardphone.  
Totally, same as Genesys Engage.  
  
### Functions  
1. SIP gateway  
2. SIP proxy  
3. MS/recording  
4. in/out bound call routing  
  
### WebRTC
Usually, use webRTC. It's based on web. not use SIP.  
  
## Queue vs Skills
Avaya skill : queue + skill  
IVR: connect to agent -> push 1 number button.  
At that time, send call to the queue.  
Different Engage's queue.  
  
* IVR --> queue(-> RP -> destination)  
Queue(=URS) IRD think alike.  
Inbound flow == IVR flow  

## AppFoundry
AppFoundry -> various 3rd party connect easy.  