# Home-Assistant SunSynk Timer
A simple template to compliment the SunSyk ESP Code

SunSynk Dashboard - Creates a SunSynk Logger System Timer dash to compliment the ESP logger

![SunSynk System Timer](<SunSynk System Timer-1.png>)

```
type: vertical-stack
cards:
  - type: tile
    entity: switch.sunsynk_logger_system_timer
    icon: mdi:timer-outline
    vertical: true
  - type: horizontal-stack
    cards:
      - type: entities
        entities:
          - entity: select.sunsynk_logger_energy_pattern
            name: Energy Pattern
        state_color: true
      - type: entities
        entities:
          - entity: select.sunsynk_logger_work_mode
            name: Work Mode
        state_color: true
  - type: entities
    entities:
      - entity: switch.sunsynk_logger_grid_charge_timezone1
        type: custom:multiple-entity-row
        name: Program 1
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_logger_time_slot_1
            name: From
          - entity: sensor.sunsynk_logger_time_slot_2
            name: To
          - entity: sensor.sunsynk_logger_setting_soc_timezone1
            name: SOC
            format: precision0
      - entity: switch.sunsynk_logger_grid_charge_timezone2
        type: custom:multiple-entity-row
        name: Program 2
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_logger_time_slot_2
            name: From
          - entity: sensor.sunsynk_logger_time_slot_3
            name: To
          - entity: sensor.sunsynk_logger_setting_soc_timezone2
            name: SOC
            format: precision0
      - entity: switch.sunsynk_logger_grid_charge_timezone3
        type: custom:multiple-entity-row
        name: Program 3
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_logger_time_slot_3
            name: From
          - entity: sensor.sunsynk_logger_time_slot_4
            name: To
          - entity: sensor.sunsynk_logger_setting_soc_timezone3
            name: SOC
            format: precision0
      - entity: switch.sunsynk_logger_grid_charge_timezone4
        type: custom:multiple-entity-row
        name: Program 4
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_logger_time_slot_4
            name: From
          - entity: sensor.sunsynk_logger_time_slot_5
            name: To
          - entity: sensor.sunsynk_logger_setting_soc_timezone4
            name: SOC
            format: precision0
      - entity: switch.sunsynk_logger_grid_charge_timezone5
        type: custom:multiple-entity-row
        name: Program 5
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_logger_time_slot_5
            name: From
          - entity: sensor.sunsynk_logger_time_slot_6
            name: To
          - entity: sensor.sunsynk_logger_setting_soc_timezone5
            name: SOC
            format: precision0
      - entity: switch.sunsynk_logger_grid_charge_timezone6
        type: custom:multiple-entity-row
        name: Program 6
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_logger_time_slot_6
            name: From
          - entity: sensor.sunsynk_logger_time_slot_1
            name: To
          - entity: sensor.sunsynk_logger_setting_soc_timezone6
            name: SOC
            format: precision0
    state_color: true
view_layout:
  grid-area: a

```