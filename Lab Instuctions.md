# Incident Triage
# Lab Description: In this challenge, you will review a capture file sent to you by a Level One Security Operations Center (SOC) Analyst
In this lab you will perform the role of a Level Two Security Operations Center (SOC) Analyst, and your task in this lab is to investigate, analyze and determine if the network traffic forwarded to you for review from the Level One analyst should be escalated and assigned to the Computer Security Incident Response team for triage collection and incident response procedures.

A bit of background, the scenario here is that of an adversary that has been identified through threat intelligence and has targeted your organization. You are a SOC Level Two Analyst for Globomantics. The group that has targeted your organization is the infamous Dark Kitten group that represents a potential Advanced Persistent Threat (APT), but this has not been validated, and part of your experience here will be to explore the methods that have been deployed and determine is this actually a sophisticated attack from a high-level threat or not.

In this lab, you will use the Wireshark tool and analyze the static file, this is in line with the current scenario of being the Level Two analyst, the “live” and real time capture would have been done and should have been observed by the Level One analyst. Let’s get started with Intrusion Analysis and Incident Response! One caveat before we get started, the reality is you never know if you are right or wrong, we have to use the skills we have and experience to the best of our ability, sometimes it works and sometimes it does not. Again, as Level Two we will just escalate and let the CSIRT assigned take it to the point of litigation or now.

We need an Ubuntu machine to run our Wireshark tool, we can then run our script. In the example here we are using Ubuntu 20.04, but most versions of Ubuntu should support Wireshark. In the Ubuntu machine

1.	Now let's open up Wireshark itself by going back to the Applications button.
2.	![](./SS1.png)
3.	Before we actually open the file, we want to explain the concepts that a Level Two analyst should have an understanding of. The main thing for an analyst is to understand the mindset of an attacker. When an attacker or a group of attackers targets an organization. The first thing that they do is plan. We define an abstract methodology as the following steps:
a.	Planning
b.	Non-Intrusive Target Search
c.	Intrusive Target Search
d.	Remote Target Assessment
e.	Local Target Assessment
f.	Data Analysis
g.	Report
4.	For our lab here we will focus on the Intrusive Target Search, this is where the majority of the attack will be concentrated. Within this step we have our scanning methodology and we further define this as follows:
a.	Live Systems
i.	There has to be a target to attack
b.	Open ports
i.	There has to be doors open on the target
c.	Services
i.	What is behind those open doors
d.	Enumeration
i.	Are there any shares, users and what is the OS
e.	Identify Vulnerabilities
i.	We have to find a weakness as an attacker, and as a defender we have to track our weaknesses
f.	Exploitation
i.	Leverage the weakness to gain access. It is important to understand while all systems and networks will have vulnerabilities, not all will be exploitable
5.	Now that we have the background of the attacker mindset and methods. We can turn our attention to that of the analyst.
6.	In our scenario here, Level One has provided a network capture fill of what they expect is an intrusion into the Golobomantics organization.
7.	We have a methodology that we can use that reverses the steps of the scanning methodology from the perspective at the packet level.
8.	This methodology is as follows:
a.	Suspicious
i.	Does anything look suspicious
b.	Open ports
i.	There has to be an open port and an attack surface to attack
c.	Data
i.	Just detecting an open port does an attacker no good, they need to extract and exfiltrate, impossible to do without data
d.	Streams
i.	In TCP traffic we have streams of communication, and if this is not encrypted then we can determine what has taken place. We also have these in UDP, but they are handled a little differently, and not part of what we are doing here
e.	Signs of compromise
i.	Once we have data and we have streams, the next step is to see if we can determine the signs of compromise
9.	Now that we have the background, let us look open the capture file from the Level One analyst and provide our methodology to it for our analysis
10.	Now let's open up Wireshark itself by going to the left side of the Desktop and selecting the Applications Button
