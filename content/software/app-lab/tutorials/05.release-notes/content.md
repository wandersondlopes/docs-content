---
title: 'App Lab Release Notes'
difficulty: beginner
tags: [app-lab, releases]
description: 'This article contains release notes of App Lab.'
author: Arduino Team
---

# Firmware Information

This page contains all release notes for Arduino App Lab. To access the software, go [here](https://www.arduino.cc/en/software/#app-lab-section).

<Alert type="note">Note that you need to have an UNO Q ([2GB](https://store.arduino.cc/products/uno-q) or [4GB](https://store.arduino.cc/products/uno-q-4gb)) to use Arduino App Lab.
</Alert>

# Firmware Versions

Cat ipsum dolor sit amet, tweeting a baseball but stick butt in face rub whiskers on bare skin act innocent. Thinking about you i'm joking it's food always food thug cat or check cat door for ambush 10 times before coming in and russian blue your pillow is now my pet bed, so jump launch to pounce upon little yarn mouse, bare fangs at toy run hide in litter box until treats are fed.

## Latest Firmware Version: [YYYY.MM.DD] | 0.5.0

You can now connect App Lab with Arduino Cloud and your Edge Impulse Account! This means that you can now use the IoT Remote App as a camera input to your examples, as well as create your own custom models using Edge Impulse.

New Examples: 
* Color Your LEDs
* Video Object Detection on Mobile

See a full list of what's new and which bugs have been fixed below.

### What's new

* Connect App Lab with Edge Impulse Account
* Edge Impulse Custom Model integration
* Switch boards from the footer
* Use Command Line to import/export Arduino Apps
* UI updated
  * What’s new pop up during update
  * Notifications update
  * Persistent Editor Panel sizing on tab change or restart
  * Other UI improvements
* Bricks
  * New: Web Socket Camera integration with Arduino IoT Remote App
  * Improvement: Camera peripheral, brick documentation
* Examples
  * New: Color your LEDs
  * New: Video Object Detection on Mobile
  * Improvements: LED Matrix Painter

### What's fixed

* HTML syntax highlighting lost on scroll
* Board discovery: duplicates and network mode shown when USB connection available
* Allow Skip/Change network when “check for updates“ fails
* Misc cosmetic/behavioral defects
* Updates will download only the minimum required data, instead of re-downloading all the container images each time
* app-cli commands now also autocomplete app names as “folder names”
* Fixed an error when checking for updates and there are no platform updates
* Bricks
  * Minor fixes on Camera peripheral discovery and Speaker peripheral discovery
* Examples
  * Fixes on Object Detection in case of multiple detection

<Alert type="note">
You can always find the latest release [here](https://github.com/arduino/arduino-app-lab/releases). 
</Alert>

## Available Firmware Versions

Below is a list of all available firmware versions with their release notes.

### App Lab | 0.4.0

<details>
  <summary><strong>2026.02.06 (Release 0.4.0)</strong></summary>

#### What’s New

- **Integrated Board Updates:** You can now update outdated boards directly within App Lab using the new built-in Flasher tool.
- **Optional Wi-Fi Setup:** You can now skip the Wi-Fi configuration step during setup. Note: A warning will appear to remind you that some network-dependent features will be unavailable.
- **Enhanced Code Editor:** Added syntax highlighting for Web development (JS/TS, CSS/SCSS, HTML, and JSON) to make code easier to read.
- **Improved Troubleshooting:** If an App crashes, the app now saves the logs so you can review what happened.
- **General Refinements:** Updated the user interface and added several small improvements to the editor for a smoother experience.
- **Analytics:** Improved our internal reporting to better understand the difference between PC and SBC users.

#### What’s Fixed

- **File Retention:** Resolved an issue where App.yaml or README.md files would occasionally be deleted during configuration.
- **App Stability:** Fixed a bug that sometimes prevented the Arduino App interface from opening.
- **Network Errors:** The system now correctly identifies and reports "wrong password" errors when connecting to a network.
- **README Display:** Fixed a bug in Network mode that caused README files to appear corrupted or fail to load.
- **Security:** Applied security updates to the open-source repository.
- **General Fixes:** Addressed various minor visual and behavioral bugs.

#### GitHub Release

https://github.com/arduino/arduino-app-lab/releases/tag/al-0.4.0

</details>

If you have already downloaded App Lab once, you should get your updates automatically next time you open the software. If you want to download the latest firmware, you can always access it [here](https://www.arduino.cc/en/software/#app-lab-section). 