# Mobile computing project example

This repository contains the source code and documentation for a project built with Flutter

## Usage

Initially this project is intended to be en example on how to organise your source code following the course guidelines. This contains:

- Documentation: the [`/docs`](docs/) folder contains the expected documentation for the project.
- Continuous integration workflow: the [`flutter.yml`](.github/workflows/flutter.yml) file show how to achieve continuous integration for this project. You can copy this file in your own project.
  - `build`: this job compiles and generates an APK file that can be used to test the application.
  - `firebase-test-lab`: this job tests your application using Firebase Test Lab.
- Dev Containers: In case you want to use dev containers with your project, the [`.devcontainer`](.devcontainer/) folder contains the configuration needed to develop using dev containers.

## Flutter: Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
