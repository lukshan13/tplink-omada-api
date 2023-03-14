# What's this?

A basic Python client for calling the TP-Link Omada controller API.

## Installation

```console
pip install tplink-omada-client
```

## Supported features

Only a subset of the controller's features are supported:
* Automatic Login/Re-login
* Basic controller information
* List sites
* Within site:
    * List Devices (APs, Gateways and Switches)
    * Basic device information
    * Port status and PoE configuraton for Switches (<-- What I actually needed)

Tested with OC200 on Omada Controller Version 5.5.7 - 5.7.6. Other versions may not be fully compatible.

## CLI

This package provides a simple CLI for interacting with one or more Omada Controllers. To start using the
CLI, you must first target a Controller.

```sh
$ omada -t NAME target --url https://your.omada.controller.here --user admin --password password --site MySite
```

Where `NAME` is a name of your choosing to identify the targeted controller. `--site` defaults to the Omada
default site name, 'Default'.  If you do not provide a password as an argument, you will be prompted for a
password.

Once you have successfully targeted a controller you can test that things are working by running:

```sh
$ omada -t NAME devices
```

This will list all the devices being managed by your controller.

To see a list of all the available commands, run:

```sh
$ omada -h
```

The CLI is still young so if there is any functionality you need, please create an issue and let us know.

## Future

The available API surface is quite large. More of this could be exposed in the future.
There is an undocumented Websocket API which could potentially be used to get a stream of updates. However,
I'm not sure how fully featured this subscription channel is on the controller. It seems to be rarely used,
so probably doesn't include client connect/disconnect notifications.

## Contributing

There is a VS Code development container, which sets up all of the requirements for running the package.

## License

MIT Open Source license.
