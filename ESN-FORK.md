# ESN-Geyser

ESN-Geyser is an ES Network-maintained fork of [GeyserMC/Geyser](https://github.com/GeyserMC/Geyser).

## Current ESN compatibility target

- Java server target: Paper/Spigot 26.2
- Bedrock target: 26.30 through 26.52
- Bedrock 26.52 is accepted on protocol 2193
- Primary artifact: `Geyser-Spigot.jar`
- Intended host: DaTHost / ESN SMP

## Build

GitHub Actions builds the Spigot artifact automatically on pushes to `master`.
The downloadable workflow artifact is named `ESN-Geyser-Spigot`.

## Upstream

This fork keeps the original GeyserMC MIT license and attribution.
Protocol/network changes should stay as small as possible so upstream fixes can be merged safely.

## Important

26.52 uses the existing protocol 2193 codec in this ESN build. This compatibility patch does not invent or emulate a different protocol number.
