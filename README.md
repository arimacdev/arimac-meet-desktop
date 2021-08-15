
# Arimac Meet Desktop Application

This is the pre-built desktop application for Arimac Meet built with Electron. The screenshots of the live app are as follows:



  
## Features

-  [End-to-End Encryption](https://jitsi.org/blog/e2ee/) support (BETA)
- Works with any Jitsi Meet deployment
- Builtin auto-updates
- ~Remote control~ (currently disabled)
- Always-On-Top window

- Support for deeplinks such as `arimac-meet://myroom` (will open `myroom` on the configured Jitsi instance) or `arimac-meet://arimac.mycompany.com/myroom` (will open `myroom` on the Jitsi instance running on `arimac.mycompany.com`)

  
## Latest Downloads

| Windows | macOS | GNU/Linux (64-bit only) |

| -- | -- | -- |

| [Download](http://tiny.cc/arimac_meet_beta_windows) | No Release | No Release |

## Development

If you want to hack on this project, here is how you do it.

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



## How to Contribute

If you spot any bugs, please use  [Gitlab Issues](https://gitlab.com/mr_arimac/arimac-meet/-/issues)  or if you want to add a new feature directly   [Fork](https://gitlab.com/mr_arimac/arimac-meet/-/forks/new) and push to the main repo.

## Sponsoring

If you like my work and want to support the development of the project, now you can! Just:

[![Buy Me A Coffee](https://camo.githubusercontent.com/0f3e240e3bc1e7876ec84f7d3e224eb01144293e5a74e7f53df732d656bfc325/68747470733a2f2f7265732e636c6f7564696e6172792e636f6d2f70616e722f696d6167652f75706c6f61642f76313537393337343730352f6275796d6561636f666665655f793679766f762e737667)](https://manoranjana.me)

## License

### Apache License 2.0

A permissive license whose main conditions require preservation of copyright and license notices. Contributors provide an express grant of patent rights. Licensed works, modifications, and larger works may be distributed under different terms and without source code.
*For more info. please read [here](https://www.apache.org/licenses/LICENSE-2.0).*