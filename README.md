# Apartment Build Backup =

## Files included

- `automations.yaml`
- `configuration.yaml`
- `ui-lovelace-matt-apartment-dashboard.yaml`
- `apartment_helper.yaml`
- `README.md`

## Purpose

These are sanitized backup/export copies of the final files from this apartment Home Assistant build.

They were prepared for public posting to GitHub by removing or generalizing:
- the personal name used in dashboard and entity references
- the personal phone device tracker name
- the notify device ID used by UPS blueprints

## Important note

These sanitized files are safe to share publicly, but they are **not plug-and-play** until you replace placeholder values with your own live entities.

## Replacements you must make before using them

### In `automations.yaml`
Replace:
- `person.primary_user` with your real person entity
- `YOUR_NOTIFY_DEVICE_ID` with your real notify device ID
- `device_tracker.primary_phone` only if you want that shown anywhere else in your setup

### In `ui-lovelace-matt-apartment-dashboard.yaml`
Replace:
- `person.primary_user` with your real person entity
- `device_tracker.primary_phone` with your real phone tracker

### In `apartment_helpers.yaml`
Replace helper logic only if your door, hallway, or living room entities are named differently.

## Main goals from this build

- Simplify and stabilize the living room automation behavior
- Make the living room lights come on when the front or side doors open
- Allow living room motion to turn on the living room lights
- Respect manual light control from the interface
- Keep outside lights on sunset/sunrise behavior
- Keep safety, UPS, and network automations
- Clean up configuration structure
- Build a cleaner multi-view dashboard

## Living room behavior decisions

Final behavior:
- Door-open lighting turns on living room lights
- Motion lighting can turn on living room lights
- Motion lighting is blocked during bedtime mode
- Door-open lighting is not blocked during bedtime mode
- Manual UI light control is respected
- Media playback is respected where relevant

## Configuration structure

The cleaned configuration file stays minimal:
- `default_config`
- `homeassistant` packages include
- frontend themes include
- automations include
- scripts include
- scenes include

## Dashboard structure

The dashboard includes:
- Main view
- Safety view
- Network / Power view
- living room automation visibility
- router/modem reboot buttons
- basic network information
- UPS information

## Files in this sanitized set

### `automations.yaml`
Rewritten automations with personal references removed.

### `configuration.yaml`
Minimal configuration file.

### `ui-lovelace-matt-apartment-dashboard.yaml`
Multi-view dashboard with personal identifiers generalized.

### `apartment_helpers.yaml`
Small package file with occupancy helper sensors.

## Recommended replacement order for private use

1. Back up your current Home Assistant files
2. Replace `automations.yaml` with `automations.yaml`
3. Replace `configuration.yaml` with `configuration.yaml`
4. Replace `ui-lovelace-dashboard.yaml` with `ui-lovelace-matt-apartment-dashboard.yaml`
5. Replace or confirm `/config/packages/apartment_helpers.yaml` using `apartment_helper.yaml`
6. Run **Developer Tools -> YAML -> Check configuration**
7. If valid, restart Home Assistant

## Important caution

Before using these files in a live environment:
- make a fresh backup
- run **Check configuration**
- verify that all entity names match your Home Assistant instance
- replace placeholders before deployment
