# Cloud Foundry buildpack: Meteorite

This build pack allows you to easily deploy meteor apps to Cloud Foundry using [meteorite](http://github.com/oortcloud/meteorite). It's easy to use different branches of meteor and any smart package you can lay your hands on.

## Usage

Create a CF app and bind it to a MongoDB service. Then run the following command in your terminal:

```
cf push [APP_NAME] -b https://github.com/oortcloud/heroku-buildpack-meteorite.git
```

## NOTES

You can specify meteor settings by setting the `METEOR_SETTINGS` environment variable:

```
cf set-env [APP_NAME] METEOR_SETTINGS '{"herp":"derp"}'
```

You need to have a service for MongoDB available and bound to the app. Alternatively, you can set `MONGO_URL` to point to your MongoDB outside of Cloud Foundry with the command:

```
cf set-env [APP_NAME] MONGO_URL mongodb://[SERVER]:[PORT]/[DB] # substitute your configuration values
```

## Websockets

To enable websockets on run.pivotal.io, you will need to use SSL over port 4443, e.g., `https://[APP_NAME].cfapps.io:4443/`
