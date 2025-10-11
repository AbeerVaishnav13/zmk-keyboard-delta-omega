# Delta Omega ZMK Module

This repository contains the shield files for the [delta omega](https://github.com/unspecworks/delta-omega) to allow users to build firmware. This can be done by adding the module to the west.yml found in your zmk-config's config directory. There is a full guide available for this here: [ZMK Modules Doc](https://zmk.dev/docs/features/modules)

### Usage

1. Add the delta omega module and zmk-rgbled-widget to your `config/west.yml`

```yaml
manifest:
  defaults:
    revision: v0.3
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: caksoylar
      url-base: https://github.com/caksoylar
    - name: unspecworks
      url-base: https://github.com/unspecworks
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: zmk-rgbled-widget
      remote: caksoylar
      revision: main
    - name: zmk-keyboard-delta-omega
      remote: unspecworks
      revision: main
  self:
    path: config
```

2. (Optional) If you want use the LED Indicator. add configs to `config/delta_omega.conf`.

```cpp
CONFIG_NFCT_PINS_AS_GPIOS=y
CONFIG_RGBLED_WIDGET=y
```
