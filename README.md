# vendor_pixys-priv_keys

A cool template to sign PixysOS v7.2.x > builds with `dev-keys`.

## Usage

1. Clone this repo into `vendor/pixys-priv/keys`.
2. Edit `gen_keys` script to reflect your data.
3. Run it:

```bash
./gen_keys
```

It will generate the certificates and makefiles on `vendor/security/pixys/`. basing on the keys defined on `_data/` folder.

4. Inherit the makefile from your device.mk

```makefile
$(call inherit-product, vendor/security/pixys/keys.mk)
```

5. That's it , just compile your build normally and it will be signed with the keys you just made

Backup **AT ALL COSTS** your `vendor/security/pixys/` dir **AND NEVER LEAK THOSE**. Losing these keys could prevent you from updating your PixysOS builds with the same keys, so formatting data would be required. Leakage of these keys can compromise the security and authenticity of your builds, requiring a new pair of keys to be generated.

## Optional cool stuffs

This script also generates the avb_custom_key.img if you are opting for full avb signing and Locking bootloader

The pixysos_pubkey can be used for verification of the build using [LineageOS/update_verifier](https://github.com/LineageOS/update_verifier)
