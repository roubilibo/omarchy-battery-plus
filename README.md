# Battery Plus

An Omarchy bar widget that replaces the standard power panel with an Apple-style
horizontal battery indicator and a richer battery/power panel.

## Features

- Horizontal battery outline with the current percentage inside.
- Right-click the bar widget to show or hide the percentage.
- Color states:
  - green while charging;
  - red below 20% while discharging;
  - orange for the `power-saver` profile;
  - blue for Lenovo conservation mode while connected to AC power.
- Left-click opens the battery panel with battery statistics and power profiles.
- Detects and toggles Lenovo IdeaPad conservation mode through the Omarchy Polkit
  agent when the kernel exposes it.

## Requirements

- Omarchy with its standard shell power commands and Quickshell panel support.
- A battery-backed system.
- Lenovo conservation controls require an IdeaPad-compatible `ideapad_acpi`
  kernel interface. Other systems will keep the conservation section hidden.

## Install

```sh
omarchy plugin add https://github.com/roubilibo/omarchy-battery-plus.git --enable
```

Place the widget in the bar if needed:

```sh
omarchy bar move roubilibo.battery-plus --section right
```

Click the widget to open its panel. Right-click it to toggle the percentage in
the bar.

## Remove

```sh
omarchy plugin remove roubilibo.battery-plus
```

## Development

The development copy lives at:

```text
~/Omarchy/roubilibo.battery-plus
```

Validate the Omarchy manifest with:

```sh
omarchy plugin validate ~/Omarchy/roubilibo.battery-plus
```

## License

MIT. See [LICENSE](LICENSE).
