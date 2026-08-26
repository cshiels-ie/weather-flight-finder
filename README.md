# Weather Flight Finder ✈️🌡️

A single-file React app that finds the **hottest** and **coldest** destinations within **non-stop flight range** of any city in the world.

## Features

- 📍 **Auto-detect location** via browser GPS, IP-based lookup, or pick manually
- 🔍 **City picker** with search (Open-Meteo geocoding API)
- ✈️ **Flight distance filter** — slider to set max non-stop range (500 – 16,000 km)
- 📏 **Haversine distances** shown on every destination card
- 🌡️ **Real-time weather** for your location and **70+ major cities** in one batched API call
- 🔥 **Hottest destination** card
- ❄️ **Coldest destination** card
- 🌍 **Destinations grid** sorted by temperature with distance & temp bars
- 🎨 Dark gradient UI with Tailwind CSS
- 📱 Mobile responsive
- 🌡️ All temperatures in **°C**

## How it works

1. Detects (or you pick) your current location
2. Fetches current weather + all 70+ destinations' weather in **one batched call** to [Open-Meteo](https://open-meteo.com/)
3. Computes great-circle distance (haversine) from you to every destination
4. Filters to destinations within your chosen flight range (with nearest-fallback if too few)
5. Ranks the survivors by temperature and surfaces the hottest and coldest

## Run it

No build step. Just open `index.html` in a browser, or serve it with any static server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## APIs used

- [Open-Meteo Forecast API](https://open-meteo.com/) — weather data (batched, one call)
- [Open-Meteo Geocoding API](https://open-meteo.com/) — city search
- [ipapi.co](https://ipapi.co/) — IP-based geolocation fallback
- [OpenStreetMap Nominatim](https://nominatim.org/) — reverse geocoding

All free, no API keys required.

## License

MIT
