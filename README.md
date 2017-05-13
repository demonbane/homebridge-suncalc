# homebridge-sundown-sensor

[Suncalc](https://github.com/mourner/suncalc) plugin for [Homebridge](https://github.com/nfarina/homebridge) that publishes a HomeKit occupancy sensor that gets triggered at Sundown, or at a certain offset from sundown. (e.g. sundown - 30 minutes)

# Offset

This plugin allows you to specify an offset for the end of sunrise, and the beginning of sunset. For instance, if you want to trigger a scene to start 30 minutes before sunset (useful for interior lighting), you can specify an sunsetStart offset of -30 in the config.json file, as shown below. This fires the trigger 30 minutes earlier than normal, allowing your lights to come on as it gets darker at your location.

# Installation

1. Install Homebridge using: `npm install -g homebridge`
2. Install this plugin using: `npm install -g homebridge-sundown-sensor`
3. Use the [Google Geocoder Tool](https://google-developers.appspot.com/maps/documentation/utils/geocoder/) to get your location coordinates.
4. Update your Homebridge `config.json` using the sample below.

# Configuration

```json
{
  "accessory": "SundownSensor",
  "location": {
    "lat": 30.506667,
    "lng": -97.830278
  },
  "offset": {
	  "sunriseEnd" : 30,
	  "sunsetStart" : -30
  },
  "name": "SundownSensor"
}
```

Fields:

* `accessory` must be "SundownSensor" (required).
* `location` contains your location coordinates (required).
* `name` is the name of the published accessory (required).
* `offset` contains offset values in minutes of when that event should be fired. (optional).
