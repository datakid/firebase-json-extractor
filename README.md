# Credential Forge

Reads Firebase service-account JSON files and shows the values to paste as Cloudflare Worker secrets.

## What it does

- Express mode takes three service-account files, identified as OTHER, Plan B and Plan C from their file names, and shows the six secret values a Worker expects: an email and a private key for each file.
- Custom mode takes any number of files and lets you name the two Cloudflare variables for each file.
- Checks that each file is a JSON object with a `client_email` and a `private_key` that starts with the `BEGIN PRIVATE KEY` marker, and normalises the key's line breaks.
- Copies each value to the clipboard.
- Remembers the last variable names you typed in custom mode, in this browser's `localStorage`.

## What it does not do

- It does not talk to Cloudflare. Nothing is set on a Worker; you paste the values yourself.
- It does not upload files. They are read in the tab.
- The six express names are fixed in `index.html`.

## Network and install

Loads Google Fonts. It makes no other requests. Not installable; no service worker.

## Built with

One HTML file, with no build step, no framework and no libraries.

## Run locally

Open `index.html` in a browser, or serve the folder with any static file server.
