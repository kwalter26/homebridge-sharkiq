<span align="center">

# Homebridge Shark Clean Vacuum Plugin
[![verified-by-homebridge](https://badgen.net/badge/homebridge/verified/purple)](https://github.com/homebridge/homebridge/wiki/Verified-Plugins)
[![npm](https://badgen.net/npm/dt/homebridge-sharkiq?color=purple)](https://www.npmjs.com/package/homebridge-sharkiq) 
[![npm](https://badgen.net/npm/v/homebridge-sharkiq?color=purple)](https://www.npmjs.com/package/homebridge-sharkiq) 

</span>

A new homebridge plugin for SharkIQ Vacuums.

Contribution would be very helpful as this plugin is still new and has some small flaws here and there. I used the [sharkiq](https://github.com/JeffResc/sharkiq/) python module as a reference for creating the javascript wrapper to control SharkIQ Vacuums.

This plguin has only been tested on the `UR250BEXUS` model.

## Install and Setup

### Step 1.

Run `npm install -g homebridge-sharkiq`

### Step 2.

Configure Homebridge. The config file for SharkIQ should include:
```json
{
    "platforms": [
        {
            "name": "SharkIQ",
            "platform": "SharkIQ",
            "email": "[Shark Clean Account Email]",
            "password": "[Shark Clean Account Password]",
            "vacuums": [
                "[Shark Vacuum Serial Number]",
                "..."
            ],
            "invertDockedStatus": false,
            "dockedUpdateInterval": 5000
        }
    ]
}
```

The email and password is your Shark Clean account you used to setup the vacuum. The Vacuums array is a list of your vacuum's serial numbers. If you only have one vacuum, just include the one's serial number.

The default interval between updating the docked status is 5 seconds (5000 ms). To change the docked status interval, add `dockedUpdateInterval` to your config. Value is in milliseconds.

## Features

- Be able to turn on and off the vacuum
- Set the power mode of the vacuum and change it while running
- Sensor for if the vacuum is docked or not
    - The sensor will display as "opened" when the vacuum is docked and "closed" when the vacuum is not docked
    - Set `invertDockedStatus` to `true` to display as "closed" when the vacuum is docked and "opened" when the vacuum is not docked
- Pause switch for pausing the vacuum while it's running

## Notes

~~This plugin is still a little buggy at some times. Sometimes the vacuum won't refresh or set a control from Homebridge right away. But it usually does update the first time. If not the second time.~~

Contributions would be very helpful to help this Homebridge plugin stay maintained and up to date. If you have any problems, please create an issue.

## Useful Links
- [SharkIQ Python](https://github.com/JeffResc/sharkiq/)
