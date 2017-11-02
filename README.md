# CyberSecurity_Week9_Assignment
Honeypots

# Project 9 - Honeypot

Time spent: **4** hours spent in total

> Objective: Setup a honeypot and intercept some attempted attacks in the wild.

## Overview

In this assignment, you will stand up a basic honeypot and demonstrate its effectiveness at detecting and/or collecting data about an attack. Guided instructions for doing this using specific software are provided below, but you are free to take any approach you wish that demonstrates the following basic principles:

Successful configuration and deployment of a network-accessible honeypot server with two primary features:
 - An attack surface that is vulnerable or exposed in some way to network-based attacks
 - A network security feature such as an IDS configured to detect and log such attacks

Illustration of at least one attack against the honeypot that can be detected or logged in a way that captures information about the attack or the attacker

## Experiment write-up

Mama always said you catch more flies with honey than vinegar, though I don't think she had the internet in mind when she said it. I set up 5 different VM's with different honeypot software.
Immediately upon setting up my first Dionaea with HTTP server I was registering attack after attack

Below is a more concise version of the required details listed on the assignment page

### Honey pots deployed (All on Ubuntu 14.04)

 - Dionaea with HTTP(mhn-honeypot-1)
 - Snort (mhn-honeypot-2)
 - ElasticHoney (mhn-honeypot-3)
 - Dionaea (mhn-honeypot-5)
 - Kippo (mhn-honeypot-6)
 
### Issues

I encountered some initial difficulty setting up the VM's since I was attempting to use Windows Powershell instead of linux and the commands were slightly different.
There was also initial difficulty getting into the admin VM, since trying to go directly to the IP address would take me to the https version, when I needed the http version.

### Summary of data

Attacks (after ~16 hours up time):

 - Dionaea with HTTP(mhn-honeypot-1) = 9219
 - Snort (mhn-honeypot-2) = 463
 - ElasticHoney (mhn-honeypot-3) = 2
 - Dionaea (mhn-honeypot-5) = 5300
 - Kippo (mhn-honeypot-6) = 216
 
Top 5 Attack signatures, Snort:

 - ET DROP Dshield Block Listed Source group 1 (124 times)
 - ET SCAN Sipvicious User-Agent Detected (friendly-scanner) (29 times)
 - ET CINS Active Threat Intelligence Poor Reputation IP TCP group 74 (25 times)
 - ET SCAN Sipvicious Scan (25 times)
 - ET CINS Active Threat Intelligence Poor Reputation IP UDP group 53 (15 times)
 
Kippo Results:

 - Top Users: <img src='https://i.imgur.com/yuDom5R.jpg' title='Top usernames' width='' alt='Top usernames' />
 - Top Passwords: <img src='https://i.imgur.com/XpTh8ss.jpg' title='Top Passwords' width='' alt='Top Passwords' />
 - Top Users and Passwords: <img src='https://i.imgur.com/Sbu8DuZ.jpg' title='Top Usernames and Passwords' width='' alt='Top Usernames and Passwords' />
 - Top Attackers: <img src='https://i.imgur.com/teSIcXq.jpg' title='Top Attackers' width='' alt='Top Attackers' />
 
Malware Samples:

 - I was unable to find any malware samples on any of the machines.
 
### Unresolved questions raised by the data collected:

 - None