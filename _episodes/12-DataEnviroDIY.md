---
title: "Set up Monitor My Watershed Data Portal"
teaching: 10
exercises: 20
questions:
- "How can I have real-time monitoring for my sensor stations?"
- "How do I send data to an internet repository?"
objectives:
- "Create a repository at MonitorMyWatershed.org."
- "Add variables to log from available sensors."
keypoints:
- "Create a repository at MonitorMyWatershed.org. Add variables to log from available sensors."
---
## Episode 12: Setting up a Monitor My Watershed Site

The EnviroDIY ecosystem includes a data repository that is free, open source, secure, and does not expire. The data portal includes a time-series analyst and the ability to download your data. In this episode you will create an account and set up a site to log variables for the Mayfly and/or BME280, and/or the DS18.

  1. Go to [MonitorMyWatershed.org](https://monitormywatershed.org) and create an account.
  2. After your account is created, click **My Sites** next to the "Monitor my Watershed" logo.
  3. Push the `Register a New Site` button.
  4. Fill in the site information by making a test site located at your desk.
      - **Site Code:** Short name for your site that does not contain spaces, such as WSP01 or RPB-3. This code will become part of the URL to reach your site. (Pro tip: avoid characters that are annoying to type on a mobile phone, such as underscore.)
      - **Site Name:** Brief description of the site. You may use spaces here, but not too long.
      - **Site Type:** This uses a *controlled vocabulary* with a drop-down menu that contains options like *stream*, *water quality station*, etc. Since this is your test station, select whatever you like.
      - **Latitude** and Longitude**: Can be set by clicking on the map or by entering decimal degrees.
    5. Leave optional fields blank and click **Register Site**.
    6. Click **Manage Sensors** and select the <kbd>+</kbd> button to *Add New Sensor*.
    7. Use the drop down menus to find and add your sensors. The Mayfly manufacturer is EnviroDIY. The clock and DS18 are by Maxim. The BME280 is made by Bosch (because they made the chip and Adafruit or Grove made the breakout board).
    <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/envirodiy_addsensor.png" width="300">
    8. After you have added at least 3-4 variables to log, click **Back to Site Details**.
    9. Click the **Token UUID List** button. This is a universally unique identifier for your data repository and for each variable that you log. These numbers are how your data get put in the right place when you transmit them to the data portal. You will need these numbers for the final episode of Part 2, but you can wait to copy and paste them during that episode.  

In the next episode we will discuss telemetry and set up your sim card.


{% include links.md %}
