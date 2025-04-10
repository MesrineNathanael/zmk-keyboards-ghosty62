# ZMK Module Template

This repository contains a template for a ZMK module, as it would most frequently be used. 

## Usage

Edit your west.yml file found in your zmk-config's config directory to add the ghosty62 module. Example:

```
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: MesrineNathanael
      url-base: https://github.com/MesrineNathanael
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: zmk-keyboards-ghosty62
      remote: MesrineNathanael
      revision: main
  self:
    path: config
```

and include in the build.yml:
```
include:
  - board: nice_nano_v2
    shield: ghosty62_left
  - board: nice_nano_v2
    shield: ghosty62_right
```
Once you have the module added to your west.yml you can then build firmware as if it was in your config's shield directory or in ZMK main.

## More Info

For more info on modules, you can read through  through the [Zephyr modules page](https://docs.zephyrproject.org/3.5.0/develop/modules.html) and [ZMK's page on using modules](https://zmk.dev/docs/features/modules). [Zephyr's west manifest page](https://docs.zephyrproject.org/3.5.0/develop/west/manifest.html#west-manifests) may also be of use.
