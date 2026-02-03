# My collection of curious wallpapers

This collection is managed by [schenesort](https://github.com/sthysel/schenesort) a tool I made to sort scenes.
schenesort uses a classifying vision model (llava) to look at a scene and suggest a filename that makes more sense than
the names I had.

## hyprland using waypaper

The file directly
```
hyprctl hyprpaper wallpaper "eDP-1, ship_at_sea_during_sunset.png"
```

Asking schenesort to get something fruity from the collection
```
hyprctl hyprpaper wallpaper "eDP-1,$(schenesort get --tag banana-1 -p)"
```

## i3 using feh

```
exec_always --no-startup-id feh --bg-scale ~/.wallpaper/
```
# schenesort cheat sheet

```bash
# Build/update the index
schenesort index ./collection
schenesort index ./collection --rebuild   # rebuild from scratch
schenesort index ./collection
 --prune     # remove deleted files

# Query collection

schenesort get --tag cyberpunk
schenesort get --mood peaceful --style photography
schenesort get --screen 4K --subject landscape
schenesort get --color blue --time sunset
schenesort get --min-width 3840
schenesort get -q "mountain"              # text search

# Random selection
schenesort get --random -n 10             # 10 random collection

schenesort get -1                         # single random wallpaper
schenesort get -1 --mood dramatic         # random with filter

# Browse results in TUI
schenesort get --mood peaceful --browse   # open matches in browser
schenesort get --style photography -b     # short form

# For scripting (paths only)
schenesort get -1 -p                      # just the path
feh $(schenesort get -1 -p)               # set random wallpaper
hyprctl hyprpaper wallpaper "eDP-1,$(schenesort get -1 -p)"

# View collection stats
schenesort stats
```

# Imaginary Property

Since I got these mostly from the high seas, I claim salvage. If you see an image that is yours and of limited use, tell
me and I will remove it from this repo.
