# hass-dual-color-icons
[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg)](https://github.com/hacs/integration)
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/sisimomo/hass-dual-color-icons)](https://github.com/sisimomo/hass-dual-color-icons/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![GitHub file size in bytes](https://img.shields.io/github/size/sisimomo/hass-dual-color-icons/dist/hass-dual-color-icons.js?label=plugin%20size)
![GitHub last commit](https://img.shields.io/github/last-commit/sisimomo/hass-dual-color-icons)
[![GitHub closed issues by-label](https://img.shields.io/github/issues-closed/sisimomo/hass-dual-color-icons/icon%20request?label=community%20requests)](https://github.com/sisimomo/hass-dual-color-icons/issues?q=is%3Aclosed+label%3A"icon+request")

Dual colors vector icons for Home Assistant.
These icons are dual color counter fit of other home assistant icons set like [Material Design Icons (MDI)](https://github.com/Templarian/MaterialDesign) or [hass-hue-icons](https://github.com/arallsopp/hass-hue-icons).


## Installation

hass-dual-color-icons has been accepted into the [Home Assistant Community Store (HACS)](https://hacs.xyz).

### HACS (Recommended):
This is the recommended way to install hass-dual-color-icons. To install:

- Open HACS (installation instructions are [here](https://hacs.xyz/docs/installation/installation/)).
- Go to "Frontend" section
- Click menu on the top right
- Click on custom repositories
- Add https://github.com/sisimomo/hass-dual-color-icons as an Lovelace
- Click button with "+" icon
- Search for "hass dual color icons" and install it.
- Add the following to your configuration.yaml, save and restart HA.
```
frontend:
  extra_module_url:
    - /hacsfiles/hass-dual-color-icons/hass-dual-color-icons.js
```

### Manual:
- Copy `dist/hass-dual-color-icons.js` into your `config/www` folder.
- Go to Configuration -> Lovelace Dashboards -> Resources -> Add Resource
- set url as `/local/hass-dual-color-icons.js` and Resource Type as `Javascript Module`.
- Add the following to your configuration.yaml, save and restart HA.
```
frontend:
  extra_module_url:
    - /local/hass-dual-color-icons.js
```

- Save, restart Home Assistant.


## Usage
- In your entity editor, specify an icon as `dci:icon-name`
- If you set `state_color: true` in your card, you'll see the icons get colorised based upon the current RGB setting.

### Example:

```
title: My Room
state_color: true
type: entities
entities:
  - entity: light.my_ceiling_light
    name: My Ceiling Light
    icon: dci:hue_ceiling-still
```

### Icon Requests?
Your dual color icon is not there? Let me know what's missing by raising a [Custom Icon Request](https://github.com/sisimomo/hass-dual-color-icons/issues/new?labels=icon+request&template=custom-icon-request.md&title=Icon%20Request%20%5Bname%20of%20fixture%5D).

### All Icons
![lovelace_example](/docs/icons.png)

### Sample Dash
With view icons and state color applied.
![lovelace_example](/docs/examples/274958492-39adba16-e687-4931-9e8c-8e6160eb930e.png)
![lovelace_example](/docs/examples/274958507-a5820f92-1736-49c3-916d-99503b15be18.png)

<details>
  <summary>The dashboard</summary>
  
  ```yaml
  title: Home
  views:
    - path: default_view
      title: Home
      badges: []
      cards:
        - square: false
          type: grid
          cards:
            - type: tile
              entity: light.virtual_light_1
              icon: dci:mdi_ceiling-light
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_1
              icon: dci:mdi_coach-lamp
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_1
              icon: dci:mdi_doorbell
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_ceiling-light
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_coach-lamp
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_doorbell
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
          columns: 3
        - square: false
          type: grid
          cards:
            - type: tile
              entity: fan.virtual_fan_1
              icon: dci:mdi_fan
              color: white
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-opactity: 1;
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                    svg{
                     animation: 2s linear 0s infinite normal none running rotating;
                    }
                    @keyframes rotating {
                      0% { 
                        transform: rotate(0); 
                      }
                      100% { 
                        transform: rotate(360deg);
                      }
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_3
              icon: dci:mdi_floor-lamp
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_3
              icon: dci:mdi_lamp
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: fan.virtual_fan_2
              icon: dci:mdi_fan
              color: white
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-opactity: 1;
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                    svg{
                     animation: 2s linear 0s infinite normal none running rotating;
                    }
                    @keyframes rotating {
                      0% { 
                        transform: rotate(0); 
                      }
                      100% { 
                        transform: rotate(360deg);
                      }
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_floor-lamp
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_lamp
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
          columns: 3
        - square: false
          type: grid
          cards:
            - type: tile
              entity: light.virtual_light_4
              icon: dci:mdi_mirror-rectangle
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_4
              icon: dci:mdi_television
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_4
              icon: dci:mdi_vanity-light
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_mirror-rectangle
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_television
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:mdi_vanity-light
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
          columns: 3
        - square: false
          type: grid
          cards:
            - type: tile
              entity: light.virtual_light_5
              icon: dci:hue_adore
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_5
              icon: dci:hue_bulb-group-classic-4-alt
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_5
              icon: dci:hue_ceiling-aurelle-circle
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:hue_adore
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:hue_bulb-group-classic-4-alt
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: light.virtual_light_2
              icon: dci:hue_ceiling-aurelle-circle
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
          columns: 3
        - square: false
          type: grid
          cards:
            - type: tile
              entity: switch.virtual_switch_1
              icon: dci:hue_ceiling-still
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: switch.virtual_switch_1
              icon: dci:hue_lightstrip-tv
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: switch.virtual_switch_1
              icon: dci:hue_ceiling-still
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: switch.virtual_switch_2
              icon: dci:hue_ceiling-still
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: switch.virtual_switch_2
              icon: dci:hue_lightstrip-tv
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
            - type: tile
              entity: switch.virtual_switch_2
              icon: dci:hue_ceiling-still
              card_mod:
                style:
                  ha-tile-icon[data-state="on"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-secondary-color: rgb(158, 158, 158);
                    }
                  ha-tile-icon[data-state="off"]$ ha-icon$ ha-svg-icon$: |
                    svg path {
                      --icon-primary-color: rgb(158, 158, 158);
                      --icon-primary-opactity: 0.4;
                      --icon-secondary-color: currentcolor;
                      --icon-secondary-opactity: 1;
                    }
          columns: 3
        - show_name: false
          show_icon: true
          show_state: false
          type: glance
          entities:
            - entity: sensor.sun_next_dawn
              icon: dci:mdi_ceiling-light
            - entity: sensor.sun_next_dusk
              icon: dci:mdi_coach-lamp
            - entity: sensor.sun_next_midnight
              icon: dci:mdi_doorbell
            - entity: sensor.sun_next_noon
              icon: dci:mdi_fan
            - entity: sensor.sun_next_rising
              icon: dci:mdi_floor-lamp
            - entity: sensor.sun_next_setting
              icon: dci:mdi_floor-lamp
            - entity: input_button.test_1
              icon: dci:mdi_mirror-rectangle
            - entity: input_button.test_2
              icon: dci:mdi_television
            - entity: input_button.test_3
              icon: dci:mdi_vanity-light
            - entity: input_button.test_4
              icon: dci:hue_adore
            - entity: input_button.test_5
              icon: dci:hue_bulb-group-classic-4-alt
            - entity: input_button.test_6
              icon: dci:hue_ceiling-aurelle-circle
            - entity: input_button.test_7
              icon: dci:hue_ceiling-still
            - entity: input_button.test_8
              icon: dci:hue_lightstrip-tv
          columns: 7
  ```
</details>

## Troubleshooting:

### Can't ever see the icons?
If you cannot see the new icons, or you get an empty box where you're expecting an icon, flush your network cache.

### Icons don't show on first load of the dash?
Did you add the frontend extra_module_url in your configuration.yaml? See the [installation section](#installation) for details.

## Thanks and Props
- @arallsopp for the [hass-hue-icons](https://github.com/arallsopp/hass-hue-icons) icon set.
