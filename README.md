# Weather Quarter | هواشناسی چهارتکه

A weather and air-quality dashboard drawn as two quarter-circle gauge clusters, in the same style as the Quarter Clock. Everything is read from the hands and arcs.
داشبورد هوا و کیفیت هوا با کمان‌های ربع‌دایره و عقربه، هم‌سبک ساعت چهارتکه.

## Gauges | کمان‌ها

**Top-right corner | گوشهٔ بالا-راست**
- **Air quality (large arc):** black hand = US AQI (scale 0–300), red hand = European AQI (scale 0–100, red labels inside the arc).
- **UV index (small arc, amber):** scale 0–12.

**Bottom-left corner | گوشهٔ پایین-چپ**
- **Temperature (large arc):** spans today's minimum to maximum. Black hand = current temperature, red hand = feels-like, red tick on the arc = dew point.
- **Humidity (small arc, blue):** 0–100%.

A legend in the free corners explains each hand. The location name is shown at the top left.

## Location | موقعیت

The page picks the location in this order:

1. `?lat=` and `?lon=` in the address, e.g. `index.html?lat=39.93&lon=32.86&name=Ankara`
2. The device's current location (the browser asks for permission once; it needs HTTPS, such as GitHub Pages)
3. The last location it saved
4. The default (Esenyurt, Istanbul), set by `LAT`, `LON` and `CITY` at the top of the script

When the device location is used, the title shows "موقعیت فعلی" (current location), not a place name.

## Features | ویژگی‌ها

- Live data from [Open-Meteo](https://open-meteo.com/) (forecast and air-quality APIs), no API key needed.
- Refreshes every 15 minutes; the last data is cached, so something still shows offline.
- Persian digits and labels; automatic light and dark theme.
- Hands move smoothly into place when the page opens.
- Installable as a web app (PWA). One HTML file, plain JavaScript and SVG, no libraries.

## Usage | نحوهٔ استفاده

Open `index.html` in a modern browser, or host the folder on GitHub Pages and add it to the home screen.

Keep these files together for install and offline support:

```
index.html
manifest.webmanifest
sw.js
icon-192.png
```

Vazirmatn loads from Google Fonts; without a connection the page falls back to Tahoma.

## Data | منبع داده

Weather and air quality: Open-Meteo. Air-quality values come from a model, so they may differ from a nearby monitoring station.

## Author

Motasem Sadeghi

## License

[MIT](LICENSE)
