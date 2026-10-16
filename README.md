> [!WARNING]
> **Experimental / Vibe Coding Test**  
> This repository is merely an automated repackaging pipeline to extract raw `.AppImage` binaries from upstream ZIP releases for integration with **Gear Lever**.  
> No code changes, no support, no guarantees. You have been warned!

Original Repository: https://github.com/DevilXD/TwitchDropsMiner

## How it works

A GitHub Actions workflow ([`repack.yml`](.github/workflows/repack.yml)) runs every 12 hours and can be started manually.

1. It reads the upstream pre-release `dev-build` and extracts the `Reference commit` from its release notes.
2. If a release named `dev-<first 7 chars of that commit>` already exists in this repository, the run ends without doing anything.
3. Otherwise it downloads the upstream ZIP files `Twitch.Drops.Miner.Linux.AppImage-x86_64.zip` and `Twitch.Drops.Miner.Linux.AppImage-aarch64.zip`, extracts the `.AppImage` files and publishes them as a pre-release.

No upstream source code is stored in this repository.

## Releases

Each release is tagged `dev-<sha7>`, where `<sha7>` is the upstream reference commit the binaries were built from. The release notes list the full commit and the upstream build date.

Files per release:

- `Twitch.Drops.Miner-x86_64.AppImage`
- `Twitch.Drops.Miner-aarch64.AppImage`

The binaries are extracted unmodified from the official upstream release ZIP files.

## License and attribution

The upstream project, [DevilXD/TwitchDropsMiner](https://github.com/DevilXD/TwitchDropsMiner), is licensed under the MIT License, Copyright (c) 2024 DevilXD. The full license text is included in [`LICENSE`](LICENSE).

This repository is not affiliated with or endorsed by the upstream author.

---
