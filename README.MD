# KinoPoisk (white listed) Jellyfin plugin

This fork adds support for Jellyfin 12.1. It retains the original project's history and credits [MiklinMA](https://github.com/MiklinMA/jellyfin-kinopoisk-white).

## About

This plugin for [jellyfin media center](https://jellyfin.org) fetches metadata from [Kinopoisk](https://www.kinopoisk.ru/).

In difference of [kinopoisk unofficial plugin](https://github.com/LinFor/jellyfin-plugin-kinopoisk) it utilizes the official Yandex API, so it could be used behind Russian White-Listed-Internet firewall.

## Installation

### Automatic

1. Navigate to Settings -> Admin Dashboard -> Plugins -> Repositories
1. Add a new repository with a Repository URL of `https://raw.githubusercontent.com/Rewentes/jellyfin-kinopoisk-white/refs/heads/master/manifest.json`. The name can be anything you like (such as `KinoPoisk`).
1. Save and navigate to Catalogue.
1. `Кинопоиск (белый список)` should be present. Click on it and install the latest version.

### Manual (and/or offline mode)

[See the official Jellyfin documentation for install instructions](https://jellyfin.org/docs/general/server/plugins/index.html#installing).

1. Download a version from the [releases tab](https://github.com/Rewentes/jellyfin-kinopoisk-white/releases) that matches your Jellyfin version.
1. Create a directory KinopoiskWhite inside jellyfin plugins directory.
1. Copy KinopoiskWhite.dll file into created directory.
1. Restart Jellyfin instance.
1. Check if plugin appears on jellyfin plugins page and in the library settings.

## Development

1. Use the .NET 10 SDK.
1. Run `dotnet test jellyfin-kinopoisk-white.sln` to restore dependencies and run the tests.
1. Run `dotnet build KinopoiskWhite/Plugin.csproj -c Release`.
1. Copy `KinopoiskWhite/bin/Release/net10.0/KinopoiskWhite.dll` to a KinopoiskWhite subdirectory in your Jellyfin plugins directory.
1. Restart jellyfin

## API

* I use official Yandex API and GraphQL which one can find on hd.kinopoisk.ru and www.kinopoisk.ru
* These APIs work as is so I don't know when it begins to behave differently (in this case feel free to create a ticket [here](https://github.com/MiklinMA/jellyfin-kinopoisk-white/discussions/new/choose))
* The only reason of using these undocumented APIs is that they are available behind the Great Russian Firewall.
