# Kitty Icons

Default [Kitty] icon (https://sw.kovidgoyal.net/kitty/) is ugly. Let's make it worst!

## How to install

Taken from [I do not like the kitty icon!](https://sw.kovidgoyal.net/kitty/faq/#i-do-not-like-the-kitty-icon) FAQ:

On macOS you can put `kitty.app.icns` or `kitty.app.png` in the [kitty configuration directory](https://sw.kovidgoyal.net/kitty/conf/#confloc), and this icon will be applied automatically at startup. Unfortunately, Apple’s Dock does not change its cached icon so the custom icon will revert when kitty is quit. Run the following to force the Dock to update its cached icons:

```sh
rm /var/folders/*/*/*/com.apple.dock.iconcache; killall Dock
```

If you prefer not to keep a custom icon in the kitty config folder, you can also set it with the following command:

```sh
# Set kitty.icns as the icon for currently running kitty
kitty +runpy 'from kitty.fast_data_types import cocoa_set_app_icon; import sys; cocoa_set_app_icon(*sys.argv[1:]); print("OK")' kitty.icns

# Set the icon for app bundle specified by the path
kitty +runpy 'from kitty.fast_data_types import cocoa_set_app_icon; import sys; cocoa_set_app_icon(*sys.argv[1:]); print("OK")' /path/to/icon.png /Applications/kitty.app
```

You can also change the icon manually by following the steps:

1. Find `kitty.app` in the Applications folder, select it and press `⌘+I`
2. Drag `kitty.icns` onto the application icon in the kitty info pane
3. Delete the icon cache and restart Dock:

```sh
rm /var/folders/*/*/*/com.apple.dock.iconcache; killall Dock
```

