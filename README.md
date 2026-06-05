# map-view.
Here is a **complete, reusable prompt** you can use (for yourself or with any AI tool) to reliably recreate the exact map you’ve built—without the trial-and-error you experienced.

This prompt encodes **all design decisions, constraints, and corrections** we established.

***

# ✅ ✅ ✅ MASTER PROMPT

*(Leaflet Hub-and-Spoke Map with Filters, Timeline, and UI Controls)*

***

## ✅ PROMPT

> Build a **fully working Leaflet.js map** using a CSV dataset hosted at a GitHub raw URL.
>
> The map must implement a **hub-and-spoke visualization** of individual records grouped by origin location, with interactive controls and a clean UI suitable for embedding in WordPress or GitHub Pages.

***

## ✅ DATA SOURCE

* Use this CSV:

```
https://raw.githubusercontent.com/emhcais/timeslidermap/main/kepler_radial_layout.csv
```

* Fields include:
  * `name_original`
  * `name_baptismal`
  * `year`
  * `pope`
  * `origin`
  * `region`
  * `lat`, `lon`

***

## ✅ CORE VISUALIZATION

### ✅ Hub-and-Spoke Structure

* Group rows by `origin`
* For each group:
  * Create a **central hub marker** at (`lat`, `lon`)
  * Create **individual nodes** arranged radially around the hub
  * Connect each node to the hub with a line

***

### ✅ Radial Layout

* Position nodes using:
  * equal angular spacing
  * radius ≈ `0.25–0.35`
* Ensure nodes do not overlap excessively

***

## ✅ COLOR ENCODING

* Assign a **unique color for each origin (location)**
* Use a dynamic color generator:
  ```
  hsl(index * 40, 70%, 50%)
  ```
* Apply the same color to:
  * hub marker
  * connecting lines
  * individual nodes

***

## ✅ TIMELINE

### ✅ Slider

* Range: `1600 → 1690`
* Step: `1`
* Controls visibility:
  * Only show records where `year <= currentYear`

***

### ✅ Animation

* Add play/pause button
* Increment year automatically
* Loop back to 1600 after 1690

***

### ✅ Label Display

Show:

```
[Current Year] ([Decade]s)
```

Example:

```
1623 (1620s)
```

***

## ✅ FILTERS (ALL REQUIRED)

Provide dropdowns for:

### ✅ Pope Filter

* Filter: `row.pope`

### ✅ Region Filter

* Filter: `row.region`

### ✅ Location Filter

* Filter: `row.origin`

***

## ✅ MAP INTERACTIONS

### ✅ Zoom Behavior

* Click hub → zoom to location (zoom level \~6)
* Click node → zoom closer (\~7)

***

### ✅ Tooltip (Hover)

* Show origin label + count
* Offset tooltip upward so it is not covered by spokes

***

## ✅ POPUPS (REQUIRED FORMAT)

Each individual node must display:

```
Name: [name_original]
Baptismal Name: [name_baptismal]
Pope: [pope]
Year: [year]
Location: [origin]
Region: [region]
```

Use fallback values (`N/A`) if fields are empty.

***

## ✅ USER INTERFACE

### ✅ Sidebar Layout

* Place control panel on the **left side**
* Full height vertical panel
* Includes:
  * slider
  * play button
  * filters
  * basemap selector

***

### ✅ Collapsible Sidebar

* Collapse to narrow bar (\~40px)
* Hide controls completely when collapsed
* Map expands to fill space

***

## ✅ BASEMAP SELECTOR

Provide dropdown with:

1. Light (OpenStreetMap)
2. Dark (Carto Dark)
3. Arabic-style (Carto Voyager Labels)

***

## ✅ ZOOM CONTROL

* Move Leaflet zoom control to:

```
top-right
```

***

## ✅ LEGEND

### ✅ Requirements

* Fixed position (bottom-right of map)
* Must NOT disappear on zoom
* Lists all visible locations

### ✅ Format

```
● Location Name
```

* Color matches map encoding

***

### ✅ Behavior

* Updates dynamically with filters
* Scrollable if many locations

***

## ✅ LAYOUT CONSTRAINTS (CRITICAL)

To ensure compatibility with WordPress:

* ❌ Do NOT use:
  * `width: 100vw`
  * negative margins
* ✅ Use:
  * relative positioning
  * fixed sidebar + flexible map

***

## ✅ LIBRARIES

Must include **properly formatted tags**:



***

## ✅ DATA LOADING

Use:

* PapaParse
* `header: true`
* `download: true`
* `skipEmptyLines: true`

***

## ✅ STABILITY REQUIREMENTS

* Code must be:
  * fully self-contained (single HTML file)
  * free of malformed `<script>` or `<link>` tags
  * safe for GitHub Pages or WordPress (Custom HTML block)

***

## ✅ FINAL GOAL

Produce:

👉 A **responsive, interactive historical map** that supports:

* temporal exploration
* geographic clustering
* filtering by multiple categories
* clear and readable UI

***

# ✅ ✅ ✅ WHY THIS PROMPT WORKS

This prompt encodes the key lessons from your build:

### ✅ Avoids your earlier failure points

* no broken script tags
* no WordPress-breaking layout hacks
* valid Leaflet initialization

### ✅ Preserves what worked

* hub-and-spoke logic
* filters + animation
* user interaction design

### ✅ Encapsulates all features cleanly

So you can:

* rebuild it quickly
* reuse it for other datasets
* hand it off to collaborators

***

# ✅ ✅ IF YOU WANT

I can also convert this into:

* ✅ a **graded assignment prompt for students**
* ✅ a **methods section for a paper**
* ✅ a **technical appendix**

Just tell me 👍
