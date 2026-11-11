# Example for `max7219` driver

## Datasheet

[MAX7219/MAX7221](https://datasheets.maximintegrated.com/en/ds/MAX7219-MAX7221.pdf)

## What it does

The example configures one or more of `max7219` devices on a SPI bus. The
number of cascaded display modules is `CONFIG_EXAMPLE_CASCADE_SIZE` (the
default is 1).

It shows some patterns on the display in a loop.

## Wiring

The example assumes that you are using a LED matrix display module with
`MAX7219`. These modules usually come with:

* `MOSI` or `DIN` pin
* `CLK` pin
* `CS` pin
* `VCC` and `GND`

| Name | Description | Defaults |
|------|-------------|----------|
| `CONFIG_EXAMPLE_PIN_NUM_MOSI` | GPIO number for `MOSI`, or `DIN` | "19" for `esp32`, `esp32s2`, and `esp32s3`, "4" for `esp32c2`, `esp32c3`, `esp32c5`, `esp32c6`, `esp32c61`, `esp32h2`, and `esp32p4` |
| `CONFIG_EXAMPLE_PIN_NUM_CLK`  | GPIO number for `CLK`  | "18" for `esp32`, `esp32s2`, and `esp32s3`, "6" for `esp32c2`, `esp32c3`, `esp32c5`, `esp32c6`, `esp32c61`, `esp32h2`, and `esp32p4` |
| `CONFIG_EXAMPLE_PIN_CS` | GPIO number for `CS` | "5" for `esp32`, `esp32s2`, `esp32s3`, `esp32c2`, `esp32c3`, `esp32c5`, `esp32c6`, `esp32c61`, `esp32h2`, and `esp32p4` |

You may cascade several modules by increasing `CONFIG_EXAMPLE_CASCADE_SIZE`.
In that case, be aware of current consumed by the modules. You need a stiff
power source for the modules.
