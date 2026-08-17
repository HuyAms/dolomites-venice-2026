# 2. Leaflet and OpenStreetMap for the in-page map, not Google Maps

Date: 2026-08-17

## Status

Accepted

## Context

The group asked for a map, and mentioned Google Maps specifically. Their sheet
links a "Google Map Itinerary" in cell B1, but that URL was not available and
may not exist in a shareable form.

The map has to show a seven-day trip whose whole point is *where things are
relative to each other* — why Brunico makes Wednesday cheap, why Thursday's exit
via Cortina is a line south rather than a doubling-back, why Alpe di Siusi is
reached from Seis and not from Ortisei. That means one map with day layers, not
seven embeds.

Constraints on delivery: the document is a single self-contained HTML file
served as a static page, with no build step, no server and no secrets store.

## Decision

Render the map in-page with **Leaflet 1.9.4** over **OpenStreetMap** raster
tiles, loaded from a CDN. Points and legs are hard-coded in the page as
coordinates, grouped into per-day layers with a toggle control.

We do **not** use the Google Maps JavaScript API or the Maps Embed API.

## Consequences

The chief reason is keys. Both Google Maps APIs require an API key, and a key in
a static public HTML file is a key that is published. Restricting it by HTTP
referrer is possible but is configuration the group would have to own forever,
for a document with a three-week useful life. Leaflet with OSM tiles needs no
key and no account.

A single iframe embed of the group's own Google map was the other realistic
option, and it is the one we would have taken had the URL existed — reusing
their map avoids two maps drifting apart, which is a real cost. Without a URL,
building our own is the only way to get a map at all, and we accept that it is
now a second source of truth that can diverge from whatever they have in Google.
The coordinates are therefore kept in one clearly-marked block at the top of the
script, so they are cheap to correct.

Being key-free and layer-based, the map degrades honestly: with no network the
tiles fail but the page and every annotation still read, which matters because
this document is also printed and carried.

OSM tile usage is subject to the OpenStreetMap Foundation's tile usage policy.
At this document's readership — six people for three weeks — we are far inside
acceptable use, but a public high-traffic deployment would need a different tile
provider.
