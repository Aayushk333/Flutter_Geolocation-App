# Flutter_Geolocation-App



Plugin 1: ‘location’
The ‘location’ plugin is the simplest way to get and track a user’s location without the hassle of any boilerplate code.

Setting up is simple enough:

Add plugin to the pubspec.yaml
dependencies:
  location: ^1.4.1
2. Add a permission to Android Manifest:

<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />


3. Add permissions to iOS Info.plist

<key>NSLocationAlwaysUsageDescription</key>
<string>Needed to access location</string>
<key>NSLocationWhenInUseUsageDescription</key>
<string>Needed to access location</string>


In Android 6.0+, we need to ask access to location in runtime, which this package handles on its own.

Getting a one-time location

It allows us to get two things:

A one-time location of the user
A stream allowing us to listen to the location of the user.
I have created a simple app which gets the one-time location of the user like above.

This package does not need much setup and the code is rather straightforward.

First, simply initialise a Location object.

var location = new Location();
location is not the location of the user itself but a class that helps us get it.

The location is returned as a map with keys like “latitude”, “longitude”, etc.

Map<String, double> userLocation;
And finally, getting the location is as simple as:

userLocation = await location.getLocation();
