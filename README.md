# Closest Open Pharmacy Finder

A lightweight, static website that helps you find the nearest pharmacies that appear to be open right now, based on a Canadian postal code.

![Screenshot placeholder](https://via.placeholder.com/800x400?text=Closest+Open+Pharmacy+Finder)

## Features

- Search by Canadian postal code (full or FSA / first 3 characters)
- Geocodes using the free Natural Resources Canada Geolocation API
- Finds nearby pharmacies from OpenStreetMap via Overpass API
- Estimates "open now" status using OSM `opening_hours` tags (parsed with opening_hours.js)
- Interactive Leaflet map with color-coded markers (green = open, red = closed, gray = unknown)
- Sorted results (open pharmacies first, then by distance)
- Fully client-side — no backend required
- Mobile-friendly UI

## Live Demo

Open `index.html` in any modern browser, or host it on GitHub Pages / Netlify / Vercel.

## How it works

1. User enters a postal code.
2. Location is resolved via [geolocator.api.geo.ca](https://geolocator.api.geo.ca/).
3. Nearby pharmacies are queried from the [Overpass API](https://overpass-api.de/).
4. Distances are calculated and results are displayed with an interactive map.

## Limitations

- Relies on community-maintained OpenStreetMap data. Opening hours are frequently incomplete or outdated.
- Postal code locations are approximate (usually the Forward Sortation Area centroid).
- "Open now" is an estimate only. Always call the pharmacy to confirm before traveling.
- Rate limits on the public Overpass and geolocation APIs may apply under heavy use.

## Disclaimer

This tool is for informational purposes only and is not a substitute for professional medical advice. In an emergency, call 911 or go to the nearest emergency department. Always verify pharmacy hours and medication availability by phone.

## Data sources

- OpenStreetMap contributors (locations & opening hours)
- Natural Resources Canada (postal code geocoding)
- Leaflet (map library)
- opening_hours.js (hours parsing)

## Local development

No build step required. Just open `index.html` in a browser.

```bash
# Optional: serve locally
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Contributing

Contributions welcome! Ideas:

- Support for other countries
- Better opening hours fallbacks
- Pharmacy chain filtering
- Dark mode
- Offline-capable PWA

## License

MIT License — see [LICENSE](LICENSE) file.
