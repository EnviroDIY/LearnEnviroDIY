---
title: "Introduction to Telemetry"
teaching: 30
exercises: 15
questions:
- "What is telemetry and why is it worth the effort?"
- "How do I manage cellular wireless data plans?"
objectives:
- "Learn how to use Hologram.io to manage your wireless network."
keypoints:
- "Realtime data has numerous benefits to maintaining monitoring stations, timing the collection of samples, and engaging others."
- "Hologram.io is a cellular IoT connectivity consolidator and broker that provides low-bandwidth, low-cost plans and that massively simplifies the management of SIM cards that can operate in 196 counties over 550 carriers."
---


## Episode 11: Introduction to Telemetry

Realtime data has numerous benefits, including:
- Improving the management and maintenance of automated monitoring stations, for example by showing that a sensor might need to be cleaned, that battery charge is getting low, or that the logger might be malfunctioning.
- Informing the prioritization and timing of when to collect samples for laboratory analysis.
- Engaging collaborators or the public in your monitoring and other activities.

### Telemetry Basics

Telemetry is the automated communication of measurements and other data from a remote monitoring station to a central location. In the 21st century (at least this part of it), telemetry typically involves using the internet to get the data to a central database server. There are two layers to telemetry: physical connectivity and communication protocol.

**Physical Connectivity for Telemetry** involves using a wire or radio to connect the remote station to the internet. Wireless, radio communications are often the most appealing, but there are many options:
- Cellular Radio
- Satellite radio
- WiFi
- Bluetooth
- Point-to-multipoint, such as 802.15.4 (or WiFi)
- Mesh Networking, such as ZigBee
- LoRa & LoRaWAN
- NB-IoT

**Communication Protocols for Telemetry** include familiar internet protocols and also more modern protocols designed specifically for IoT, such as:
- FTP
- HTTP SOAP web services api
- HTTP REST web services api
- Message Queuing Telemetry Transport (MQTT)
- UDP CoAP
    -NOTE: the client (your station or device) and the server BOTH need to be configured to use the same protocol.

Any of these Communication Protocols can operate over any physical connectivity layer.

Presently, the use of cellular radios with HTTP REST is the most common combination of physical connectivity and communication protocol because of its ease of use, broad coverage, and now relatively low cost. EnviroDIY ModularSensors was thus primarily designed and tested to work with this combination, although some other combinations are also supported.

### Hologram.io to Manage Your Wireless Network

There are many ways to acquire and manage cellular plans for monitoring devices. However, we have found that [Hologram.io](https://hologram.io) provides one of the most flexible, lowest-cost and easiest-to-manage services for organizations developing cellular IoT networks. Read some of the reasons [Why Hologram](https://hologram.io/why-hologram/), including that you can [Start for Free](https://dashboard.hologram.io/account/register?e=IA==). (Hologram.io has no affiliation with or sponsorship of EnviroDIY.)

**Get Stared:**
- Set up a [Free Hologram Account](https://dashboard.hologram.io/account/register?e=IA==)
- Order and activate your first SIM, which is free for first one!
- Set up or join an [Organization](https://hologram.io/docs/guide/account/organizations/) to collaborate with others.


{% include links.md %}
