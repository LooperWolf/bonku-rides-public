***This is a documentation of my work at Bonku, Only snippets, and some files of code can be shown and not the full stack***

# How it started
Before I joined, Bonku was running its mobile platform using React Native and RESTful api with GIN on Golang.
My good friend and CEO wanted the application to run faster, more efficient, and with more modern animations so we landed on Flutter (dart) 1.0 for the Front-End and gRPC for Backend.

![Flutter 1 0](https://github.com/user-attachments/assets/63dbad40-7efd-427b-9882-5763d1f09e16)

Bonku Rides was my second product that I have ever built from scratch without a place to spring board from.
My responsibilities were to plan the mobile infrastructure, backend infrastructure, design the application, develop, and launch the product onto the App store and Play store and migrate all the RESTful API calls to gRPC on Golang.

# React Native Issues
In 2020 when we decided to scrap everything and rebuild on Flutter, React Native was having performance issues when handling animation interpolation, state update issues, and much more due trying its compiler and rendering engine that was translating from JS to Native Code.

# RESTful API to gRPC
There wasn't an immediate issue with REST was of handling, but for reduce latency, bandwith, and support on streaming, we opted for gRPC to adopt real time live data sync and updates.

This was very abundant when we have multiple elements overlaying our Google Maps leading to huge spikes in the profilier.

# Adoption of Flutter
I'll be going into key features that, I believe, took me a while to develop and get right even if its still not perfect yet.

## In House Global State Management
Flutter in its early stages was difficult to say the least, multiple dependecies changes, rendering engine changes, and lack of State Manangement Libraries.
Without a reliable state management and constraint of time to get the first launch out, I've planned the infrastructure to handle Global State Changes through ValueNotifiers and ChangeNotifiers. (This was later on improved to purely use Value Notifiers)
```dart
  final ValueNotifier<int> selectedServiceNotifier = ValueNotifier(4);
  final ValueNotifier<int> selectedRouteNotifier = ValueNotifier(0);

  int get selectedRoute => selectedRouteNotifier.value;
  set selectedRoute(int value) => selectedRouteNotifier.value = value;
  int get selectedService => selectedServiceNotifier.value;
  set selectedService(int value) => selectedServiceNotifier.value = value;

```
The few example above is a usage of a value that is modifiable by multiple interactions but dictates the render of only one element.
Utilizing ValueNotifier to direct render states when value is modified, and modifying the readability and usability by using get and sets to modify how values are parsed.

## Google Map Animated Gradient Polyline with Leaflet

### Why Overlay with Leaflet?

## Leaflet Marker Collision Physics and Boundry control

## Payment Modal Collision Physics, Animation, and Optimization



