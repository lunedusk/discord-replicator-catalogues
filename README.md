# discord-replicator-catalogues

Encrypted **route catalogues** for [discord-replicator](https://github.com/vedant/discord-replicator).

Library binaries do **not** need a release when Discord’s client routes change — only a new folder here.

## Layout

```text
latest.json
catalogues/
  <client_build>/
    <unix_epoch>/
      catalogue.dctl      # DCTE (AES-256-GCM) or plain DCTL
      endpoints.jsonl     # human-readable
      science.jsonl       # optional
      meta.json           # blake3, key_id, encrypted flag
```

## Consumers

```bash
export DR_CATALOGUE_BASE=https://raw.githubusercontent.com/vedant/discord-replicator-catalogues/main/
export DR_CATALOGUE_KEY=<64 hex from library secrets/catalogue.key>
```

## Publishers

From the library repo:

```bash
./tools/har_to_git.sh --js ... --har ... --build 610373 \
  --catalogues-repo ../discord-replicator-catalogues --push
```

GitHub Action updates `latest.json` on push of new `catalogue.dctl` + `meta.json`.
