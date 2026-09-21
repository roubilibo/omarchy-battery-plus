# Battery Plus

An Omarchy bar widget that replaces the standard power panel with an Apple-style
horizontal battery indicator and a richer battery/power panel.

## Features

- Horizontal battery outline with either the current percentage or a charge fill inside.
- Right-click the bar widget to toggle between percentage and charge-fill modes.
- Shows battery health in the panel and battery percentage plus time remaining
  in the bar tooltip. While charging, the tooltip shows the estimated time to
  full instead.
- Color states:
  - green while charging;
  - red below 20% while discharging;
  - orange for the `power-saver` profile;
  - blue for `Long_Life` charge mode while connected to AC power.
- Left-click opens the battery panel with battery statistics and power profiles.
- Shows and changes the kernel `charge_types` interface when available, including
  Fast, Standard, and Long Life modes.
- Uses the newer `charge_types` interface as the single visible control. The
  legacy `conservation_mode` scripts remain in the repository for compatibility,
  but are no longer shown in the panel.

## Requirements

- Omarchy with its standard shell power commands and Quickshell panel support.
- A battery-backed system.
- Charge mode controls require a battery exposing the kernel `charge_types`
  interface. Other systems will keep the charge mode section hidden.

## Install

```sh
omarchy plugin add https://github.com/roubilibo/omarchy-battery-plus.git --enable
```

This is the repository used by this project. Omarchy clones it as a
git-managed plugin at `~/.config/omarchy/plugins/roubilibo.battery-plus/`.
For unattended installation, append `--yes` to skip the confirmation prompt.

Place the widget in the bar if needed:

```sh
omarchy bar move roubilibo.battery-plus --section right
```

Click the widget to open its panel. Right-click it to toggle between percentage
and charge-fill modes in the bar. The bar tooltip shows the current battery
percentage and time left (or time to full while charging).

## Remove

```sh
omarchy plugin remove roubilibo.battery-plus
```

## Development

For local development, clone the same remote repository somewhere in your
Omarchy workspace:

```sh
git clone https://github.com/roubilibo/omarchy-battery-plus.git ~/Omarchy/roubilibo.battery-plus
```

Validate the Omarchy manifest with:

```sh
omarchy plugin validate ~/Omarchy/roubilibo.battery-plus
```

## License

MIT. See [LICENSE](LICENSE).
