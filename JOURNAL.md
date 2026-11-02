---
title: "Xbox Controller Custom Bluetooth Adder"
author: "rehanhabbu"
description: "Uses an ESP32-S3 to convert a proprietary XBOX One controller into a Bluetooth that PC's can use."
created_at: "2026-10-03"
---

# 2026-10-09: Continued Working on Schematic

**Total time spent: 0.5 hours**

Continued working on schematic and updated parts with final BOM, fixed capacitor and resistor values from TI datasheets, and got footprints from online and wired them. Stopped for now because lapse was being really glitchy and only recorded my browser for a part, then kept cutting off and removing time. ![image.png](https://cdn.hackclub.com/01a122ae-9d14-7ef7-90cd-eb777b00b39c/image.png)
https://lapse.hackclub.com/timelapse/2X8PF4nIzJ3m
https://lapse.hackclub.com/timelapse/72Wt8PUK65uOv

# 2026-10-08: Updated BOM and created Github Repo

**Total time spent: 0.75 Hours**

Updated and mostly finalized BOM with LCSC parts for PCB-A from JLCPCB and other parts for things i'm going to hand solder as well as links and exact pricing. Also created the git repo with the folders, BOM.md and CSV, and schematic.![image.png](https://cdn.hackclub.com/01a11d17-2777-736a-8114-24a8ead17d51/image.png)

# 2026-10-06: Began Designing V1 schematic model

**Total time spent: 0.5 hours**

Today I started working on the schematic for the PCB on KiCad and added the ESP32, USBC, LiPo JST, buck/boost, and capacitors.
![image.png](https://cdn.hackclub.com/01a113cc-0706-701c-9e97-3c93dc6682a9/image.png)

# 2026-10-05: Designed the V1 3D model

**Total time spent: 2 Hours**

Today I measured out my Xbox controller dimensions of things like the battery cavity and made a V1 3D model with the neck and the part that goes in the cavity to get better sizing requirements before moving to PCB. Next I just gotta get it to go into the cavity by pushing it a bit tommorrow. 
Btw I recored on my phone not lapse cuz I was measuring and apparently I can't upload to lapse soooo. yeah. The video was 2:02:34  ![image.png](https://cdn.hackclub.com/01a10e84-b230-7614-8191-d2f49e1b50fc/image.png)![image.png](https://cdn.hackclub.com/01a10e84-c786-7176-be6d-fb2718a39597/image.png)

# 2026-10-04: Organized power calculations and estimated battery runtime

**Total time spent: 1 Hour**

Today I created a basic diagram in Circuit designed with mostly placeholder, but accurate parts:
![image.png](https://cdn.hackclub.com/01a10889-3674-7510-98c0-927b0939a6d6/image.png)
Then I used Falstad to simulate and check all the voltages and make sure power seemed right. ![image.png](https://cdn.hackclub.com/01a10889-f267-7f37-86a5-1067f05ed158/image.png)![image.png](https://cdn.hackclub.com/01a1088a-07ef-7815-8f6f-dd6806b7817f/image.png)![image.png](https://cdn.hackclub.com/01a1088a-2979-7a48-9957-2eb853bf63af/image.png)

Then i made a Desmos engineering calculation sheet for, and I organized the editable equations into Battery Sense, Typical Loads, Boost + Worst Case, and Runtime, shortened the variable names, and fixed the boost-current reference so it uses the controller power correctly.

The battery divider uses two 100 kΩ resistors and gives 1.85 V at the ADC from a 3.7 V battery. The controller estimate is 0.294 A at 5 V (1.471 W), and the ESP estimate is 0.300 A at 3.3 V (0.990 W), giving about 2.461 W combined typical power. With 90% efficiency, the controller boost input current is about 0.442 A. Worst-case combined power is 4.15 W.

For a 1000 mAh, 3.7 V LiPo, the estimated energy is 3.7 Wh. Using the 90% efficiency assumption, estimated runtime is about 1.35 hours typical and 0.802 hours (48 minutes) worst case. These are calculation-based estimates; I have not measured the loads or tested battery runtime on hardware yet.

Screenshots of the organized worksheet:

**Battery Sense**

![Battery divider calculations](https://cdn.hackclub.com/01a1087f-f2d7-7143-bf16-e82a86c171ef/clipboard.png)

**Typical Loads**

![Controller and ESP power calculations](https://cdn.hackclub.com/01a10880-12ac-7bd0-a11d-6d0269b2b209/clipboard.png)

**Boost + Worst Case and Runtime**


# 2026-10-03: Designed Sketch + Rough BOM

**Total time spent: 1 Hour**

Today I started making a rough sketch of placement and how everything will look in onshape and made a rough BOM. My plan is to use an ESP32-S3 to convert the USB signals from my XBOX controller without Bluetooth signals the computer can access into ones it can.
![image.png](https://cdn.hackclub.com/01a103f9-4151-7f24-b2b7-94925fc050cc/image.png)
![image.png](https://cdn.hackclub.com/01a103f9-80bb-7fda-94cf-16810af87f15/image.png)

