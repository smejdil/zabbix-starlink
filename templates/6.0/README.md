
# Starlink

## Overview

For Zabbix version: 6.0 and higher  
The template to monitor Starlink dish by Zabbix that work with any external starlink-grpc-tools.

This template was tested on:

- starlink-grpc-tools in FreeBSD and Docker version starlink-grpc-tools.

## Setup

- 

## Zabbix configuration

No specific Zabbix configuration is required.

### Macros used

|Name|Description|Default|
|----|-----------|-------|
|{$STARLINK.PORT}|<p>8080</p> |`CHANGE_IF_NEEDED` |
|{$STARLINK.SCHEME}|<p>http</p> |`CHANGE_IF_NEEDED` |

## Template links

There are no template links in this template.

## Discovery rules

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|-|<p>-</p>|-|<p>-</p>|

## Items collected

|Group|Name|Description|Type|Key and additional info|
|-----|----|-----------|----|---------------------|
|Starlink |Starlink uptime|<p>The amount of time, in seconds, since the user terminal last rebooted. Starlink uptime in 'N days, hh:mm:ss' format.</p>| DEPENDENT |starlink.uptime<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_uptime_seconds`</p>|
|Starlink |Starlink uplink throughput bps|<p>Most recent sample value. See bulk history data for detail.</p>| DEPENDENT |starlink.uplink<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_uplink_throughput_bps`</p>|
|Starlink |Starlink status alert unexpected location|<p>Alert corresponding with bit 3 (bit mask 8) in *alerts*.</p>| DEPENDENT |starlink.status_alert_unexpected_location<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_unexpected_location`</p>|
|Starlink |Starlink status alert thermal throttle|<p>Alert corresponding with bit 2 (bit mask 4) in *alerts*.</p>| DEPENDENT |starlink.status_alert_thermal_throttle<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_thermal_throttle`</p>|
|Starlink |Starlink status alert thermal shutdown|<p>Alert corresponding with bit 1 (bit mask 2) in *alerts*.</p>| DEPENDENT |starlink.status_alert_thermal_shutdown<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_thermal_shutdown`</p>|
|Starlink |Starlink status alert slow ethernet speeds|<p>Alert corresponding with bit 5 (bit mask 32) in *alerts*.</p>| DEPENDENT |starlink.status_alert_slow_ethernet_speeds<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_slow_ethernet_speeds`</p>|
|Starlink |Starlink status alert roaming|<p></p>| DEPENDENT |starlink.status_alert_roaming<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_roaming`</p>|
|Starlink |Starlink status alert power supply thermal throttle|<p>Alert corresponding with bit 9 (bit mask 512) in *alerts*.</p>| DEPENDENT |starlink.status_alert_power_supply_thermal_throttle<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_power_supply_thermal_throttle`</p>|
|Starlink |Starlink status alert motors stuck|<p>Alert corresponding with bit 0 (bit mask 1) in *alerts*.</p>| DEPENDENT |starlink.status_alert_motors_stuck<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_motors_stuck`</p>|
|Starlink |Starlink status alert mast not near vertical|<p>Alert corresponding with bit 4 (bit mask 16) in *alerts*.</p>| DEPENDENT |starlink.status_alert_mast_not_near_vertical<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_mast_not_near_vertical`</p>|
|Starlink |Starlink status alert is heating|<p>Alert corresponding with bit 8 (bit mask 256) in *alerts*.</p>| DEPENDENT |starlink.status_alert_is_heating<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_is_heating`</p>|
|Starlink |Starlink status alert install pending|<p>Alert corresponding with bit 7 (bit mask 128) in *alerts*.</p>| DEPENDENT |starlink.status_alert_install_pending<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alert_install_pending`</p>|
|Starlink |Starlink state|<p>As string describing the current connectivity state of the user terminal. One of:<br>"UNKNOWN", "CONNECTED", "BOOTING", "SEARCHING", "STOWED", "THERMAL_SHUTDOWN", "NO_SATS", "OBSTRUCTED", "NO_DOWNLINK", "NO_PINGS"</p>| DEPENDENT |starlink.state<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_state`</p>|
|Starlink |Starlink software version|<p>A string identifying the software currently installed on the user terminal.</p>| DEPENDENT |starlink.software_version<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_info - label: software_version`</p>|
|Starlink |Starlink snr above noise floor|<p>Most recent sample value. See bulk history data for detail.<br>**OBSOLETE**: The user terminal no longer provides this data.</p>| DEPENDENT |starlink.snr_above_noise_floor<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_is_snr_above_noise_floor`</p>|
|Starlink |Starlink seconds to first nonempty slot|<p>Amount of time from now, in seconds, until a satellite will be scheduled to be available for transmit/receive. See also *scheduled* in the bulk history data. May report as a negative number, which appears to indicate unknown time until next satellite scheduled and usually correlates with *state* reporting as other than "CONNECTED".</p>| DEPENDENT |starlink.seconds_to_first_nonempty_slot<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_seconds_to_first_nonempty_slot`</p>|
|Starlink |Starlink seconds obstructed|<p>The amount of time within the history buffer, in seconds, that the user terminal determined to be obstructed, regardless of whether or not packets were able to be transmitted or received.<br>**OBSOLETE**: The user terminal no longer provides this data.</p>| DEPENDENT |starlink.seconds_obstructed<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_seconds_obstructed`</p>|
|Starlink |Starlink pop ping drop rate|<p>Most recent sample value. See bulk history data for detail.</p>| DEPENDENT |starlink.pop_ping_drop_rate<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_pop_ping_drop_rate`</p>|
|Starlink |Starlink ping latency|<p>Most recent sample value. See bulk history data for detail.</p>| DEPENDENT |starlink.ping_latency<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_pop_ping_latency_ms`</p>|
|Starlink |Starlink obstruction interval|<p>Average time, in seconds, between the start of such "prolonged" obstructions, or None if no such obstructions were recorded.</p>| DEPENDENT |starlink.obstruction_interval<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_obstruction_interval`</p>|
|Starlink |Starlink obstruction duration|<p>Average consecutive time, in seconds, the user terminal has detected its signal to be obstructed for a period of time that it considers "prolonged", or None if no such obstructions were recorded.</p>| DEPENDENT |starlink.obstruction_duration<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_obstruction_duration`</p>|
|Starlink |Starlink ID|<p>A string identifying the specific user terminal device that was reachable from the local network. Something like a serial number.</p>| DEPENDENT |starlink.id<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_info - label id`</p>|
|Starlink |Starlink hardware version|<p>A string identifying the user terminal hardware version.</p>| DEPENDENT |starlink.hardware_version<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_info - label hardware_version`</p>|
|Starlink |Starlink fraction obstructed|<p>The fraction of total area (or possibly fraction of time?) that the user terminal has determined to be obstructed between it and the satellites with which it communicates.</p>| DEPENDENT |starlink.fraction_obstructed<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_fraction_obstructed`</p>|
|Starlink |Starlink downlink throughput bps|<p>Most recent sample value. See bulk history data for detail.</p>| DEPENDENT |starlink.downlink<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_downlink_throughput_bps`</p>|
|Starlink |Starlink direction elevation|<p>Elevation angle, in degrees, of the direction in which the user terminal's dish antenna is physically pointing.</p>| DEPENDENT |starlink.direction_elevation<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_direction_elevation`</p>|
|Starlink |Starlink direction azimuth|<p>Azimuth angle, in degrees, of the direction in which the user terminal's dish antenna is physically pointing. Note that this generally is not the exact direction of the satellite with which the user terminal is communicating.</p>| DEPENDENT |starlink.direction_azimuth<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_direction_azimuth`</p>|
|Starlink |Starlink currently obstructed|<p>Most recent sample value. See *obstructed* in bulk history data for detail. This item still appears to be reported by the user terminal despite no longer appearing in the bulk history data.</p>| DEPENDENT |starlink.currently_obstructed<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_currently_obstructed`</p>|
|Starlink |Starlink alerts|<p>A bit field combining all active alerts, where a 1 bit indicates the alert is active. See alert detail status data for which bits correspond with each alert, or to get individual alert flags instead of a combined bit mask.</p>| DEPENDENT |starlink.alerts<p>**Preprocessing**:</p><p>- PROMETHEUS_PATTERN: `starlink_status_alerts`</p>|
|Zabbix raw items |Starlink: Get dish data|Getting data from a starlink prometeus exporter - Python project starlink-grpc-tools.| HTTP_AGENT |zbx.starlink.dish.data|

## Triggers

|Name|Description|Expression|Severity|Dependencies and additional info|
|----|-----------|----|----|----|
|Starlink alert|<p>Starlink alert. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.alerts,#3)>0`|Information|<p>Template_OT_Starlink_dish_prom: Starlink alert install pending</p>|
|Starlink alert install pending|<p>Starlink alert install pending. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.status_alert_install_pending,#3)=1`|Warning|<p>-</p>|
|Starlink alert motors stuck|<p>Starlink alert motors stuck. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.status_alert_motors_stuck,#3)=1`|High|<p>-</p>|
|Starlink alert Terminal is heating|<p>Starlink alert Terminal is heating. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.status_alert_is_heating,#3)=1`|Information|<p>-</p>|
|Starlink alert Terminal mast not near vertical|<p>Starlink alert Terminal mast not near vertical. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.status_alert_mast_not_near_vertical,#3)=1`|Warning|<p>-</p>|
|Starlink firmware has changed|<p>Firmware version has changed. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.software_version,#1)<>last(/Template_OT_Starlink_dish_prom/starlink.software_version,#2) and length(last(/Template_OT_Starlink_dish_prom/starlink.software_version))>0`|Informarion|<p>-</p>|
|Starlink status has changed|<p>Status has changed. Ack to close</p>|`last(/Template_OT_Starlink_dish_prom/starlink.state,#1)<>last(/Template_OT_Starlink_dish_prom/starlink.state,#2) and length(last(/Template_OT_Starlink_dish_prom/starlink.state))>0`|Average|<p>-</p>|
|starlink_exporter is not available (or no data for 30m)|<p>Failed to fetch starlink metrics from starlink_exporter in time.</p>|`nodata(/Template_OT_Starlink_dish_prom/zbx.starlink.dish.data,30)=1`|High|<p>-</p>|
|{HOST.NAME} has been restarted (uptime < 10m)|<p>Uptime is less than 10 minutes</p>|`last(/Template_OT_Starlink_dish_prom/starlink.uptime)<10m`|Warning|<p>-</p>|

## Feedback

Please report any issues with the template at https://open-tech.cz
