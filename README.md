# discord-replicator-catalogues

Encrypted **route catalogues** for [discord-replicator](https://github.com/lunedusk/discord-replicator).

Library binaries do **not** need a release when Discord’s client routes change — only a new folder here.

## Layout

```text
latest.json
catalogues/
  <client_build>/
    <unix_epoch>/
      catalogue.dctl      # DCTE (AES-256-GCM) or plain DCTL
      meta.json           # blake3, key_id, encrypted flag
```

## Consumers

```bash
export DR_CATALOGUE_BASE=https://raw.githubusercontent.com/vedant/discord-replicator-catalogues/main/
export DR_CATALOGUE_KEY=<64 hex from library secrets/catalogue.key>
```
