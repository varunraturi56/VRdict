# VRdict — Personal Film & TV Tracker

A single-file web application for tracking, discovering, and curating your movie and TV show collection. Built as a self-contained HTML file with no build tools or backend required.

## Features

### Library
- Browse your full collection split by **Movies** and **TV Shows** tabs
- Filter by genre, tags, and sort by rating, title, year, or TMDB score
- Smooth, non-flickery search within your collection
- Three view modes: grid, compact, and list
- Rotating hero banner (5s interval) showcasing a random high-rated title
- Click any title to edit rating, tags, year watched, or remove it
- Hover preview tooltips showing title, rating, genres, overview, and tags

### Favourites
- Curate your top picks by toggling the Favourites star on any title
- Filter favourites by genre, mood, and tags using pill-row filters
- Smooth search that only updates the grid (no page flicker)
- Separate Movies/TV Shows tabs with counts
- Export a shareable HTML page of your recommendations

### Recommend
- Surface your highest-rated titles filtered by genre, mood, and tags
- Adjustable minimum rating threshold (5+ to 9+)
- Smooth search and multiple view modes
- Hover preview on all cards

### Watchlist
- **Movies** and **TV Shows** tabs for titles you plan to watch
- **Rewatch** tab for titles from your library you want to see again
- Filter by genre, mood, and TMDB rating
- Dual full-width search bars: one to filter your collection, one to search TMDB and add new titles
- Hover preview tooltips on all cards (including rewatch)
- Mark a watchlist title as "Watched" to move it into your library with full details
- Gradient separator dividers between tab buttons

### Discover
- Find new movies and TV shows based on your taste profile
- Filter by genre, mood, era (decade), and keyword search
- Built-in **search & add** bar to find any title on TMDB and add it directly to your library or watchlist
- Hover preview tooltips showing TMDB rating, year, genres, and overview
- Excludes titles already in your library or watchlist
- "Fresh Picks" button to load new pages of results
- Cards show TMDB score with compact, symmetric quick-add buttons (+Add / +Watch)

### Stats
- Total watched count, watch time (hours/days toggle), average rating, top genre
- Interactive charts powered by Chart.js:
  - Genre breakdown (doughnut)
  - Ratings distribution (bar)
  - Your rating vs TMDB rating (scatter)
  - Films by decade (bar)
- Top 10 rated movies and TV shows with poster rows

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Frontend | Single HTML file (~1940 lines) with embedded CSS and JavaScript |
| Data API | [TMDB (The Movie Database)](https://www.themoviedb.org/) for search, metadata, and posters |
| Charts | [Chart.js 4.4.1](https://www.chartjs.org/) via CDN |
| Fonts | Google Fonts — Bodoni Moda (headings), Sora (body), JetBrains Mono (numbers) |
| Storage | Browser `localStorage` — no server or database required |
| Design | Dark theme with blue-to-violet gradient accent system |

## Setup

1. **Get a TMDB API key**
   - Create a free account at [themoviedb.org](https://www.themoviedb.org/signup)
   - Go to Settings > API and request an API key
   - When asked for a URL, enter `http://localhost`

2. **Open `cinelog.html`** in any modern browser

3. **Enter your API key** on the setup screen — it's stored locally and never sent anywhere except TMDB

That's it. No install, no build, no dependencies to manage.

## Data & Backup

All data is stored in your browser's `localStorage` under these keys:

| Key | Contents |
|-----|----------|
| `cinelog_key` | Your TMDB API key |
| `cinelog_data` | Your library entries (movies & shows with ratings, tags, etc.) |
| `cinelog_bucket` | Your watchlist queue |
| `cinelog_tags` | Custom tags you've created |

### Backup & Restore
- Click the gear icon in the header to **Export** a JSON backup file
- **Import** a backup to restore your full collection on any browser
- The app reminds you to back up after every 10 new entries

## Navigation

| Tab | Description |
|-----|-------------|
| **Library** | Your full collection with filters and hero banner |
| **Favourites** | Starred titles filtered by genre, mood, and tags |
| **Recommend** | High-rated titles you'd suggest to friends |
| **Watchlist** | Queue of unwatched titles + rewatch list |
| **Discover** | Find new titles via TMDB + search & add to library |
| **Stats** | Analytics and charts about your viewing habits |

## Design

- Dark theme (`#08080a` base) with subtle noise texture overlay
- Blue (`#0ea5e9`) to violet (`#a78bfa`) gradient accent on headings, labels, and ratings
- Blue-to-violet gradient text on all major headings, stat numbers, filter labels, and chart titles
- Gradient header border below the navigation bar
- Gradient vertical separators between sub-tab buttons (Movies | TV Shows | Rewatch)
- Color-coded: blue for movies, violet for TV shows
- Hover preview tooltips on film cards across all tabs
- Responsive layout with breakpoints at 900px and 600px
- Smooth animations using `cubic-bezier(.22, 1, .36, 1)` easing
- Three view modes (grid, compact, list) available on all collection tabs

## File Structure

```
movie-logger/
  cinelog.html              # The entire application (HTML + CSS + JS)
  vrdict-backup-*.json      # Exported backup files
  README.md                 # This file
```

## Browser Support

Works in any modern browser with ES6+ support (Chrome, Firefox, Safari, Edge). Requires JavaScript enabled and an internet connection for TMDB API calls and poster images.

## License

Personal project — not currently published under a specific license.
