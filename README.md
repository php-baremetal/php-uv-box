# php-uv-box

A UV curing box for resin 3D prints, controlled by firmware written in PHP.

It is a project built on [php-baremetal](https://github.com/php-baremetal): the box's controller is an
ESP32-S3 running the real PHP interpreter through [php-esp32](https://github.com/php-baremetal/php-esp32),
so the logic that drives the curing cycle is a plain PHP script rather than C or Arduino code. It is
both a useful workshop tool and a real-world showcase of what PHP can do on a microcontroller.

> **Status: work in progress.** The enclosure is being designed in FreeCAD. The electronics and the PHP
> firmware are not in this repository yet.

## How it works

- **Enclosure**: a 3D-printable case designed in FreeCAD, assembled with M3 screws.
- **Controller**: an ESP32-S3 board running php-esp32.
- **Firmware**: a PHP script that runs the curing cycle, executed on the chip by the official Zend engine.
- **Tooling**: the firmware is built and flashed with [phpflash](https://github.com/php-baremetal/flash-tool).

## Repository layout

```
Cad/
├── FullAssembly.FCStd        # complete assembly of the box
├── ShareVarSet.FCStd         # shared parameters (dimensions) used by the parts
├── A4_Landscape_themplate.svg  # drawing template for technical sheets
├── parts/
│   ├── body/                 # body parts
│   ├── bottom/               # bottom parts
│   └── tests/                # test pieces
└── external-components/
    └── M3x8/                 # M3x8 screw model
```

Open `Cad/FullAssembly.FCStd` in [FreeCAD](https://www.freecad.org/) to see the whole box. The parts read
their main dimensions from `ShareVarSet.FCStd`, so edit them there to change the design consistently.

## License

This project is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
(see [LICENSE](LICENSE)). You are free to build one for yourself, modify the design and share your
changes under the same license, as long as you credit the author. Commercial use, including
manufacturing and selling the box, is not allowed without a separate license: contact
[gianfri@php-baremetal.com](mailto:gianfri@php-baremetal.com).
