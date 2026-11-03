# Asset Inspector downloads

The page people open on their controller to download the latest Drone Harmony Asset Inspector app:
pick a server (US1, AU1, APP, or type a custom one), then tap **Download latest app**.

Page: https://adamsaciuk.github.io/AssetInspectorApps/

Direct link for one server: add `?server=<name>`, for example
https://adamsaciuk.github.io/AssetInspectorApps/?server=us1

## Publish a new version

Edit `latest.json` and commit. The page picks it up within a minute or two of the commit.

| Field | What it does |
| --- | --- |
| `version` | The version every server downloads, e.g. `2.14.1`. |
| `size` | Shown under the button, e.g. `254 MB`. Leave it `""` to hide it. |
| `updated` | The date shown at the bottom, `YYYY-MM-DD`. |
| `servers` | The server buttons on the first screen. |
| `serverVersions` | A different version for one server, e.g. `{ "AU1": "2.14.0" }`. Leave `{}` when all match. |
| `link` | The download address; `{server}` becomes the server in lower case, `{version}` the version. |

With version `2.14.1`, US1 downloads `https://apks.droneharmony.com/dh_dji_us1_2.14.1.apk`.
A custom server typed on the page builds its link the same way.
