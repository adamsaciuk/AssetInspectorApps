# Asset Inspector downloads

The landing page for downloading the latest Drone Harmony Asset Inspector app. Tap **Download latest app**,
choose your server (AU1, US1, APP, or type a custom one), and the download for that server starts.

Page: https://adamsaciuk.github.io/AssetInspectorApps/

Laid out for a landscape tablet, a laptop browser and a DJI controller; it also works on a phone.

## Publish a new version

Edit `latest.json` and commit. The page reads it fresh every time it opens, once GitHub Pages has
published the commit (a minute or two).

| Field | What it does |
| --- | --- |
| `version` | The version every server downloads, e.g. `2.14.1`. |
| `size` | Shown under the button, e.g. `254 MB`. Leave it `""` to hide it. |
| `updated` | The date shown at the bottom, `YYYY-MM-DD`. |
| `servers` | The server buttons, in order. |
| `serverVersions` | A different version for one server, e.g. `{ "AU1": "2.14.0" }`. Leave `{}` when all match. |
| `link` | The download address; `{server}` becomes the server in lower case, `{version}` the version. |
| `serverCheck` | The address used to check a typed custom server exists. |

With version `2.14.1`, US1 downloads `https://apks.droneharmony.com/dh_dji_us1_2.14.1.apk`.

## Custom servers

A typed server name builds its link the same way. Before downloading, the page checks that the
server exists by loading `https://<name>.droneharmony.com/favicon.ico`; a name with no such server
shows an error. This proves the server exists, not that its app file does.
