# Cordova Skeleton

This is a reasonably configured skeleton application for Cordova based
mobile apps, because I don't want to spend all morning setting this lot
up again.

On startup the app will set up everything device related, and then pull
`www/application.js` from the content server to start the actual application.

## Development Setup

1. Edit `config.xml` and set an application name and identifier.
2. Make sure you have Node.js installed. (Homebrew, apt, etc can help)
3. For extra awesome, install [direnv](http://direnv.net) to automated
   environment configuration. (Run `direnv allow` to let it load the
   project's config).
4. Install dependencies with `npm install`.
5. Add any platforms you're going to work with: `cordova platform add android`.

## Running the Development Server

The app pulls its assets from an HTTP server, so you'll need to start that up 
for local development.

`nf start -p$AN_EMPTY_PORT`

## Configuration

The file `config.json` contains configuration for the application, at the moment
just a content endpoint to get additional content from. You can add extra variables
to that file, and accompanying meta tags to the head of `www/index.html` to have 
them replaced as well. Substitution is done on building the app.

## Installing on a Mobile Device

### Android

1. Set up the Android depedencies using the [Cordova Android Platform Guide](http://cordova.apache.org/docs/en/3.5.0/guide_platforms_android_index.md.html#Android%20Platform%20Guide)
2. Make sure you can connect to your device in debug mode with `adb devices`. It should list your phone as connected. If it isn't, find out how to turn on USB Debugging.
3. Forward the development server port to your device. `adb forward $PORT 8888`. Leave 8888 as is, since the Cordova app assumes that port is being used.
4. Push the app to your device with `cordova run`.

### iOS

TODO
