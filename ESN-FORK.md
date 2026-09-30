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


## Verified build

- Version: `2.11.3-ESN.1`
- Successful GitHub Actions run: `36708471107`
- Artifact: `Geyser-Spigot.jar`
- SHA-256: `b9101ced0e19b7bba8ebaf985deb5f16f104f9bca311febc94fd1f6af63eec29`
- Compiled protocol table verified to include Bedrock `26.52` on the `Bedrock_v2193` codec.
