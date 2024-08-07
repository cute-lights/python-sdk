# Cute Lights

Cute Lights is a simple library for controlling various types of smart lights threw a unified api. It is designed to be simple to use and easy to extend. It can be used as a rust crate or a c shared library. With bindings for dotnet and python.

## Supported Lights

-   [x] Philips Hue
-   [x] Tp-Link Kasa
-   [x] Govee (Must have lan control enabled)
-   [ ] OpenRgb

## Usage

```python
import time
import cute_light

lights = cute_light.discover_lights()
frame = cute_light.Frame()

state = True
while True:
    frame.set_on_all(lights, state)
    state = not state
    frame.run()
    frame.clear()
    time.sleep(0.5)
```

## Configuration

The configuration file is located at `~/.config/cute_lights/lights.toml`. It is used to store the ip addresses and api keys for lights. The file should look like this:

```toml
[kasa]
enabled = true
addresses = [
    "192.168.86.xx",
    "192.168.86.xx",
]

[govee]
enabled = true
addresses = ["192.168.86.xx"]

[hue]
enabled = true
bridge_ip = "192.168.86.xx"
username = "<Your Hue Api Key>"
```

## Language Bindings

-   [x] Rust