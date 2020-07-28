# Netflix HD Patch APK

Patched Netflix App for Android enabling Widevine L1 allowing not certified devices to play HD

## Prerequisites

- apktool v2.4.1

## Step by step guide:

- Clone this repo
- Download [Netflix 4.16.3](https://www.apkmirror.com/apk/netflix-inc/netflix/netflix-4-16-3-build-15172-release/), rename to `netflix.apk`
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

## Notes:

- To generate patch file, run this

```bash
diff -ruN orig/ new/ > file.patch
# -r == recursive, so do subdirectories
# -u == unified style, if your system lacks it or if recipient
#       may not have it, use "-c"
# -N == treat absent files as empty
```
