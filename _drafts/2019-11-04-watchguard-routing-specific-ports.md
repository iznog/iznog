---
layout: default
title: Watchguard - reencaminhamento de portas
date: 2019-11-04
author: Paulo
categories: routing watchguard
---

# Watchguard - reencaminhamento de portas

You have a server providing a service (e.g., SMTP) and need your Firebox firewall to pass traffic to it.

Solution

There are two steps to this. First, you create an SNAT rule and, second, you create a firewall policy to map that rule to a port on the firewall.

First, setup port forwarding, which Watchguard calls SNAT.

    Click on Firewall->SNAT.
    Click Add.
    You will land in the SNAT configuration page.
    For Name, enter SMTP to Exchange.
    Click Add.
    Choose External.
    For Internal IP Address, enter the LAN IP of your Exchange server.
    Click Ok.
    Click Save.

Second, setup our firewall policy to use the SNAT rule:

    Click Firewall->Firewall Policies.
     Click the Plus sign on the far right.
    In Select a Policy Type, choose Packet Filters->SMTP. Notice that choosing this policy type will set the Policy Name. You can change the Policy Name if you’d like.
    Click Add Policy.
    The Policy will be created and you will land in the Policy Configuration page.
    In the From, click Any-Trusted and click Remove.
    In the From, click Add.
    Set Member Type to Alias and choose Any.
    Click Ok.
    In the To, click on Any-External and click Remove.
    In the To, click on Add.
    Set Member Type to Static NAT and click the SNAT rule we created earlier.
    Click Ok.
    Scroll to the bottom of the Policy Configuration page and click Save.
