# Changelog

<!--next-version-placeholder-->
## v1.3.0 (2026-01-21)
### Features
* Implement app operation reverse sync - Add `update_from_latest_data` method to sync device state changes from cloud/app to Home Assistant

### Improvements
* Optimize state update logic in climate.py and water_heater.py
* Remove redundant calls to `set_device_attr` to avoid duplicate state updates
* Improve cache update consistency across all control methods
* Add clearer comments for state update flow

### Technical Details
* Direct update to `device_attrs` and `_cache` in async_set_* methods
* Avoid calling `set_device_attr` which triggers redundant `update_from_latest_data` calls
* Unified state update pattern: control_device → update device_attrs → update cache → async_write_ha_state

## v1.2.4 (2024-04-05)
* [#13](https://github.com/daxingplay/home-assistant-vaillant-plus/issues/13) Support to disable IPv6 in this integration for Home Assistant version >= `2023.10.0`.
* Add Github actions for more HA versions.

## v0.6.0 (2023-05-13)
* Refactor to use new API. Resolve [#5](https://github.com/daxingplay/home-assistant-vaillant-plus/issues/5)

## v0.6.0 (2023-05-13)
### Others
* Re-tag to match HACS requirements.

## v0.5.1 (2023-05-13)
### Bug
* Fix login failed issues when auth token expired.

## v0.3.1 (2023-02-27)
### Bug
* Fix custom components cannot be installed due to dependency conflict.