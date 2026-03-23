# megcullen_landing_page

BAIS:3500 - Landing Page project by Meghan Cullen.

## Project Overview

A simple static HTML landing page. The `index.html` file is the main (and only) file for the site.

## Architecture

- **Type**: Static HTML website
- **Entry point**: `index.html`
- **No build step required**

## Development

The site is served using Python's built-in HTTP server on port 5000:

```
python3 -m http.server 5000
```

## Deployment

Configured as a static site deployment, serving from the root directory (`.`).
