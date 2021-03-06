# System View

[Readme](README.md) |
[Home View](home.md) | [Media](media.md) | [Rooms](rooms.md) | [Cameras](cameras.md) | [Comics](comics.md) | [**System**](system.md) | [Floor Plan](floorplan.md) 

![System View](https://github.com/dnguyen800/home-assistant-configuration-example/blob/master/images/system.png?raw=true)

## Components in this View
Note: I set 'panel: true' to use the entire width of the screen. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L495-L500) |

0) **Lovelace Layout Card** - Backend card that provides more control in how to organize your Lovelace cards in a readable format, versus the previous method of using vertical and horizontal stacks. You define the columns and choose where to insert breaks, thus maximizing screen space | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L495-L504) | [Github](https://github.com/thomasloven/lovelace-layout-card) |

1) **Compact Custom Header** - Reduces the height of the original HA header, saving precious space on small tablets like the Fire HD8. Also adds a clock. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L507-L510) | [Github](https://github.com/maykar/compact-custom-header/) |

2) **System Info Cards** - Showing system details of the Raspberry Pi and the SD card. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L511-L549)
    * **Vertical and Horizontal stack cards** used to organize the gauge cards in a 2x2 format. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L505-L554) |
    * **Gauge cards** displays the system monitor data in an appealing view. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L513-L528) | [HA Lovelace Card](https://www.home-assistant.io/lovelace/gauge/) |
    * **System Monitor sensor** provides the system monitor data, duh. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/config/sensors.yaml#L89-L98) | [HA Component](https://www.home-assistant.io/components/sensor.systemmonitor/) |

3) **System Info Cards (2)** - Showing system details of the Raspberry Pi and the SD card. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L557-L580) |
    * **Lovelace Sensor cards** are used to display system information. I forgot to set 'graph: line' for an even cooler visual. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L561-L580) | [HA Lovelace card](https://www.home-assistant.io/lovelace/sensor/) |
    * **Commandline sensors** are used to pull CPU and GPU temperatures from a Raspberry Pi. Taken from the HA Component page. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/config/sensors.yaml#L71-L82) | [HA Component](https://www.home-assistant.io/components/sensor.command_line/) | 
    * **Speedtest sensor** gets the download and upload speeds of my internet connection. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/config/sensors.yaml#L59-L62) | [HA Component](https://www.home-assistant.io/components/sensor.speedtest/) |

4) **Tracker Card** - Tracks the installed and latest versions of (some) custom components and Lovelace cards. I can't say Custom Updater tracks every custom URL I added, but it works for some. If you do not have YAML mode enabled, then this will not work.
    * **Custom tracker card** displays the data from Custom Updater sensor and lets you click a button to update the components. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L550-L554) | [Github](https://github.com/custom-cards/tracker-card) |
    * **Customer Updater Sensor** tracks version changes of the custom components and Lovelace cards used in my UI. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/configuration.yaml#L87-L95) | [Github](https://github.com/custom-components/custom_updater) | [Wiki](https://github.com/custom-components/custom_updater/wiki/Installation) |

5) **Host Details** - Uses the Entities Lovelace card to display some info about the Home Assistant host. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L583-L589) | [HA Lovelace Card](https://www.home-assistant.io/lovelace/entities/) |
    * **REST and Version sensors** pull up the latest and installed Home Assistant version. Template was found in HA forums. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/config/sensors.yaml#L100-L108) | [HA Component](https://www.home-assistant.io/components/sensor.rest/) |

6) **Automations** - Sometimes I need to disable certain media automations (like turning on the TV when Xbox turns on), so I dynamically list all automations using the Monster card and the Entities card. | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L590-L597) |
    * **Monster card** used to dynamically show all automations--in my case, any automations labeled as 'Media.' | [My Config](https://github.com/dnguyen800/home-assistant-configuration-example/blob/c464015b67898ab87d38762f3f4858ecddc3ea87/configuration/ui-lovelace.yaml#L590-L597) | [Github](https://community.home-assistant.io/t/lovelace-bringing-back-entity-filter-monster-card/58701) |
