# upgrade-camera-log-parser
This repo contains scripts which parse versions of upgrade-camera log files from the IceCube Collaboration into JSON files.

V0 is compatible with log files from Jan17th (and potentially earlier)

V1 is compatible with log files from Jan18th-21st (and potentially later)
## JSON File Overview
### Variables included in JSON files
- RETRY - number of attempts at capturing image (?)
- FILENAME - path and file name of .raw image (/path/to/image.raw)
- LED_ON - time in UTC that LED was turned on
- LED_OFF - time in UTC that LED was turned off
- CAPTURE_START - time in UTC that capture was started
- CAPTURE_STOP - time in UTC that capturer stopped
- run-type - 'type' of image taken (i.e. IA, IB, Geometry, etc.)
- string - string number that image was taken on
- device - type of device that took image
- port - number identifying which device took image (?)
- cam - indicates which camera took the image
- illum - indicates which LED was on
- gain - amount of camera gain used while capturing image
- exposure - exposure time camera used while capturing image
- config_fname - path and file name of .json file which was used to configure capture settings (/path/to/config.json)
- config_lst - contents of config_fname

*All values stored as strings*

*(?) indicates that I don't really know what these variables are...*

### Example JSON file
```json
[
  {
    "RETRY": "0",
    "FILENAME": "/home/verical/hole-freeze-operations-data/UpgradeCamera/images/raw/2026-01-18-21-23-10/Camera-Run_IB_string87_mDOM_port5175_cam2_illum4_gain0_exposure3700ms_20260118-21-25-07_trial0.raw",
    "LED_ON": "2026-01-18 21:24:48.073238",
    "LED_OFF": "2026-01-18 21:24:55.491376",
    "CAPTURE_START": "2026-01-18 21:24:48.073244",
    "CAPTURE_FINISH": "2026-01-18 21:24:55.474705",
    "run_type": "IB",
    "string": "87",
    "device": "mDOM",
    "port": "5175",
    "cam": "2",
    "illum": "4",
    "gain": "0",
    "exposure": "3700ms",
    "config_fname": "/home/verical/hole-freeze-operations/UpgradeCamera/OperationsConfigs/String87/ExposureTimeScans/Quad6plus_run11/string87_IA_Q6plus_exp_time_3700_0.json",
    "config_lst": "[{'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 6, 'Wire Pair': 0, 'Address': 2, 'Index': 26, 'Depth': 2178, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5080, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 7, 'Wire Pair': 1, 'Address': 7, 'Index': 27, 'Depth': 2181, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5104, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 8, 'Wire Pair': 0, 'Address': 2, 'Index': 38, 'Depth': 2214, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5112, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 9, 'Wire Pair': 1, 'Address': 7, 'Index': 39, 'Depth': 2217, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5136, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 10, 'Wire Pair': 0, 'Address': 2, 'Index': 50, 'Depth': 2250, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5144, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 11, 'Wire Pair': 1, 'Address': 7, 'Index': 51, 'Depth': 2253, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5168, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 15, 'Wire Pair': 1, 'Address': 2, 'Index': 77, 'Depth': 2331, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5232, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 15, 'Wire Pair': 0, 'Address': 7, 'Index': 78, 'Depth': 2334, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5224, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 19, 'Wire Pair': 1, 'Address': 2, 'Index': 101, 'Depth': 2403, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5296, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 19, 'Wire Pair': 0, 'Address': 7, 'Index': 102, 'Depth': 2406, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5288, 'host': 'fieldhub87'}]"
  },
  {
    "RETRY": "0",
    "FILENAME": "/home/verical/hole-freeze-operations-data/UpgradeCamera/images/raw/2026-01-18-21-23-10/Camera-Run_IA_string87_mDOM_port5082_cam1_illum0_gain0_exposure3700ms_20260118-21-25-07_trial0.raw",
    "LED_ON": "None",
    "LED_OFF": "None",
    "CAPTURE_START": "2026-01-18 21:24:47.838073",
    "CAPTURE_FINISH": "2026-01-18 21:24:55.310467",
    "run_type": "IA",
    "string": "87",
    "device": "mDOM",
    "port": "5082",
    "cam": "1",
    "illum": "0",
    "gain": "0",
    "exposure": "3700ms",
    "config_fname": "/home/verical/hole-freeze-operations/UpgradeCamera/OperationsConfigs/String87/ExposureTimeScans/Quad6plus_run11/string87_IA_Q6plus_exp_time_3700_0.json",
    "config_lst": "[{'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 6, 'Wire Pair': 0, 'Address': 2, 'Index': 26, 'Depth': 2178, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5080, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 7, 'Wire Pair': 1, 'Address': 7, 'Index': 27, 'Depth': 2181, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5104, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 8, 'Wire Pair': 0, 'Address': 2, 'Index': 38, 'Depth': 2214, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5112, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 9, 'Wire Pair': 1, 'Address': 7, 'Index': 39, 'Depth': 2217, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5136, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 10, 'Wire Pair': 0, 'Address': 2, 'Index': 50, 'Depth': 2250, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5144, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 11, 'Wire Pair': 1, 'Address': 7, 'Index': 51, 'Depth': 2253, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5168, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 15, 'Wire Pair': 1, 'Address': 2, 'Index': 77, 'Depth': 2331, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5232, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 15, 'Wire Pair': 0, 'Address': 7, 'Index': 78, 'Depth': 2334, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5224, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IA', 'Quad': 19, 'Wire Pair': 1, 'Address': 2, 'Index': 101, 'Depth': 2403, 'Camera': 'cam_down', 'LED': '0', 'ExposureTime': 3700, 'DOMNet Data Port': 5296, 'host': 'fieldhub87'}, {'String': 87, 'Device': 'mDOM', 'RunType': 'IB', 'Quad': 19, 'Wire Pair': 0, 'Address': 7, 'Index': 102, 'Depth': 2406, 'Camera': 'cam_ortd_a', 'LED': 'led_up', 'ExposureTime': 3700, 'DOMNet Data Port': 5288, 'host': 'fieldhub87'}]"
  }
]
```

