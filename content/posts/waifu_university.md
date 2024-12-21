---
title: "Xintra APT Emulation Lab - Waifu University"
subtitle: "some lab notes"
date: 2024-12-21T01:45:48+02:00
lastmod: 2024-12-21T02:45:48+02:00
draft: true
description: "Lab writeup"
author: "0x61616161"
tags: [ "apt", "notes", "xintra"]
categories: ["notes", "xintra"]
---

# Xintra APT Emulation Lab - Waifu University

https://www.xintra.org/dashboard

## Lab setup
### LAB DESCRIPTION
This is an emulation of Alphv/BlackCat ransomware group. This lab is designed to test your incident response and detection capabilities when faced with a ransomware breach with techniques including (but not limited to):

* VPN compromise
* BlackCat ransomware deployment
* Cloud credential compromise
* Local administrator privilege escalation
* C2 deployment

You are provided a Windows 11 VM prepped with all the tools, snapshots and evidence you will need to answer these questions. You are also granted access to an ELK instance with pre-parsed logs to conduct the analysis. Take a read of the scoping note to begin the investigation.

We have also provided for your convenience:

* Pre-parsed KAPE output

### SCOPING NOTE
(＞ω＜) ♡ Welcome to Waifu University ♡ (＞ω＜)

Waifu University's cyber team has called you after their IT teams reported a number of servers with files that aren't opening and have a strange extension.

On your scoping call, the victim also said they had identified a ransom note stating their data has been stolen. When asked about any earlier signs, the victim mentioned some strange, failed login activity early in March 2024 in their Entra ID, but wasn't of concern at the time...

Ransomware will typically avoid system files to not cause crashes in the system, which also happens to be where a lot of forensic evidence is! You have been provided triage images of the hosts and log exports from the relevant systems.

The Waifu University team took triage collections from the affected hosts using the account WAIFU\kscanlan6 at approximately 2024-03-07 05:00:00 UTC. Consider activity after this point related to the response.

![network_diagram.png](xintra/waifu_university/network_diagram.png)