# Weather Flight Finder ✈️🌡️

A single-file React app that finds the **hottest** and **coldest** direct-flight destinations from any city in the world.

## Features

- 📍 **Auto-detect location** via browser GPS, IP-based lookup, or pick manually
- 🔍 **City picker** with search (Open-Meteo geocoding API)
- 🌡️ **Real-time weather** for your location and 12 randomly-selected destinations
- 🔥 **Hottest destination** card
- ❄️ **Coldest destination** card
- 🌍 **All destinations grid** sorted by temperature
- 🎨 Beautiful dark gradient UI with Tailwind CSS
- 📱 Mobile responsive

## How it works

1. Detects (or you pick) your current location
2. Fetches current weather from [Open-Meteo](https://open-meteo.com/)
3. Picks 12 random destinations from a list of 20 popular cities
4. Fetches real-time temps for each, then ranks them
5. Surfaces the hottest and coldest

## Run it

No build step. Just open `index.html` in a browser, or serve it with any static server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## APIs used

- [Open-Meteo Forecast API](https://open-meteo.com/) — weather data
- [Open-Meteo Geocoding API](https://open-meteo.com/) — city search
- [ipapi.co](https://ipapi.co/) — IP-based geolocation fallback
- [OpenStreetMap Nominatim](https://nominatim.org/) — reverse geocoding

All free, no API keys required.

## License

MIT
