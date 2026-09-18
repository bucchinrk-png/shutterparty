# SHUTTERPARTY

**Viewers press a button and your stream is photographed onto the broadcast.**
A Twitch extension; the two files here are the half that runs on your own PC.

- **Download:** [latest release](https://github.com/bucchinrk-png/shutterparty/releases/latest)
- **Setup guide** (requirements, the six steps, updating, your data): [shutterparty.app/start](https://shutterparty.app/start)
- 日本語の導入手順: [shutterparty.app/start/ja](https://shutterparty.app/start/ja)

| | |
|---|---|
| `SHUTTERPARTY-setup.html` | Open it in your normal browser. It connects to OBS, builds the scenes and browser sources, and writes your settings into them. |
| `overlay/index.html` | OBS loads it as a browser source. It takes the photographs and draws the effects. |

**Keep them next to each other** — the setup page looks for the overlay beside it.

**You can read what you are about to run.** These are ordinary HTML files — not
minified, not bundled — so you can open either one in a text editor before you
type your OBS password into it.

Report a problem: open an issue here, or mail tabuchin.room@gmail.com.
[Privacy policy](https://shutterparty-ebs.bucchi.workers.dev/privacy) ·
[Terms](https://shutterparty-ebs.bucchi.workers.dev/terms)

## Licence

[MIT](LICENSE) for the code in this repository. **The name is not part of that:**
`SHUTTERPARTY` and `SHUTTER PARTY` identify this product, and the licence covers
the code, not the right to publish something else under the same name.
