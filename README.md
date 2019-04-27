# ESPHome Devices

Collection of IoT devices using ESPHome

## Introduction

This repository is my personal collection of IoT devices based on ESP and using the framework [ESPHome](https://esphome.io).

The devices are interfaced into [Home Assistant](https://www.home-assistant.io/). So, most of the configurations rely on Home Assistant and uses the ESPHome native API.

Most of the devices use custom hardware based on ESP8266 or ESP32. The devices are used in my home automation system.

## Dependencies

### [ESPHome](https://esphome.io)

ESPHome is a C++ framework to create custom firmware for ESP devices based on YAML file. The YAML files describe the hardware configuration of the ESP and the various functions needed. Then the ESPHome framework turns this YAML file into C++ files and create the final firmware image.

This is a fantastic tool for rapid prototyping and quick updates to IoT devices.

Go to the [Getting Started Tutorial](https://esphome.io/guides/getting_started_command_line.html) to set up your environment and create your first configuration.

### [Home Assistant](https://www.home-assistant.io/)

Home Assistant is a home automation framework developed in Python3. It provides support for a lot of [components](https://www.home-assistant.io/components/) ... a lot! The community is big, very helpful and amazing. If you are into home automation and you don't know Home Assistant, then this is my gift to you: https://www.home-assistant.io/

The ESP configurations in this repo use Home Assistant with the component [ESPHome](https://www.home-assistant.io/components/esphome/).

Go to the [Getting Started Tutorial](https://www.home-assistant.io/getting-started/) to set up your own installation of Home Assistant.
You can also modify the configurations to use MQTT instead of the Home Assistant native API.

## Installation

The installation focuses of setting up the Python2 Virtual Environnement. So obviously you need Python 2.7 and pip installed on your development system.

For my own need, I create the virtual environment inside the local copy of the repo. I will assume that your are on in a Linux box. If your are on Windows, I'm sorry for you...

1. Clone this repo:

    `$ git clone https://github.com/eklex/esphome-devices.git`

2. Go into the local repo:

    `$ cd esphome-devices`

3. Install Python2 Virtual Env:

    `$ sudo pip install virtualenv`

4. Create the Virtual Env:

    `$ virtualenv env`

5. Activate the Virtual Env:

    `$ source env/bin/activate`

    You should see your prompt changing to `(env) $`. From here on, everything you install with pip will be installed into the Virtual Env only, and won't populate your Python2 installation.

6. Install the ESPHome framework:

   `$ sudo pip install esphome`

The environment is now ready.

Next time, you need to build something, you simply activate the Virtual Env first, and then you can build:

1. Go into the local repo:

    `$ cd esphome-devices`

2. Activate the Virtual Env:

    `$ source env/bin/activate`

## Storing Password

If you try to build, the build will fail because it's missing the file secrets.yaml. This file contains the various passwords for WiFi, OTA or Home Assistant.

1. Copy the file secrets-template.yaml to secrets.yaml:

    `$ cp collection/secrets-template.yaml collection/secrets.yaml`

2. Update the passwords with your own in collection/secrets.yaml.

## Output the full configuration

`$ esphome <filename>.yaml config`

## Build the configuration

`$ esphome <filename>.yaml compile`

## Program the configuration

`$ esphome <filename>.yaml run`
