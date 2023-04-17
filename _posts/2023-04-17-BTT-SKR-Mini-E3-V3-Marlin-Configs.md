---
title:  "MarlinFw Config Notes for BTT SKR Mini E3 V3 Board on Ender 3 Pro"
categories:
  - Electronics
  - 3D Printing
tags:
  - Ender 3 Pro
  - Marlin Firmware
  - BTT SKR Mini E3 V3
  - Electronics
---

# WIP

Download base configs from [MarlinFirmware/Configurations](https://github.com/MarlinFirmware/Configurations/tree/bugfix-2.1.x/config/examples/Creality/Ender-3%20Pro/BigTreeTech%20SKR%20Mini%20E3%203.0)

### For Octoprint [From Octoprint Community](https://community.octoprint.org/t/a-list-of-recommended-marlin-features/39048):

Plugins:

1. https://plugins.octoprint.org/plugins/m73progress/
2. https://plugins.octoprint.org/plugins/arc_welder/
3. https://github.com/chendo/BufferBuddy
4. https://plugins.octoprint.org/plugins/meatpack/
5. Also enable in OctoPrint (>= 1.9) Serial Connection -> Firmware & protocol -> Wait to load the SD card file list until the firmware capability report is processed.
6. OctoPrint Settings -> Serial Connection -> Firmware & protocol:
    1. add M524 to "Emergency commands"
    2. set M524 as "SD Cancel Command"

Configuration.h:
```c
#define NOZZLE_PARK_FEATURE
#define SPEAKER
```
Configuration_adv.h:
```c
#define SOUND_MENU_ITEM
#define SET_PROGRESS_MANUALLY
#define SET_PROGRESS_PERCENT
#define SHOW_REMAINING_TIME
#define SET_REMAINING_TIME
#define LONG_FILENAME_HOST_SUPPORT
#define AUTO_REPORT_SD_STATUS
#define ARC_SUPPORT
#define EMERGENCY_PARSER
#define ADVANCED_OK
#define ADVANCED_PAUSE_FEATURE
//Configure NOZZLE_PARK_FEATURE
//HOST_PROMPT_SUPPORT or EMERGENCY_PARSER ?
//PARK_HEAD_ON_PAUSE 
#define AUTO_REPORT_TEMPERATURES
#define AUTO_REPORT_POSITION
#define M114_DETAIL
#define M114_REALTIME
#define EXTENDED_CAPABILITIES_REPORT
#define REPORT_FAN_CHANGE
#define MEATPACK_ON_SERIAL_PORT_1
#define MEATPACK_ON_SERIAL_PORT_2
#define GCODE_CASE_INSENSITIVE
#define HOST_ACTION_COMMANDS
#define HOST_PROMPT_SUPPORT
#define HOST_START_MENU_ITEM
//M20_TIMESTAMP_SUPPORT
// Maybe?
#define BLOCK_BUFFER_SIZE 64
#define BUFSIZE 32
#define TX_BUFFER_SIZE 32
#define RX_BUFFER_SIZE 2048
```

SuperSlicer:

### Faster BLTouch [From Crosslink](https://www.youtube.com/watch?v=PFuz8915GCs)

Configuration.h
```c
//#define MULTIPLE_PROBING //Disable
//Z_PROBE_FEEDRATE_FAST 10*60
//DEFAULT_MAX_FEEDRATE { 500, 500, 20, 25 }
//XY_PROBE_FEEDRATE (150*60)
//Z_CLEARANCE_BETWEEN_PROBES 3
//HOMING_FEEDRATE_MM_M {(150*60), (150*60), (10*60) }
```

Configuration_adv.h:
```c
#define BLTOUCH_HS_MODE true
#define BLTOUCH_DELAY 300 //200

```



