# ESPHome Configuration

## Introduction

The following secions describe each individual component.

Note that if you need a specific version oft the component, you can use the following code example instead of the slim package reference.

```yaml
packages:
  home-assistant-voice:
    url: https://github.com/mariopenzendorfer/esphome-public
    ref: # preferred commit version or tag
    files:
      - base/[component].yaml
```

## home-assistant-voice

Supported hardware: [Home Assistant Voice PE](https://www.home-assistant.io/voice-pe/)

Test with ESPHome build: [2026.5.1](https://esphome.io/changelog/2026.5.0/)

### What is it?

This is a modified version, based the original **home-assistant-voice** component (see [here](https://github.com/esphome/home-assistant-voice-pe/blob/dev/home-assistant-voice.yaml)), which allows to output sound via the internal speakers while an audio jack is connected.

The output is always routed to both the audio jack and the internal speaker. The internal speaker can be switched off manually and is automatically switched off, when music is playing.

This allows for a simple setup, in which a sound system is permanently connected (but not always powered on), and the home-assistant-voice device is still used for voice control.

### How to use this component

In the below code example, just change the substitutions for `mac` and `api_key` to your preferred ones. Meaningfully, the `mac` parameter should be the last 6 characters of the devices mac address, to allow for easy identification.

The device will appear as **home-assistant-voice-[mac]**.

```yaml
substitutions:
  mac: "abcdef"
  api_key: "..."

packages:
  home-assistant-voice: github://mariopenzendorfer/esphome-public/base/home-assistant-voice.yaml
```

## respeaker-lite

Supported hardware: [reSpeaker Lite Voice Kit](https://www.seeedstudio.com/ReSpeaker-Lite-Voice-Assistant-Kit-p-5929.html)

Test with ESPHome build: [2026.5.1](https://esphome.io/changelog/2026.5.0/)

### What is it?

This is firmware for the **reSpeaker Lite** device to make it a fully fledged Sendspin streamking device, compatible with [music-assistant](https://www.music-assistant.io/) and similar to the **Home Assistant Voice PE**.

### How to use this component

In the below code example, just change the substitutions for `mac`, `api_key`, `ota_pwd` and `ap_pwd` (fallback hotspot password) to your preferred ones. Meaningfully, the `mac` parameter should be the last 6 characters of the devices mac address, to allow for easy identification.

The device will appear as **respeaker-lite-[mac]**.

```yaml
substitutions:
  mac: "abcdef"
  api_key: "..."
  ota_pwd: "..."
  ap_pwd: "..."

packages:
  respeaker-lite: github://mariopenzendorfer/esphome-public/base/respeaker-lite.yaml
```
