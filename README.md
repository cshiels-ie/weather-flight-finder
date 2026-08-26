# Weather Flight Finder ✈️🌡️

A single-file React app that finds the **hottest** and **coldest** destinations within **flight range** of any city in the world.

## Features

- 📍 **Auto-detect location** via browser GPS, IP-based lookup, or pick manually
- 🔍 **City picker** with search (Open-Meteo geocoding API)
- 🌍 **252 world capitals + major cities** — every country capital, all with coordinates, embedded in the app (no data fetch needed)
- 🇮🇪 **Emoji country flags** everywhere — derived from ISO2 codes, zero dependencies
- ✈️ **Flight distance filter** — slider to set max flight range (500 – 16,000 km)
- 📏 **Haversine distances** shown on every destination card
- 🌡️ **Real-time weather** for your location and all 252 destinations in **one batched API call**
- 🔥 **Hottest destination** card
- ❄️ **Coldest destination** card
- 🌍 **Destinations grid** sorted by temperature with distance & temp bars
- 🎨 Dark gradient UI with Tailwind CSS
- 📱 Mobile responsive
- 🌡️ All temperatures in **°C**

## How it works

1. Detects (or you pick) your current location
2. Fetches current weather + all 252 destinations' weather in **one batched call** to [Open-Meteo](https://open-meteo.com/)
3. Computes great-circle distance (haversine) from you to every destination
4. Filters to destinations within your chosen flight range (with nearest-fallback if too few)
5. Ranks the survivors by temperature and surfaces the hottest and coldest

## The capitals dataset

The 252-destination list was built by geocoding the [countriesnow.space](https://countriesnow.space/) capitals dataset through the Open-Meteo geocoding API, with manual QA fixes for ambiguous city names (Bern 🇨🇭 vs Berne Indiana 🇺🇸, Hamilton 🇧🇲 vs Hamilton Ontario 🇨🇦, etc.). Each entry has an ISO2 code so flags render as native emoji — no flag image API needed.

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
