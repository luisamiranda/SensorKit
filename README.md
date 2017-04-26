# SensorKit

SensorKit is an open library and a set of tools for sensors and machine learning. If you are a sensor manufacturer, the library provides a high level SDK to make it easier for developers to use your products. For developers, the library makes it very easy to connect Bluetooth LE sensors (or other sensors, e.g. WiFi etc) to you app, gather sensor data and process it with advanced machine learning and AI algorithms.

![SensorKit running in the app](https://github.com/kevinash/SensorKit/blob/master/assets/sensorkit_app_250.png)

## How to add your sensor to SensorKit

* Add your own sensor to [SensorsRegistry](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorsRegistry.cs). SensorKit is open to all sensor manufacturers.

* Make sure to provide [SensorCapabilities](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorCapabilities.cs) describing what your sensor can do in the [SensorsRegistry](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorsRegistry.cs). If your sensor can do more than that, add new capability to [SensorCapabilities](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorCapabilities.cs)

* Clone and create a new connector class based on [SensorConnector](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorKitConnector.cs) class for your sensor (naming convention is ...Connector e.g. MySensorConnector.cs). This class describes how your sensor connects with your device.

* DONE! SensorKit automatically polls/accepts notifications from your sensor and updates its data model.

## How to use SensorKit in your app

A good place for SensorKit is your Universal app's App.xaml.cs file: declare Sensors property

```C#
public SensorKit Sensors { get; set;}
```

Then instantiate SensorKit in your OnLaunched event:

```C#
// make an instance of SensorKit
Sensors = new SensorKit();
```

Then, when your app needs to scan for sensors supported by SensorKit, add:

```C#
Sensors.StartScanning();
```

## Sensors supported by SensorKit

Add your own sensor to [SensorsRegistry](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorsRegistry.cs). SensorKit is open to all sensor manufacturers. If you are a registered developer, simply update GitHub with your sensor information in the open [SensorsRegistry](https://github.com/kevinash/SensorKit/blob/master/SensorKit/SensorsRegistry.cs) and you can use SensorKit to connect to any sensors supported by the kit easily:

[![illumiSki](https://github.com/kevinash/SensorKit/blob/master/assets/illumiski-150.png)](https://illumisens.com/collections/frontpage/products/illumiski-ski-sensor) [illumiSki](https://illumisens.com/collections/frontpage/products/illumiski-ski-sensor) sensor addon for ski and snowboard

![illumiSens](https://github.com/kevinash/SensorKit/blob/master/assets/illumisens-150.png)
[illumiSens](https://illumisens.com/collections/frontpage/products/illumisens-body-sensors) body sensor with straps

![illumiBand](https://github.com/kevinash/SensorKit/blob/master/assets/illumiband-150.png)
[illumiBand](https://illumisens.com/collections/frontpage/products/illumiband-wearable-sensors) wearable wrist sensor

## Apps using SensorKit

[Active Fitness](http://activefitness.co) - Active Fitness is a fitness tracking app and a social fitness network of 2 million users

[Winter Sports](http://winter-sports.co) - Winter Sports is an app geared towards ski and snowboard enthusiasts

