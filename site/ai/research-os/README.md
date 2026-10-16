# Research OS — Knowledge Desk Prototype

This folder contains a standalone UI experiment for the Research OS project. It is a public-safe demo and does not connect to the private `21mm/research-os-memory` archive.

## Use

Open `index.html` in a modern browser. No build step, framework, external JavaScript, third-party stylesheet, or server API is required. Records are stored in the browser's `localStorage` for this site origin. They do not sync across devices, browsers, or conversations. JSON exports download locally.

## Demo data and privacy

- The initial records are synthetic examples about a hypothetical search interface, not real user research or evidence.
- The page does not call GitHub APIs, contact the private archive, or send record content to a server.
- Use only synthetic or deliberately public data here. Do not enter passwords, access tokens, confidential information, or private research.
- Clearing browser site data can remove locally stored records. Export a backup before experimenting with important data.

## JSON interchange v0.1

Exports use a `research-os-browser-export` envelope with `format_version: "0.1"` and a `records` array. Each entry wraps one `claim`, `source`, `evidence`, or `relation` record.

The bundle format is a prototype; it is **not yet an adapter** for the private repository's canonical one-file-per-record layout. The browser preflight validator is intentionally narrower than the private repository's full JSON Schema/cross-record validator.

## Import safeguards

Import is limited to 5 MB and 500 records. Before applying it, the app checks known fields, required values, ID format, dates, URL schemes, duplicate IDs, unresolved references, claim/evidence role consistency, and supersession cycles. It previews the candidate dataset first; merge refuses existing-ID collisions; merge and replacement require confirmation.

## Current limitations

Only claims, sources, evidence, and relations are supported. There is no authenticated access, server sync, version history, graph visualization, or canonical archive conversion. Advanced edits use a raw JSON editor. This is an experiment, not a production research archive.
