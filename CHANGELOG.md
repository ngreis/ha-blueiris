# Changelog

## 2020-04-29

**Implemented enhancements:**

- New feature under options - Control which camera, binary sensor or profile switch are being created 

## 2020-04-28

**Fixed bugs:**

- Fix disabled entity check throws an exception in logs

## 2020-04-27

**Fixed bugs:**

- Fix disabled entities still being triggered for updates

## 2020-04-26

**Fixed bugs:**

- Removed limitation of one instance only
- Fix [\#62](https://github.com/elad-bar/ha-bleuiris/issues/62) disabled entities are getting enabled after periodic update (update interval)

## 2020-04-25 #2

**Fixed bugs:**

- Fix log message restored appeared when it shouldn't

## 2020-04-25 #1

**Implemented enhancements:**

- Moved auto-generating configurations service `blueiris.generate_advanced_configurations` to Integration -> Options
- Added ability to configure the log level of the component from Integration - Options, more details in README

**Fixed bugs:**

- Fix [\#60](https://github.com/elad-bar/ha-bleuiris/issues/60) configuration generating process and README links

## 2020-04-24 #2

**Fixed bugs:**

- Fix [\#56](https://github.com/elad-bar/ha-bleuiris/issues/51) moved dependency on MQTT to optional
- Fix missing resources

## 2020-04-24 #1

**Implemented enhancements:**

- Refactored camera to use basic camera component instead of generic

## 2020-04-20

**Fixed bugs:**

- Added validation if state is not available to restore it [\#54](https://github.com/elad-bar/ha-bleuiris/issues/54) 

## 2020-04-19

**Fixed bugs:**

- Fix issue [\#51](https://github.com/elad-bar/ha-bleuiris/issues/51) in config_flow
- Validation of server existence made 2 calls to server instead of 1 
 
## 2020-04-18

**Implemented enhancements:**

- Added CHANGELOG.md
- Improved README.md
- Separated BlueIris Server setting from README.md

**Fixed bugs:**

- Fix issue caused by integration removal - duplicate call for removing event listener 

## 2020-04-15

**Implemented enhancements:**

- Major change of file structure
- Improved communication between BI API and HA
- Fix component update upon change
- Avoid API get details requests upon change of switch or when an MQTT message is being received
- Better management of entities and devices
- Added more log messages for faster debugging 

## 2020-04-12

**Fixed bugs:**

- Fix issue [\#37](https://github.com/elad-bar/ha-bleuiris/issues/37) - Restart of HASS causes all entities to be renamed to defaults <br/>
  improving the way the component is loading, unloading and discover new entities (sensors, camera and switch).  <br/>
  the main issue as reported in the past was that once changing the entity_id / name it will return to the original after restart.  <br/>
  another issue that caused by the way it was handled, upon changing the options (settings) - it took few seconds to present the new entities and sometimes it happened only after restart.  <br/>
  In that version, the entity_id, name will remain as manually set and changes of options will take place immediately

## 2020-02-28

**Fixed bugs:**

- Removed hard-dependency on MQTT, if MQTT integration was not set, binary sensors will not be created - Issue [\#32](https://github.com/elad-bar/ha-bleuiris/issues/32)
- Fix issue [\#28](https://github.com/elad-bar/ha-bleuiris/issues/28) - entities not available after restart
- Fix issue [\#27](https://github.com/elad-bar/ha-bleuiris/issues/27) - when changing switch it doesn't work smoothly and after restart
- Resources (strings) fixed


**Implemented enhancements:**

- Username and password are now optional, if not set, will not create profile's switches
- Added validation for host, port and SSL state in configuration, if URL is not accessible, will throw an error
- Validate administrator username and password, in case entered wrong credentials, will throw an error


## 2020-02-07 - v2.0.0 - Breaking change!!! 

**Implemented enhancements:**

- BlueIris 5 JSON API integration
- UI configuration support instead of YAML
- Less configurations, takes configurations from BI server (all cameras are loaded, audio binary sensor will not created unless needed)
- More details per camera in the attributes 
- Switch functionality changed, each profile is being represented with a switch, `is armed` switch removed
- Added support for HACS

## 2020-02-05

**Implemented enhancements:**

- No need to declare binary_sensor, switch and camera as those are being auto-discovered 

## 2020-01-17

**Implemented enhancements:**

- Fixed binary sensor for motion / audio to work without zones (no need to define MOTION_A to get its off event)  