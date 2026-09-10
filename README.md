# SHUTTERPARTY

**Viewers press a button and your stream is photographed onto the broadcast.**
A Twitch extension, and the two files here are the half that runs on your own PC.

- **Download:** [latest release](https://github.com/bucchinrk-png/shutterparty/releases/latest)
- **Setup guide (six steps, about five minutes):** [shutterparty.pages.dev/start](https://shutterparty.pages.dev/start)
- 日本語の導入手順: [shutterparty.pages.dev/start/ja](https://shutterparty.pages.dev/start/ja)

---

## What this repository is

The extension itself lives on Twitch and is installed from the Extension Store.
It cannot take the photograph — **a Twitch extension has no access to the video**
(confirmed with Twitch developer support), so the capture happens in your own OBS
and the result is composited onto your broadcast.

That is what these two files do:

| | |
|---|---|
| `SHUTTERPARTY-setup.html` | You open this in your normal browser. It connects to OBS over obs-websocket, builds the scenes and browser sources for you, and writes your settings into them. |
| `overlay/index.html` | OBS loads this as a browser source. It takes the photographs and draws the effects. It has no interface of its own. |

**They have to stay next to each other.** The setup page finds the overlay at
`overlay/index.html` beside it, so unzip the folder and leave it as it came.

## Why a download instead of a website

A page served over the web is not allowed to talk to software running on your
computer. The photograph is taken by *your* OBS, so the file has to live on your
disk. That restriction is also why nothing here can see your scenes, your screen,
or your obs-websocket password.

## You can read what you are about to run

**These are ordinary HTML files — not minified, not bundled, not obfuscated.**
Open either one in a text editor before you type a password into it. That is the
point of publishing them this way: the setup page asks for your obs-websocket
password, and downloading an unfamiliar HTML file and typing a password into it
is the same shape as a phishing attack. Being able to check is the only honest
answer to that.

What you will find:

- **The obs-websocket password never leaves your machine.** It is used to open a
  connection to `127.0.0.1`, and it is never sent anywhere.
- **It is not left lying about on your PC either.** The password and the pairing
  code are kept encrypted, under a key that the page itself cannot read back out
  — so a copy of your browser profile, a backup, or a sync does not carry them.
  They also arrive in the OBS browser source's address and are **taken back out
  of it** once they are safely stored: OBS shows that address in the source's
  properties, which is a window you might open while you are live.
- **The photographs are never uploaded.** They are produced by your OBS and
  appear inside your own broadcast, the same way everything else on your canvas
  does.
- **Saving to disk is off** until you choose a folder.
- **No network requests to anywhere but your own OBS and the extension's own
  backend** — and the backend only ever hears "somebody pressed the button".

Full detail: [privacy policy](https://shutterparty-ebs.bucchi.workers.dev/privacy)
· [terms](https://shutterparty-ebs.bucchi.workers.dev/terms)

## Requirements

- **OBS 28 or newer.** obs-websocket ships inside OBS from version 28; older
  versions need a plugin and are not supported.
- **The extension installed on your channel**, activated as a Component (over the
  video) or a Panel (below it).
- **Affiliate or Partner is not required.** Bits need it, but free presses fill
  the goal bar on their own, so a SHUTTER PARTY can happen on any channel.

## Updating

Download again and replace the file and the folder where they already are, then
open `SHUTTERPARTY-setup.html` and press **Write to OBS** once — OBS keeps the old overlay
until it is told to fetch the new one. The setup page says *"The overlay file is
newer than what OBS has. Write it again"* until you do. **Your settings survive
the replacement**; they are kept by the browser you set things up in, not by the
files.

## Reporting something

Open an issue here, or mail tabuchin.room@gmail.com.

## Licence

[MIT](LICENSE) for the code in this repository.

**The name is not part of that.** `SHUTTERPARTY` and `SHUTTER PARTY` identify
this product; the licence covers the code, not the right to publish something
else under the same name.

---

*This repository carries what is distributed. The development history, the plan
and the internal documents are not published here.*
