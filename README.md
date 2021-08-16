
# Arimac Meet Desktop Application

This is the desktop application for Arimac Meet built with Electron.  Currently we have released application versions for both Windows and Linux. The screenshots of the live app are as follows:

![](https://gitlab.com/mr_arimac/arimac-meet-desktop-app/-/raw/main/resources/screenshots/1.jpeg)

![](https://gitlab.com/mr_arimac/arimac-meet-desktop-app/-/raw/main/resources/screenshots/3.jpeg)

  
## Features

- [End-to-End Encryption](https://jitsi.org/blog/e2ee/) support (BETA)
- Works with any Jitsi Meet deployment
- Builtin auto-updates
- ~~Remote control~~ (currently disabled due to [security issues](https://github.com/jitsi/security-advisories/blob/master/advisories/JSA-2020-0001.md))
- Always-On-Top window
- Support for deeplinks such as `arimac-meet://myroom` (will open `myroom` on the configured Arimac Meet instance) or `arimac-meet://meet.arimac.digital/myroom` (will open `myroom` on theArimac Meet instance running on `meet.arimac.digital`)

## Installation

Download **Arimac Meet** Desktop latest release and you're off to the races!

| Windows | GNU/Linux (AppImage) | GNU/Linux (Deb) | macOS |
| -- | -- | -- | -- |
| [Download](https://arimaccommon.blob.core.windows.net/arimac-meet/arimac_meet_setup.exe) | [Download](https://arimaccommon.blob.core.windows.net/arimac-meet/arimac_meet_package-x86_64.AppImage) | [Download](https://arimaccommon.blob.core.windows.net/arimac-meet/arimac_meet_package-amd64.deb) | ~~Download~~ | 

***NOTE:** The GNU/LInux builds are 64-bit only.*

## Development

If you want to hack on Arimac Meet project, here is how you do it.

<details><summary>Show building instructions</summary>

#### Installing dependencies

Install Node.js 12 first (or if you use [nvm](https://github.com/nvm-sh/nvm), switch to Node.js 12 by running `nvm use`).

<details><summary>Extra dependencies for Windows</summary>

```bash
npm install --global --production windows-build-tools
npm config set msvs_version 2017
```
</details>

<details><summary>Extra dependencies for GNU/Linux</summary>

X11, PNG and zlib development packages are necessary. On Debian-like systems then can be installed as follows:

```bash
sudo apt install libx11-dev zlib1g-dev libpng-dev libxtst-dev
```
</details>

Install all required packages:

```bash
npm install
```

#### Starting in development mode

```bash
npm start
```

The debugger tools are available when running in dev mode and can be activated with keyboard shortcuts as defined here https://github.com/sindresorhus/electron-debug#features.

It can also be displayed automatically from the `SHOW_DEV_TOOLS` environment variable such as:

```bash
SHOW_DEV_TOOLS=true npm start
```
or from the application `--show-dev-tools` command line flag.

#### Building the production distribution

```bash
npm run dist
```

</details>

## Known Issues

### Windows
A warning will show up mentioning the app is unsigned upon first install. This is expected.

### macOS
On macOS Catalina a warning will be displayed on first install. The app won't open unless "open" is pressed. This dialog is only shown once.

Builtin auto-updates are not yet handled in macOS due to unsigned build.

### GNU/Linux
There is a known issue which prevents the app from starting on some Linux distributions: [#231](https://github.com/jitsi/jitsi-meet-electron/issues/231)

If after downloading it, you can't execute the file directly, try running `chmod u+x ./jitsi-meet-x86_64.AppImage`

The workaround for now is to launch the app like so: `./jitsi-meet-x86_64.AppImage --no-sandbox`

<details><summary>NOTE for old GNU/Linux distributions</summary>

You might get the following error:

```
FATAL:nss_util.cc(632)] NSS_VersionCheck("3.26") failed. NSS >= 3.26 is required.
Please upgrade to the latest NSS, and if you still get this error, contact your
distribution maintainer.
```

If you do, please install NSS (example for Debian / Ubuntu):

```bash
sudo apt-get install libnss3
```

</details>

## Arimac Meet Web

If you are interested to join to develop our regular Arimac Meet Web Application, you can simply vist following repository:

[https://gitlab.com/mr_arimac/arimac-meet](https://gitlab.com/mr_arimac/arimac-meet)

## How to Contribute

If you spot any bugs, please use  [Gitlab Issues]https://gitlab.com/mr_arimac/arimac-meet-desktop-app/-/issues)  or if you want to add a new feature directly   [Fork](https://gitlab.com/mr_arimac/arimac-meet-desktop-app/-/forks/new) and push to the main repo.

## Sponsoring

If you like my work and want to support the development of the project, now you can! Just:

[![Buy Me A Coffee](https://camo.githubusercontent.com/0f3e240e3bc1e7876ec84f7d3e224eb01144293e5a74e7f53df732d656bfc325/68747470733a2f2f7265732e636c6f7564696e6172792e636f6d2f70616e722f696d6167652f75706c6f61642f76313537393337343730352f6275796d6561636f666665655f793679766f762e737667)](https://manoranjana.me)

## License

### Apache License 2.0

A permissive license whose main conditions require preservation of copyright and license notices. Contributors provide an express grant of patent rights. Licensed works, modifications, and larger works may be distributed under different terms and without source code.
*For more info. please read [here](https://www.apache.org/licenses/LICENSE-2.0).*