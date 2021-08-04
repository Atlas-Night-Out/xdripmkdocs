# Welcome to The Diabetic way


For full Website content visit [The Diabetic Way](https://www.thediabeticway.co.uk/index.php/en/).
<br>
<br>

## <span style="color:#111478">Nightscout Plugins </span> <br> 



<font size="4">
 
**Plugins**
Plugins are used extend the way information is displayed, how notifications are sent, alarms are triggered, and more.

The built-in/example plugins that are available by default are listed below. The plugins may still need to be enabled by adding to the ENABLE environment variable.

Default Plugins
These can be disabled by adding them to the DISABLE variable, for example DISABLE="direction upbat"

delta (BG Delta)
Calculates and displays the change between the last 2 BG values.

direction (BG Direction)
Displays the trend direction.

upbat (Uploader Battery)
Displays the most recent battery status from the uploader phone. . Use these extended setting to adjust behavior:

UPBAT_ENABLE_ALERTS (false) - Set to true to enable uploader battery alarms via Pushover and IFTTT.
UPBAT_WARN (30) - Minimum battery percent to trigger warning.
UPBAT_URGENT (20) - Minimum battery percent to trigger urgent alarm.
timeago (Time Ago)
Displays the time since last CGM entry. Use these extended setting to adjust behavior:

TIMEAGO_ENABLE_ALERTS (false) - Set to true to enable stale data alarms via Pushover and IFTTT.
ALARM_TIMEAGO_WARN (on) - possible values on or off
ALARM_TIMEAGO_WARN_MINS (15) - minutes since the last reading to trigger a warning
ALARM_TIMEAGO_URGENT (on) - possible values on or off
ALARM_TIMEAGO_URGENT_MINS (30) - minutes since the last reading to trigger a urgent alarm
devicestatus (Device Status)
Used by upbat and other plugins to display device status info. Supports the DEVICESTATUS_ADVANCED="true" extended setting to send all device statuses to the client for retrospective use and to support other plugins.

errorcodes (CGM Error Codes)
Generates alarms for CGM codes 9 (hourglass) and 10 (???).

Use extended settings to adjust what errorcodes trigger notifications and alarms:
ERRORCODES_INFO (1 2 3 4 5 6 7 8) - By default the needs calibration (blood drop) and other codes below 9 generate an info level notification, set to a space separate list of number or off to disable
ERRORCODES_WARN (off) - By default there are no warning configured, set to a space separate list of numbers or off to disable
ERRORCODES_URGENT (9 10) - By default the hourglass and ??? generate an urgent alarm, set to a space separate list of numbers or off to disable
ar2 (AR2 Forecasting)
Generates alarms based on forecasted values. See Forecasting using AR2 algorithm

Enabled by default if no thresholds are set OR ALARM_TYPES includes predict.
Use extended settings to adjust AR2 behavior:
AR2_CONE_FACTOR (2) - to adjust size of cone, use 0 for a single line.
simplealarms (Simple BG Alarms)
Uses BG_HIGH, BG_TARGET_TOP, BG_TARGET_BOTTOM, BG_LOW thresholds to generate alarms.

Enabled by default if 1 of these thresholds is set OR ALARM_TYPES includes simple.
profile (Treatment Profile)
Add link to Profile Editor and allow to enter treatment profile settings. Also uses the extended setting:

PROFILE_HISTORY (off) - possible values on or off. Enable/disable NS ability to keep history of your profiles (still experimental)
PROFILE_MULTIPLE (off) - possible values on or off. Enable/disable NS ability to handle and switch between multiple treatment profiles
Advanced Plugins:
careportal (Careportal)
An optional form to enter treatments.

boluscalc (Bolus Wizard)
food (Custom Foods)
An option plugin to enable adding foods from database in Bolus Wizard and enable .

rawbg (Raw BG)
Calculates BG using sensor and calibration records from and displays an alternate BG values and noise levels. Defaults that can be adjusted with extended setting

DISPLAY (unsmoothed) - Allows the user to control which algorithm is used to calculate the displayed raw BG values using the most recent calibration record.
unfiltered - Raw BG is calculated by applying the calibration to the glucose record's unfiltered value.
filtered - Raw BG is calculated by applying the calibration to the glucose record's filtered value. The glucose record's filtered values are generally produced by the CGM by a running average of the unfiltered values to produce a smoothed value when the sensor noise is high.
unsmoothed - Raw BG is calculated by first finding the ratio of the calculated filtered value (the same value calculated by the filtered setting) to the reported glucose value. The displayed raw BG value is calculated by dividing the calculated unfiltered value (the same value calculated by the unfiltered setting) by the ratio. The effect is to exagerate changes in trend direction so the trend changes are more noticeable to the user. This is the legacy raw BG calculation algorithm.
iob (Insulin-on-Board)
Adds the IOB pill visualization in the client and calculates values that used by other plugins. Uses treatments with insulin doses and the dia and sens fields from the treatment profile.

cob (Carbs-on-Board)
Adds the COB pill visualization in the client and calculates values that used by other plugins. Uses treatments with carb doses and the carbs_hr, carbratio, and sens fields from the treatment profile.

bwp (Bolus Wizard Preview)
This plugin in intended for the purpose of automatically snoozing alarms when the CGM indicates high blood sugar but there is also insulin on board (IOB) and secondly, alerting to user that it might be beneficial to measure the blood sugar using a glucometer and dosing insulin as calculated by the pump or instructed by trained medicare professionals. The values provided by the plugin are provided as a reference based on CGM data and insulin sensitivity you have configured, and are not intended to be used as a reference for bolus calculation. The plugin calculates the bolus amount when above your target, generates alarms when you should consider checking and bolusing, and snoozes alarms when there is enough IOB to cover a high BG. Uses the results of the iob plugin and sens, target_high, and target_low fields from the treatment profile. Defaults that can be adjusted with extended setting

BWP_WARN (0.50) - If BWP is > BWP_WARN a warning alarm will be triggered.
BWP_URGENT (1.00) - If BWP is > BWP_URGENT an urgent alarm will be triggered.
BWP_SNOOZE_MINS (10) - minutes to snooze when there is enough IOB to cover a high BG.
BWP_SNOOZE - (0.10) If BG is higher then the target_high and BWP < BWP_SNOOZE alarms will be snoozed for BWP_SNOOZE_MINS.
cage (Cannula Age)
Calculates the number of hours since the last Site Change treatment that was recorded.

CAGE_ENABLE_ALERTS (false) - Set to true to enable notifications to remind you of upcoming cannula change.
CAGE_INFO (44) - If time since last Site Change matches CAGE_INFO, user will be warned of upcoming cannula change
CAGE_WARN (48) - If time since last Site Change matches CAGE_WARN, user will be alarmed to to change the cannula
CAGE_URGENT (72) - If time since last Site Change matches CAGE_URGENT, user will be issued a persistent warning of overdue change.
CAGE_DISPLAY (hours) - Possible values are 'hours' or 'days'. If 'days' is selected and age of canula is greater than 24h number is displayed in days and hours
sage (Sensor Age)
Calculates the number of days and hours since the last Sensor Start and Sensor Change treatment that was recorded.

SAGE_ENABLE_ALERTS (false) - Set to true to enable notifications to remind you of upcoming sensor change.
SAGE_INFO (144) - If time since last sensor event matches SAGE_INFO, user will be warned of upcoming sensor change
SAGE_WARN (164) - If time since last sensor event matches SAGE_WARN, user will be alarmed to to change/restart the sensor
SAGE_URGENT (166) - If time since last sensor event matches SAGE_URGENT, user will be issued a persistent warning of overdue change.
iage (Insulin Age)
Calculates the number of days and hours since the last Insulin Change treatment that was recorded.

IAGE_ENABLE_ALERTS (false) - Set to true to enable notifications to remind you of upcoming insulin reservoir change.
IAGE_INFO (44) - If time since last Insulin Change matches IAGE_INFO, user will be warned of upcoming insulin reservoir change
IAGE_WARN (48) - If time since last Insulin Change matches IAGE_WARN, user will be alarmed to to change the insulin reservoir
IAGE_URGENT (72) - If time since last Insulin Change matches IAGE_URGENT, user will be issued a persistent warning of overdue change.
bage (Battery Age)
Calculates the number of days and hours since the last Pump Battery Change treatment that was recorded.

BAGE_ENABLE_ALERTS (false) - Set to true to enable notifications to remind you of upcoming pump battery change.
BAGE_DISPLAY (days) - Set to hours to display time since last Pump Battery Change in hours only.
BAGE_INFO (312) - If time since last Pump Battery Change matches BAGE_INFO hours, user will be warned of upcoming pump battery change (default of 312 hours is 13 days).
BAGE_WARN (336) - If time since last Pump Battery Change matches BAGE_WARN hours, user will be alarmed to to change the pump battery (default of 336 hours is 14 days).
BAGE_URGENT (360) - If time since last Pump Battery Change matches BAGE_URGENT hours, user will be issued a persistent warning of overdue change (default of 360 hours is 15 days).
treatmentnotify (Treatment Notifications)
Generates notifications when a treatment has been entered and snoozes alarms minutes after a treatment.

TREATMENTNOTIFY_SNOOZE_MINS (10) - Number of minutes to snooze notifications after a treatment is entered
TREATMENTNOTIFY_INCLUDE_BOLUSES_OVER (0) - U value over which the bolus will trigger a notification and snooze alarms
basal (Basal Profile)
Adds the Basal pill visualization to display the basal rate for the current time. Also enables the bwp plugin to calculate correction temp basal suggestions. Uses the basal field from the treatment profile. Also uses the extended setting:

BASAL_RENDER (none) - Possible values are none, default, or icicle (inverted)
bolus (Bolus Rendering)
Settings to configure Bolus rendering

BOLUS_RENDER_OVER (0) - U value over which the bolus labels use the format defined in BOLUS_RENDER_FORMAT. This value can be an integer or a float, e.g. 0.3, 1.5, 2, etc.
BOLUS_RENDER_FORMAT (default) - Possible values are hidden, default (with leading zero and U), concise (with U, without leading zero), and minimal (without leading zero and U).
BOLUS_RENDER_FORMAT_SMALL (default) - Possible values are hidden, default (with leading zero and U), concise (with U, without leading zero), and minimal (without leading zero and U).
bridge (Share2Nightscout bridge)
Glucose reading directly from the Dexcom Share service, uses these extended settings:

BRIDGE_USER_NAME - Your username for the Share service.
BRIDGE_PASSWORD - Your password for the Share service.
BRIDGE_INTERVAL (150000 2.5 minutes) - The time (in milliseconds) to wait between each update.
BRIDGE_MAX_COUNT (1) - The number of records to attempt to fetch per update.
BRIDGE_FIRST_FETCH_COUNT (3) - Changes max count during the very first update only.
BRIDGE_MAX_FAILURES (3) - How many failures before giving up.
BRIDGE_MINUTES (1400) - The time window to search for new data per update (the default value is one day in minutes).
BRIDGE_SERVER (``) - The default blank value is used to fetch data from Dexcom servers in the US. Set to (EU) to fetch from European servers instead.
mmconnect (MiniMed Connect bridge)
Transfer real-time MiniMed Connect data from the Medtronic CareLink server into Nightscout (read more)

MMCONNECT_USER_NAME - Your user name for CareLink Connect.
MMCONNECT_PASSWORD - Your password for CareLink Connect.
MMCONNECT_INTERVAL (60000 1 minute) - Number of milliseconds to wait between requests to the CareLink server.
MMCONNECT_MAX_RETRY_DURATION (32) - Maximum number of total seconds to spend retrying failed requests before giving up.
MMCONNECT_SGV_LIMIT (24) - Maximum number of recent sensor glucose values to send to Nightscout on each request.
MMCONNECT_VERBOSE - Set this to "true" to log CareLink request information to the console.
MMCONNECT_STORE_RAW_DATA - Set this to "true" to store raw data returned from CareLink as type: "carelink_raw" database entries (useful for development).
MMCONNECT_SERVER - Set this to EU if you're using the European Medtronic services
pump (Pump Monitoring)
Generic Pump Monitoring for OpenAPS, MiniMed Connect, RileyLink, t:slim, with more on the way

Requires DEVICESTATUS_ADVANCED="true" to be set
PUMP_ENABLE_ALERTS (false) - Set to true to enable notifications for Pump battery and reservoir.
PUMP_WARN_ON_SUSPEND (false) - Set to true to get an alarm when the pump is suspended.
PUMP_FIELDS (reservoir battery) - The fields to display by default. Any of the following fields: reservoir, battery, clock, status, and device
PUMP_RETRO_FIELDS (reservoir battery clock) - The fields to display in retro mode. Any of the above fields.
PUMP_WARN_CLOCK (30) - The number of minutes ago that needs to be exceed before an alert is triggered.
PUMP_URGENT_CLOCK (60) - The number of minutes ago that needs to be exceed before an urgent alarm is triggered.
PUMP_WARN_RES (10) - The number of units remaining, a warning will be triggered when dropping below this threshold.
PUMP_URGENT_RES (5) - The number of units remaining, an urgent alarm will be triggered when dropping below this threshold.
PUMP_WARN_BATT_P (30) - The % of the pump battery remaining, a warning will be triggered when dropping below this threshold.
PUMP_URGENT_BATT_P (20) - The % of the pump battery remaining, an urgent alarm will be triggered when dropping below this threshold.
PUMP_WARN_BATT_V (1.35) - The voltage (if percent isn't available) of the pump battery, a warning will be triggered when dropping below this threshold.
PUMP_URGENT_BATT_V (1.30) - The voltage (if percent isn't available) of the pump battery, an urgent alarm will be triggered when dropping below this threshold.
PUMP_WARN_BATT_QUIET_NIGHT (false) - Do not generate battery alarms at night.
openaps (OpenAPS)
Integrated OpenAPS loop monitoring, uses these extended settings:

Requires DEVICESTATUS_ADVANCED="true" to be set
OPENAPS_ENABLE_ALERTS (false) - Set to true to enable notifications when OpenAPS isn't looping. If OpenAPS is going to offline for a period of time, you can add an OpenAPS Offline event for the expected duration from Careportal to avoid getting alerts.
OPENAPS_WARN (30) - The number of minutes since the last loop that needs to be exceed before an alert is triggered
OPENAPS_URGENT (60) - The number of minutes since the last loop that needs to be exceed before an urgent alarm is triggered
OPENAPS_FIELDS (status-symbol status-label iob meal-assist rssi) - The fields to display by default. Any of the following fields: status-symbol, status-label, iob, meal-assist, freq, and rssi
OPENAPS_RETRO_FIELDS (status-symbol status-label iob meal-assist rssi) - The fields to display in retro mode. Any of the above fields.
OPENAPS_PRED_IOB_COLOR (#1e88e5) - The color to use for IOB prediction lines. Colors can be in #RRGGBB format, but other CSS color units may be used as well.
OPENAPS_PRED_COB_COLOR (#FB8C00) - The color to use for COB prediction lines. Same format as above.
OPENAPS_PRED_ACOB_COLOR (#FB8C00) - The color to use for ACOB prediction lines. Same format as above.
OPENAPS_PRED_ZT_COLOR (#00d2d2) - The color to use for ZT prediction lines. Same format as above.
OPENAPS_PRED_UAM_COLOR (#c9bd60) - The color to use for UAM prediction lines. Same format as above.
OPENAPS_COLOR_PREDICTION_LINES (true) - Enables / disables the colored lines vs the classic purple color.
Also see Pushover and IFTTT Maker.

loop (Loop)
iOS Loop app monitoring, uses these extended settings:

Requires DEVICESTATUS_ADVANCED="true" to be set
LOOP_ENABLE_ALERTS (false) - Set to true to enable notifications when Loop isn't looping.
LOOP_WARN (30) - The number of minutes since the last loop that needs to be exceeded before an alert is triggered
LOOP_URGENT (60) - The number of minutes since the last loop that needs to be exceeded before an urgent alarm is triggered
Add loop to SHOW_FORECAST to show forecasted BG.
For remote overrides, the following extended settings must be configured:

LOOP_APNS_KEY - Apple Push Notifications service (APNs) Key, created in the Apple Developer website.
LOOP_APNS_KEY_ID - The Key ID for the above key.
LOOP_DEVELOPER_TEAM_ID - Your Apple developer team ID.
LOOP_PUSH_SERVER_ENVIRONMENT - (optional) Set this to production if you are using a provisioning profile that specifies production aps-environment, such as when distributing builds via TestFlight.
override (Override Mode)
Additional monitoring for DIY automated insulin delivery systems to display real-time overrides such as Eating Soon or Exercise Mode:

Requires DEVICESTATUS_ADVANCED="true" to be set
xdripjs (xDrip-js)
Integrated xDrip-js monitoring, uses these extended settings:

Requires DEVICESTATUS_ADVANCED="true" to be set
XDRIPJS_ENABLE_ALERTS (false) - Set to true to enable notifications when CGM state is not OK or battery voltages fall below threshold.
XDRIPJS_STATE_NOTIFY_INTRVL (0.5) - Set to number of hours between CGM state notifications
XDRIPJS_WARN_BAT_V (300) - The voltage of either transmitter battery, a warning will be triggered when dropping below this threshold.
alexa (Amazon Alexa)
Integration with Amazon Alexa, detailed setup instructions

googlehome (Google Home/DialogFLow)
Integration with Google Home (via DialogFlow), detailed setup instructions

speech (Speech)
Speech synthesis plugin. When enabled, speaks out the blood glucose values, IOB and alarms. Note you have to set the LANGUAGE setting on the server to get all translated alarms.

cors (CORS)
Enabled CORS so other websites can make request to your Nightscout site, uses these extended settings:

CORS_ALLOW_ORIGIN (*) - The list of sites that are allow to make requests
dbsize (Database Size)
Show size of Nightscout Database, as a percentage of declared available space or in MiB.

Many deployments of Nightscout use free tier of MongoDB Atlas on Heroku, which is limited in size. After some time, as volume of stored data grows, it may happen that this limit is reached and system is unable to store new data. This plugin provides pill that indicates size of Database and shows (when configured) alarms regarding reaching space limit.

IMPORTANT: This plugin can only check how much space database already takes, but cannot infer max size available on server for it. To have correct alarms and realistic percentage, DBSIZE_MAX need to be properly set - according to your mongoDB hosting configuration.

NOTE: This plugin rely on db.stats() for reporting logical size of database, which may be different than physical size of database on server. It may work for free tier of MongoDB on Atlas, since it calculate quota according to logical size too, but may fail for other hostings or self-hosted database with quota based on physical size.

NOTE: MongoDB Atlas quota is for all databases in cluster, while each instance will get only size of its own database only. It is ok when you only have one database in cluster (most common scenario) but will not work for multiple parallel databases. In such case, spliting known quota equally beetween databases and setting DBSIZE_MAX to that fraction may help, but wont be precise.

All sizes are expressed as integers, in Mebibytes 1 MiB == 1024 KiB == 1024*1024 B

DBSIZE_MAX (496) - Maximal allowed size of database on your mongoDB server, in MiB. You need to adjust that value to match your database hosting limits - default value is for standard Heroku mongoDB free tier.
DBSIZE_WARN_PERCENTAGE (60) - Threshold to show first warning about database size. When database reach this percentage of DBSIZE_MAX size - pill will show size in yellow.
DBSIZE_URGENT_PERCENTAGE (75) - Threshold to show urgent warning about database size. When database reach this percentage of DBSIZE_MAX size, it is urgent to do backup and clean up old data. At this percentage info pill turns red.
DBSIZE_ENABLE_ALERTS (false) - Set to true to enable notifications about database size.
DBSIZE_IN_MIB (false) - Set to true to display size of database in MiB-s instead of default percentage.
This plugin should be enabled by default, if needed can be diasabled by adding dbsize to the list of disabled plugins, for example: DISABLE="dbsize".

Extended Settings
Some plugins support additional configuration using extra environment variables. These are prefixed with the name of the plugin and a _. For example setting MYPLUGIN_EXAMPLE_VALUE=1234 would make extendedSettings.exampleValue available to the MYPLUGIN plugin.

Plugins only have access to their own extended settings, all the extended settings of client plugins will be sent to the browser.

DEVICESTATUS_ADVANCED (true) - Defaults to true. Users who only have a single device uploading data to Nightscout can set this to false to reduce the data use of the site.
DEVICESTATUS_DAYS (1) - Defaults to 1, can optionally be set to 2. Users can use this to show 48 hours of device status data for in retro mode, rather than the default 24 hours. Setting this value to 2 will roughly double the bandwidth usage of nightscout, so users with a data cap may not want to update this setting.
Pushover
In addition to the normal web based alarms, there is also support for Pushover based alarms and notifications.

To get started install the Pushover application on your iOS or Android device and create an account.

Using that account login to Pushover, in the top left you’ll see your User Key, you’ll need this plus an application API Token/Key to complete this setup.

You’ll need to Create a Pushover Application. You only need to set the Application name, you can ignore all the other settings, but setting an Icon is a nice touch. Maybe you'd like to use this one?

Pushover is configured using the following Environment Variables:

* `ENABLE` - `pushover` should be added to the list of plugin, for example: `ENABLE="pushover"`.
* `PUSHOVER_API_TOKEN` - Used to enable pushover notifications, this token is specific to the application you create from in [Pushover](https://pushover.net/), ***[additional pushover information](#pushover)*** below.
* `PUSHOVER_USER_KEY` - Your Pushover user key, can be found in the top left of the [Pushover](https://pushover.net/) site, this can also be a pushover delivery group key to send to a group rather than just a single user.  This also supports a space delimited list of keys.  To disable `INFO` level pushes set this to `off`.
* `PUSHOVER_ALARM_KEY` - An optional Pushover user/group key, will be used for system wide alarms (level > `WARN`).  If not defined this will fallback to `PUSHOVER_USER_KEY`.  A possible use for this is sending important messages and alarms to a CWD that you don't want to send all notification too.  This also support a space delimited list of keys.  To disable Alarm pushes set this to `off`.
* `PUSHOVER_ANNOUNCEMENT_KEY` - An optional Pushover user/group key, will be used for system wide user generated announcements.  If not defined this will fallback to `PUSHOVER_USER_KEY` or `PUSHOVER_ALARM_KEY`.  This also support a space delimited list of keys. To disable Announcement pushes set this to `off`.
* `BASE_URL` - Used for pushover callbacks, usually the URL of your Nightscout site, use https when possible.
* `API_SECRET` - Used for signing the pushover callback request for acknowledgments.

If you never want to get info level notifications (treatments) use `PUSHOVER_USER_KEY="off"`
If you never want to get an alarm via pushover use `PUSHOVER_ALARM_KEY="off"`
If you never want to get an announcement via pushover use `PUSHOVER_ANNOUNCEMENT_KEY="off"`

If only `PUSHOVER_USER_KEY` is set it will be used for all info notifications, alarms, and announcements

For testing/development try [localtunnel](http://localtunnel.me/).
IFTTT Maker
In addition to the normal web based alarms, and pushover, there is also integration for IFTTT Webhooks.

With Maker you are able to integrate with all the other IFTTT Services. For example you can send a tweet when there is an alarm, change the color of hue light, send an email, send and sms, and so much more.

Setup IFTTT account: login or create an account
Follow the Detailed IFTTT setup Instructions
Configure Nightscout by setting these webpage environment variables:
ENABLE - maker should be added to the list of plugins, for example: ENABLE="maker".
MAKER_KEY - Set this to your secret key (see [Detailed Instructions ) MAKER_KEY="abcMyExampleabc123defjt1DeNSiftttmak-XQb69p" This also supports a space delimited list of keys.
MAKER_ANNOUNCEMENT_KEY - An optional Maker key, will be used for system wide user generated announcements. If not defined this will fallback to MAKER_KEY. A possible use for this is sending important messages and alarms to another device that you don't want to send all notification too. This also support a space delimited list of keys.
Plugins can create custom events, but all events sent to IFTTT webhooks will be prefixed with ns-. The core events are:

ns-event - This event is sent to the maker service for all alarms and notifications. This is good catch all event for general logging.
ns-allclear - This event is sent to the maker service when an alarm has been ack'd or when the server starts up without triggering any alarms. For example, you could use this event to turn a light to green.
ns-info - Plugins that generate notifications at the info level will cause this event to also be triggered. It will be sent in addition to ns-event.
ns-warning - Alarms at the warning level with cause this event to also be triggered. It will be sent in addition to ns-event.
ns-urgent - Alarms at the urgent level with cause this event to also be triggered. It will be sent in addition to ns-event.
see the full list of events
Treatment Profile
Some of the plugins make use of a treatment profile that can be edited using the Profile Editor, see the link in the Settings drawer on your site.

Treatment Profile Fields:

timezone (Time Zone) - time zone local to the patient. Should be set.
units (Profile Units) - blood glucose units used in the profile, either "mg/dl" or "mmol"
dia (Insulin duration) - value should be the duration of insulin action to use in calculating how much insulin is left active. Defaults to 3 hours.
carbs_hr (Carbs per Hour) - The number of carbs that are processed per hour, for more information see #DIYPS.
carbratio (Carb Ratio) - grams per unit of insulin.
sens (Insulin sensitivity) How much one unit of insulin will normally lower blood glucose.
basal The basal rate set on the pump.
target_high - Upper target for correction boluses.
target_low - Lower target for correction boluses.
Some example profiles are here.









</font>




  <!--  
  
  mkdocs.yml    # The configuration file.
    docs/
    index.md  # The documentation homepage.
       ...       # Other markdown pages, images and other files.
		
		
		
<a href="http://nightscout.github.io/pages/update-fork/" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/Time to Update Nightscout.png" title="Update Tool"/></a>		
		
		
adding 	Yellow Hightligher!!!!!!!!	
<span style="background-color: #FFFF00">**Marked text**</span>


<a>
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/Time to Update Nightscout.png" title="Update Tool"/></a>	




Adding a image
<a href="https://www.youtube.com/watch?v=MFsbm45b6YY" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/nightscout version_14.06.jpg" title="Version of Nightscout Video"/>
</a>


Adding Video

<iframe width="850" height="415" src="https://www.youtube.com/embed/MFsbm45b6YY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>




-->

