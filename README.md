Webpack
-------------------
Replace `cfx-server-data` webpack and now is not coming leak shit.
Same proplem have 2022: https://forum.cfx.re/t/random-added-local-code-random-server-scripts-in-fxmanifest/4872285/16
--------------------
Clone the repo into your `resources/[system]/[builders]` and run `npm i` or any other package manager command to install the dependencies (for some reason fxserver didn't install them for me here)
-----
Add this to your `server.cfg` somewhere early, preferably next to default webpack
```
ensure webpack
```
```lua
dependencies {
    'yarn',
    'webpack'
}

webpack_config 'webpack.prod.js'
```
Keep in mind FXServer is limited to fork of Node.js 16.9 so you WILL run into dependency issues when installing the latest and greatest stuff that might depend on Node.js 16.10+
