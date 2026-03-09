# FAgram Desktop OTA Updates

This repository hosts OTA (Over-The-Air) update packages for [FAgram Desktop](https://github.com/fagramdesktop/fagramdesktop).

## Structure

```
ota/
├── current4              # JSON manifest with latest versions per platform
├── tx64upd<version>      # Windows x64 update package
├── tlinuxupd<version>    # Linux update package
└── README.md
```

## How it works

The FAgram Desktop client periodically checks `current4` for new versions. If an update is available, it downloads the signed package and installs it automatically.

## Supported platforms

| Platform    | Key     | File prefix  |
|-------------|---------|--------------|
| Windows x64 | `win64` | `tx64upd`    |
| Linux       | `linux` | `tlinuxupd`  |

## Publishing updates

Use the publish script from the main repo:

```bash
python Telegram/build/publish_update.py \
  --version <version_int> \
  --platform win64 \
  --file path/to/tx64upd<version>
```

See [docs/ota-updates.md](https://github.com/fagramdesktop/fagramdesktop/blob/dev/docs/ota-updates.md) for full documentation.
