# Groundsat

**See where satellites are, when they pass over a ground station, and whether the radio link would actually close, from the orbit to the margin in dB.**

**[Open groundsat.com →](https://groundsat.com)** Free, no sign-up, works in the browser.

![Groundsat: satellites, ground stations and passes on a 3-D globe](screenshots/hero.png)

## What you can do

### Track satellites and their passes
Pick from about 17,000 satellites (weather, Earth observation, CubeSats, amateur radio, GNSS…), add ground stations, and see every pass over the next day on a timeline: green where the link closes with margin, amber where it's tight, grey where the satellite is only in view.

[![ESA and NASA stations tracking weather and Earth-observation satellites](screenshots/demo-agency.png)](https://groundsat.com/#sats=44714,44057,100914,42063,57166,33591&gs=67.85713,20.96432,402,5,,,ag:esa-kiruna;35.4259,-116.88954,1001,5,,,ag:nasa-goldstone;-25.887,27.712,1545,5,,,ag:sansa-hartebeesthoek;-35.40242,148.98127,689,5,,,ag:nasa-canberra&tx=57166:8128000000:FM,33591:2247500000:BPSK)
*Demo: six satellites over ESA Kiruna, NASA Goldstone, Hartebeesthoek and Canberra.*

### A whole constellation over one station
[![All ICEYE satellites over KSAT Svalbard](screenshots/demo-iceye.png)](https://groundsat.com/#sats=43800,44390,46496,46497,56963,58288,58302,59100,59102,59103,60539,60546,60548,60549,62384,62389,62698,62700,62705,62707,63253,63255,63257,63258,64570,64572,64574,64578,64581,64584,66300,66301,66302,66751,66752,66753,66754,66755,67372,67373,68494,68496,68497,68500,68502,68504,68995,68996,69870,69889,69892,69893,100889,100894,100910,100914&gs=78.229,15.408,500,5,,,ag:ksat-svalbard)
*Demo: all 56 ICEYE satellites over KSAT's Svalbard station.*

### Use real stations, or describe your own
Over 600 active SatNOGS stations, 25 agency sites (ESA, NASA, JAXA, ISRO…) and about 150 commercial ones (KSAT, SSC, AWS, Leaf Space, ATLAS…), with their dishes and bands. Or save your own station and say exactly what it receives: whole bands or frequency ranges, each with its dish or antenna, LNA noise figure and line loss, or a measured G/T.

### See the whole link budget
Every term for a satellite and a station, now or at the next pass's peak: EIRP, path loss, gases, rain, pointing, G/T, C/N0, Eb/N0, required, margin. Each input is marked as **yours**, **listed** (published data), **assumed** (a typical value for the band) or **computed**, so you can see what's still a guess and replace it with real numbers.

### "Can I hear anything from it?"
Satellites often transmit in several bands. Each station budgets the downlink it can actually receive, or, in *any downlink* mode, every downlink it can receive (data, TT&C, beacons), counting the best.

### Share a scenario
One link carries what's on screen (satellites, your stations and their bands, your downlinks, the time and the camera) and each satellite's orbit as it was. The recipient can watch it with today's orbits or **replay it exactly as sent**, and save what they like. Signed in, you get short links too.

## How accurate is it?

- **Orbits:** SGP4/SDP4, the standard model for public orbital elements, via [satellite.js](https://github.com/shashwatak/satellite-js). Checked against Vallado's official SGP4 verification set: 32 test orbits, 666 points, agreement within **0.12 mm**. The verification runs with every build. In practice, accuracy is limited by the public elements themselves: about a kilometre at epoch, growing by a few kilometres a day.
- **Atmosphere:** ITU-R P.676 (gases), P.838 / P.839 / P.618 (rain) and sky noise, from the ITU-Rpy implementation, with reference-value tests.
- **Coding thresholds:** DVB-S2 Es/N0 thresholds and spectral efficiencies checked line by line against ETSI EN 302 307-1, Table 13.
- **What's estimated:** most satellites' transmit power and antenna gain aren't published anywhere, so typical values per band fill in until you enter real ones, always labelled. Not modelled yet: clouds, scintillation, ionospheric effects, Doppler, interference, satellite antenna patterns.

Margins are estimates. Don't use them for operational or safety decisions without independent checks.

## Privacy

No account is needed: what you add is saved in your browser. Signing in (optional, with Google) saves the same things to an account, so they're on every device: we keep your email address and your items, and nothing else. No ads, no analytics, no trackers; the page loads nothing from other sites. Details: [privacy](https://groundsat.com/privacy).

## Data and credits

Orbital elements from [CelesTrak](https://celestrak.org), refreshed every 6 hours. Transmitters and stations from [SatNOGS](https://satnogs.org) (CC BY-SA 4.0). Agency and commercial stations from their operators' published pages, cited per station. Maps: Natural Earth, NASA Blue Marble, shadedrelief.com. Globe: [CesiumJS](https://cesium.com/platform/cesiumjs/).

The full user guide is the [manual](https://groundsat.com/manual).

## Feedback

Found a bug, a wrong station, or a satellite whose radio details you know? **[Open an issue](../../issues/new)**. Questions and ideas are welcome in **[Discussions](../../discussions)**.

---

This repository holds Groundsat's documentation and issue tracker; the application's source code isn't published. The contents here are licensed under the [MIT License](LICENSE).
