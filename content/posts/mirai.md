---
title: "April 4, 2024 - Mirai: The IoT Botnet"
date: 2024-04-17T09:51:53-04:00
draft: false
---
# Analyzing Mirai: A Deep Dive into a Persistent Threat

In the realm of cybersecurity, few names evoke as much intrigue and concern as Mirai. For years, this resilient botnet has persisted, wreaking havoc across networks worldwide. Despite efforts to curb its influence, Mirai continues to evolve, perpetuating its status as the largest botnet in existence.

## Understanding Mirai Binaries

Mirai manifests in various binary forms, each tailored to exploit specific vulnerabilities across different architectures. Some of the notable binaries associated with Mirai include:

- `skid.mips`
- `skid.x86.elf`
- `skid.arm5`
- `skid.mpsl`
- `skid.arm`
- `skid.arm7`
- `skid.arm6`
- `faith.mips`
- `rebirth.x86`
- `IG.Sx86_64`
- `active.x86`
- `bot.x86_64`
- `FBI.x86_64`

## Identification of Mirai Actors

Among the myriad actors associated with Mirai, one notable entity is [AS151338] POLONETWORK-AS-AP, traced to the IP address 195.58.39.189 with the hostname 'rocock.gay'.

## Analysis of 'x86' Linux Commands

Upon scrutinizing one instance of Mirai, specifically the variant identified by the hash 10854ca81573b19d553b6c69ff95f73b, a series of 'x86' Linux commands were observed:

- `/bin/sh -c "sudo chown user \"/tmp/x86\.o\"  && chmod +x \"/tmp/x86\.o\" && DISPLAY=:0 sudo -i \"/tmp/x86\.o\" "`
- `sudo chown user /tmp/x86.o`
- `chown user /tmp/x86.o`
- `chmod +x /tmp/x86.o`
- `sudo -i /tmp/x86.o`
- `/tmp/x86.o`
- `/usr/bin/locale-check C.UTF-8`
- `-bash --login -c \/tmp\/x86\.o`
- `sh -c "cat /usr/etc/debuginfod/*\.urls 2>/dev/null"`
- `cat /usr/etc/debuginfod/*.urls`
- `tr \n " "`
- `mesg n`
- `/tmp/x86.o`

## Significance of Analysis

The significance of delving into Mirai's intricacies cannot be overstated. Understanding its propagation methods, payload delivery mechanisms, and evasion techniques is paramount in fortifying systems against its insidious attacks. By shedding light on the inner workings of Mirai, we empower defenders to stay one step ahead in the perpetual cat-and-mouse game of cybersecurity.

# References
- [Joe Sandbox Analysis](https://www.joesandbox.com/analysis/841196/0/executive)
- [Any.Run Report](https://any.run/report/a939592b7c4b82eb07bf7ad619a3ce9606ebc119d3d7091b193b1a625684d77b/86ae468b-5f9d-428e-90dc-4bb76bf42c40)
- [VirusTotal Analysis](https://www.virustotal.com/gui/file/713ca6a961a02c78b95decc18a01c69606d112c77ffc9f8629eb03ac39e7a22b/detection/f-713ca6a)
- [GreyNoise Blog - CVE-2024-3273 D-Link NAS RCE Exploited in the Wild](https://www.greynoise.io/blog/cve-2024-3273-d-link-nas-rce-exploited-in-the-wild)
