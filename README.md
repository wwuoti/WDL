# Reaper on Wayland

This repo contains a forked version of SWELL with modifications for providing experimental Wayland support.

**NOTE: this work is considered not ready for daily use!**

See this [blog post](https://wuoti.com/blog/reaper-wayland) for more info.

## Build

```
cd WDL/WDL/swell
make DEBUG=1
```

After this, you have a `libSwell.so` library file in the current directory. Let's symlink it to Reaper so that is uses the newly built one instead of the default library it ships with:

```
cd <path_to_reaper>
mv libSwell.so libsSwell.so.bak
ln -s <path_to_WDL_repo>/WDL/swell/libSwell.so libSwell.so
```

Last, run Reaper with:

```
GDK_BACKEND=wayland reaper
```
