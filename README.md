[![Build Status](https://travis-ci.org/kuzzleio/kuzzle-plugin-mqtt.svg?branch=master)](https://travis-ci.org/kuzzleio/kuzzle-plugin-mqtt) [![codecov.io](http://codecov.io/github/kuzzleio/kuzzle-plugin-mqtt/coverage.svg?branch=master)](http://codecov.io/github/kuzzleio/kuzzle-plugin-mqtt?branch=master) [![Dependency Status](https://david-dm.org/kuzzleio/kuzzle-plugin-mqtt.svg)](https://david-dm.org/kuzzleio/kuzzle-plugin-mqtt)

![logo](https://camo.githubusercontent.com/e40bd0387af8440d3276c9fdea60650d9f787482/687474703a2f2f6b757a7a6c652e696f2f67756964652f696d616765732f6b757a7a6c652e737667)

# Kuzzle compatibility

Versions 1.x of this plugin are compatible with Kuzzle v1.0.0-RC.4 and upper.
# Protocol plugin: mqtt

Protocol plugin adding mqtt support to Kuzzle.

# Manifest

This plugin doesn't need any right.

# Configuration

You can override the configuration in your `config/customPlugins.json` file in Kuzzle:

| Name | Default value | Type | Description                 |
|------|---------------|-----------|-----------------------------|
| ``port`` | ``1883`` | Integer > 1024 | Network port to open |
| ``room`` | ``"Kuzzle"`` | String | Name of the room listened by the plugin |

# How to use

Kuzzle may send a multitude of messages to a client, either to respond to multiple asynchronous requests, or to notify events on client's subscriptions.  
To allow a client to link a response to a request or to a subscription, Kuzzle normally features a room system for protocols allowing it.

Since Kuzzle has its own subscription system, all messages sent through this protocol contain an additional `room` attribute at the root of the message structure. Clients connecting to Kuzzle using this protocol must use this field to dispatch incoming messages to the right parts of an application.

This `room` attribute is either:

* a request `requestId`, for request responses
* a `channel` (see [Kuzzle subscriptions](http://kuzzle.io/api-reference/#on)), for notifications on subscriptions


# How to create a plugin

See [Kuzzle documentation](http://kuzzle.io/guide/#plugins) about plugin for more information about how to create your own plugin.

# About Kuzzle

For UI and linked objects developers, [Kuzzle](https://github.com/kuzzleio/kuzzle) is an open-source solution that handles all the data management
(CRUD, real-time storage, search, high-level features, etc).

[Kuzzle](https://github.com/kuzzleio/kuzzle) features are accessible through a secured API. It can be used through a large choice of protocols such as REST, Websocket or Message Queuing protocols.
