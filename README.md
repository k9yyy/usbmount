# USBmount

USBmount for Alpine.

For more detailed documentation regarding to USBmount itself, please refer to the original repo: <https://github.com/rbrito/usbmount>

## Build the package

To build this package, here are some simple steps.

Install necessary build tools:

```
sudo apk add abuild gcc
```

Note: Looks like abuild does not run properly if GCC is not installed.

Add user to `abuild` group:

```
sudo addgroup $USER abuild
```

Generate a key pair:

```
abuild-keygen -a -i
```

- **`-a`** Set `PACKAGER_PRIVKEY=<generated key>` in `abuild.conf`
- **`-i`** Install public key into `/etc/apk/keys` using `sudo`

If you just want to build the package, you can simply do:

```
abuild -r
```

and if there are no errors, the built package should be located at `~/packages/test/<arch>/usbmount-#.#.#-r#.apk`.

For more advanced use, please refer to: <https://wiki.alpinelinux.org/wiki/Abuild_and_Helpers>.

## Instal the package

To install the built package, simply do:

```
apk add usbmount-#.#.#-r#.apk
```

Dependencies should be installed automatically.

## Start udev-trigger

USBmount  relies on  udev-trigger to work.

You can start the service by issuing:

```
rc-service udev-trigger start
```

and make it auto start:

```
rc-update add udev-trigger
```

