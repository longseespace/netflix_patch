# Netflix HD Patch APK

Patched Netflix App for Android enabling Widevine L1 allowing not certified devices to play HD

## Prerequisites

- apktool v2.4.0

## Step by step guide:

- Clone this repo
- Download [Netflix 4.12.2](https://www.apkmirror.com/apk/netflix-inc/netflix/netflix-4-12-2-build-14444-release/), rename to `netflix.apk`
- Open `Terminal.app` and run the following

```bash
# decompile
apktool d -r -f netflix.apk

# apply the patch
patch -p0 -i ./netflix.patch

# recompile
apktool b -f netflix

# sign
./signapk.sh netflix/dist/netflix.apk mimi.keystore password mimi
```

- Install `signed_netflix.apk` and enjoy Netflix HD
