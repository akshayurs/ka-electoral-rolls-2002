# Karnataka Electoral Rolls 2002 — PDF Viewer

A simple, single-page tool to view the 2002 Karnataka electoral roll PDFs by
**district → constituency → part number**.

The official page at `ceo.karnataka.gov.in` sits behind a load balancer that
returns `HTTP 503` most of the time, and its own "View PDF" button gives up on
the first failure. This viewer fetches the PDF directly and **keeps retrying
through the 503s** (8 parallel requests, first success wins), so the file
usually loads in a couple of seconds.

## Usage

Open the page, pick a district, constituency and part number, then click
**View PDF**. The PDF renders inline with Download / Open-in-new-tab links.

## Notes

- Unofficial. All PDFs are served directly from the Chief Electoral Officer,
  Karnataka (`ceo.karnataka.gov.in`). This page stores no data.
- Single static `index.html`, no build step, no dependencies.
