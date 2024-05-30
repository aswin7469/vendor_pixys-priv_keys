# vendor_pixys-priv_keys

A cool template to sign PixysOS v7.2.x > builds with `dev-keys`.

## Usage

1. Clone this repo into `vendor/pixys-priv/keys`.
2. Edit `gen_keys` script to reflect your data.
3. Run it:

```bash
./gen_keys
```

It will generate the certificates and keys used on `~/.android-certs/`.

It will also generate the makefiles basing on the keys defined on `_data/` folder.

Backup **AT ALL COSTS** your `~/.android-certs/` dir **AND NEVER LEAK THOSE**. Losing these keys could prevent you from updating your PixysOS builds with the same keys, so formatting data would be required. Leakage of these keys can compromise the security and authenticity of your builds, requiring a new pair of keys to be generated.
