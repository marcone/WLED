# Fix unreachable net services V2

**Attention: This usermod compiles only for ESP8266**

This usermod-v2 modification performs a ping request to a local IP address every 60 seconds. This ensures WLED net services remain accessible in some problematic WiFi environments.

The modification works with static or DHCP IP address configuration.

_Story:_

Unfortunately, with many ESP projects where a web server or other network services are running, after some time, the connecton to the web server is lost.
The connection can be reestablished with a ping request from the device.

With this modification, in the worst case, the network functions are not available until the next ping request. (60 seconds)

## Webinterface

The number of pings and reconnects is displayed on the info page in the web interface.
The ping delay can be changed. Changes persist after a reboot.

## JSON API

The usermod supports the following state changes:

| JSON key    | Value range      | Description                     |
|-------------|------------------|---------------------------------|
| PingDelayMs | 5000 to 18000000 | Deactivate/activate the sensor  |

 Changes also persist after a reboot.

## Installation

1. Add `Fix_unreachable_netservices` to `custom_usermods` in your PlatformIO environment.

Hopefully I can help someone with that - @gegu
