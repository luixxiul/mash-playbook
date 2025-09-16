<!--
SPDX-FileCopyrightText: 2025 MASH project contributors
SPDX-FileCopyrightText: 2025 Suguru Hirahara

SPDX-License-Identifier: AGPL-3.0-or-later
-->

# Radarr

[Radarr](https://radarr.video/) is a movie organizer/manager for usenet and torrent users.

## Dependencies

This service requires the following other services:

- a [Traefik](traefik.md) reverse-proxy server

## Configuration

To enable this service, add the following configuration to your `vars.yml` file and re-run the [installation](../installing.md) process:

```yaml
########################################################################
#                                                                      #
# radarr                                                               #
#                                                                      #
########################################################################

radarr_enabled: true

radarr_hostname: radarr.example.com

# To mount additional data directories, use `radarr_container_additional_volumes`
#
# Example:
# radarr_container_additional_volumes:
#   - type: bind
#     src: /path/on/the/host
#     dst: /data
#   - type: bind
#     src: /another-path/on/the/host
#     dst: /read-only
#     options: readonly

########################################################################
#                                                                      #
# /radarr                                                              #
#                                                                      #
########################################################################
```

## Usage

After running the command for installation, the Autobrr instance becomes available at the URL specified with `radarr_hostname`. With the configuration above, the service is hosted at `https://radarr.example.com`.

>[!NOTE]
> The `radarr_path_prefix` variable can be adjusted to host under a subpath (e.g. `radarr_path_prefix: /radarr`), but this hasn't been tested yet.

To get started, open the URL with a web browser, and configure a username and password. The recommended authentication method is `Forms (Login Page)`.

For additional configuration options, refer to [ansible-role-radarr](https://github.com/spatterIight/ansible-role-radarr)'s `defaults/main.yml` file.

## Recommended other services

Consider these other related services:

- [Autobrr](autobrr.md)
- [Jackett](jackett.md)
  - For Jackett integration instructions, see the [setup guide](jackett.md#intergration-with-sonarrradarr)
- [Jellyfin](jellyfin.md)
- [Overseerr](overseerr.md)
- [Plex](plex.md)
- [qBittorrent](qbittorrent.md)
  - For qBittorrent integration instructions, see the [setup guide](qbittorrent.md#intergration-with-sonarrradarr)
- [Sonarr](sonarr.md)
