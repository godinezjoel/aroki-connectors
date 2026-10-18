# AROKI Connectors

Public connector repository for **AROKI - Made by Synthetiq**.

This repository contains bounded declarative JSON manifests and the
`index.json` used by AROKI's repository importer. It does **not** contain the
AROKI iOS application, executable modules, JavaScript, WebViews, browser
automation, credentials, media files, or a proxy/backend service.

## Available connector

This repository currently contains only **AniWorld** (`aniworld-expansion`),
an experimental multilingual video connector. It provides native declarative
discovery, search, title details, episode listings, and stream resolution for
the configured AniWorld hosts, with German Dub and Sub (German subtitles,
English-subtitle fallback). The connector is version `0.4.0` and requires
AROKI `2.0.36` or newer.

The index contains only this connector. Availability can change independently
of AROKI, and users and source publishers remain responsible for ensuring they
have permission to access and distribute the content they configure.

## Safety boundary

Connectors describe a finite set of HTTPS requests and typed extraction steps.
They cannot add executable behavior to AROKI. The native app continues to own
validation, request limits, host policy, parsing, caching and AVPlayer playback.

The repository signing key is held outside Git and is never committed here.
The checked-in index is an unsigned personal/test feed after this cleanup;
official app distribution requires the protected publishing workflow to
re-sign it.

## Windows publishing

Windows contributors can validate the AniWorld manifest with:

```powershell
py scripts/validate-unsigned-connector.py aniworld-expansion
```

For signed publication, push a candidate branch and dispatch the protected
GitHub publishing workflow. For an unsigned bridge-build feed, see
[Windows connector workflow](docs/WINDOWS_CONNECTOR_WORKFLOW.md).
