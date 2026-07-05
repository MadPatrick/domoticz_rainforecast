@ -7,7 +7,8 @@ devices:
- **Neerslag**: a Domoticz Rain device with the current rain value and the
  accumulated total.
- **Buienradar**: a text device with a short, readable forecast, the current
  temperature, weather description, wind direction, and Beaufort wind force.
  Buienradar weather icon, temperature, weather description, wind direction,
  and Beaufort wind force.
- **Temperature**: a Domoticz Temperature device with the nearest Buienradar
  station temperature.

@ -26,7 +27,7 @@ Depending on the data, the text device may show messages such as:
- `Het regent nu 0.8 mm`
- `Regen verwacht 1.2 mm`
- `2.4 mm regen verwacht om 14:35`
- `Voorlopig droog - 19,7°C - Zwaar bewolkt NW4`
- `Voorlopig droog <img src="..."> - 19,7°C - Zwaar bewolkt NW4`

The Rain device is also updated with:

@ -92,7 +93,7 @@ not already exist:
| Unit | Device | Type | Purpose |
| --- | --- | --- | --- |
| 1 | Neerslag | Rain | Current rain and accumulated total |
| 2 | Buienradar | Text | Readable rain forecast with temperature, weather description, and wind |
| 2 | Buienradar | Text | Readable rain forecast with weather icon, temperature, weather description, and wind |
| 3 | Temperature | Temperature | Current temperature from the nearest Buienradar station |

You do not need to create these devices manually.
@ -104,9 +105,9 @@ You do not need to create these devices manually.
2. The plugin creates the required devices if they do not already exist.
3. A first measurement is performed immediately on startup.
4. After that, the plugin periodically retrieves new data from Buienradar.
5. The Buienradar JSON feed is used for the nearest station temperature,
   weather description, wind direction, and Beaufort wind force, with
   `fivedayforecast` as fallback for missing description data.
5. The Buienradar JSON feed is used for the nearest station weather icon,
   temperature, weather description, wind direction, and Beaufort wind force,
   with `fivedayforecast` as fallback for missing icon or description data.
6. The raw Buienradar values are converted to mm/hour.
7. The plugin integrates the 5-minute forecast values over the configured poll
   interval to estimate the amount of rain since the previous poll.
