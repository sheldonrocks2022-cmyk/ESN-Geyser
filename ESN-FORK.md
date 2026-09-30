# ESN-Geyser

ESN-Geyser is an ES Network-maintained fork of [GeyserMC/Geyser](https://github.com/GeyserMC/Geyser).

## Current ESN compatibility target

- ESN version: `2.11.3-ESN.2`
- Java backend target: Paper/Spigot 26.2
- ESN Bedrock target: 26.30 through 26.52
- Bedrock 26.52 is accepted on protocol 2193
- Paper/Spigot artifact: `ESN GEYSER.jar`
- Velocity artifact: `ESN GEYSER VELOCITY.jar`
- Intended network: ESN SMP / DaTHost backend with a dedicated Velocity proxy process

## Velocity support

The repository now builds the official Geyser Velocity bootstrap in the same CI run as the existing Paper/Spigot build.

Current PaperMC documentation lists Velocity compatibility for Java clients from Minecraft 1.7.2 through 26.3. To translate the broadest practical Java client range to a modern backend, install the matching current releases of:

- ViaVersion
- ViaBackwards
- ViaRewind

Velocity itself is a separate proxy process. Do not try to load `ESN GEYSER VELOCITY.jar` as a Paper plugin.

If ESN uses Geyser on Velocity, Geyser should run on the proxy rather than also running Geyser-Spigot on the backend server. Floodgate can remain on the proxy and may also be installed on backend servers when its API or skin features are needed.

## Forwarding note

Velocity modern forwarding is preferred for networks that only need Minecraft 1.13+ clients.

If ESN intentionally supports Java clients older than 1.13, Velocity modern forwarding cannot be used for those clients. Use a properly secured legacy/BungeeGuard-compatible forwarding design and protect the backend from direct connections.

Do not commit a live forwarding secret to this repository.

## Build

GitHub Actions builds both platform artifacts automatically on pushes to `master`.

The workflow performs these checks before publishing artifacts:

- Builds both `:spigot:build` and `:velocity:build`
- Confirms both JARs exist and are non-empty
- Opens each JAR and confirms the expected Geyser platform main class exists
- Publishes the Paper/Spigot JAR separately
- Publishes the Velocity JAR separately
- Publishes a combined ESN network artifact containing both

## Bedrock version limitation

Geyser cannot support every historical Bedrock client version. Bedrock protocol support is limited to the versions implemented by the current Geyser protocol stack.

For the current ESN build, the target range is 26.30 through 26.52. Future Bedrock releases may require an upstream Geyser protocol update before ESN can support them.

## Upstream

This fork keeps the original GeyserMC MIT license and attribution.

Protocol/network changes should stay as small as possible so upstream fixes can be merged safely.

## ESN production connection

Last verified live ESN SMP connection before the Velocity layer was added:

- Java backend/public address: `esn.ggwp.cc:17769`
- Bedrock / Xbox: `esn.ggwp.cc:17429`
- Geyser external connection test for the Bedrock listener passed on UDP port `17429`

When Velocity becomes the public Java entry point, keep the backend Paper listener separate from the proxy listener so the two processes never bind to the same TCP port.
