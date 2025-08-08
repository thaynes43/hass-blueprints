# Home Assistant Blueprint Repository by thaynes
This repository is for hosting blueprints that work with Home Assistant. 

I found many blueprints seem generic but really only work well with a specific device or device class. I will organize these by vendor in the "vendors" folder. Any generic blueprints will be placed elsewhere though none exist today.

## Vendors

Vendor specific blueprints listed below.

### Thirdreality 

#### Multi Function Night Light

I tried using these with local control but I'd often find them all in a weird state where the light would be always on but very dim. I could fix this by setting the brightness to 100% but eventually I got fed up and disabled the local control mode. 

- [Blueprint](vendors/thirdreality/multi-function-night-light.yaml)
- [Device](https://3reality.com/product/multi-function-night-light/?srsltid=AfmBOorRmSz-9wMrWX-aQzW6vmrzwU0TmavZpIxrhNiRBAEm7k02YvaZ)
- [HA Forums](https://community.home-assistant.io/t/thirdreality-multi-function-night-light/918726)

**Mandatory Prerequisites**

1. Make sure your device is on the latest firmware (>= v1.00.82) or local control will re-enable automatically
2. Press the pinhole on the device so that the light flashes red. If it flashes green press it once more to see red.
3. Import the blueprint

**Usage**

The blueprint requires three entities which are all exposed by this device. The defaults lx, brightness, and color work well for my needs but can be modified. I've included a pre-defined list of colors, more can be added by request but since the device used xy color this was the best option for my use case.

The blueprint allows for more than one motion or occupancy sensor to be configured to trigger the night light. This is night if you have multiple nightlights so nearby lights can trigger each other. Or if you have sensors from another vendor that can be used to trigger the light which reduces the delay when just the sensor from the night light is used. 