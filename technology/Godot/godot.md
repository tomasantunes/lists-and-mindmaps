# Godot Engine Development Links
http://docs.godotengine.org/en/3.0/development/cpp/index.html

http://docs.godotengine.org/en/3.0/development/compiling/index.html

http://docs.godotengine.org/en/3.0/development/file_formats/tscn.html

http://docs.godotengine.org/en/3.0/classes/index.html

# How to update fork

- Verify the remote branch attached for fetch and push operation using following command: git remote -v
- Specify a remote upstream repo to sync with your fork git remote add upstream https://github.com/OriginalRepo/OriginalProject.git
- Verify using git remote -v
- Fetch branches and commits from the upstream repo. You’ll be storing the commits to master in a local branch upstream/master using following command: git fetch upstream
- Checkout your fork’s local master using following command: git checkout master
- Merge changes from upstream/master into it git merge upstream/master
- Push changes to update your fork master on Github: git push origin master

# Godot GUI

enum SizeFlags

- SIZE_FILL = 1 — Tells the parent Container to expand the bounds of this node to fill all the available space without pushing any other node. Use with size_flags_horizontal and size_flags_vertical.
- SIZE_EXPAND = 2 — Tells the parent Container to let this node take all the available space on the axis you flag. If multiple neighboring nodes are set to expand, they’ll share the space based on their stretch ratio. See size_flags_stretch_ratio. Use with size_flags_horizontal and size_flags_vertical.
- SIZE_EXPAND_FILL = 3 — Sets the node’s size flags to both fill and expand. See the 2 constants above for more information.
- SIZE_SHRINK_CENTER = 4 — Tells the parent Container to center the node in itself. It centers the Control based on its bounding box, so it doesn’t work with the fill or expand size flags. Use with size_flags_horizontal and size_flags_vertical.
- SIZE_SHRINK_END = 8 — Tells the parent Container to align the node with its end, either the bottom or the right edge. It doesn’t work with the fill or expand size flags. Use with size_flags_horizontal and size_flags_vertical.

**Set minimum size:**
```
control->set_custom_minimum_size(Size2(300, 0) * EDSCALE);
```
**How to change GUI theme color:**

Go to Editor -> Editor Settings -> Theme and select a base color.

# Export to HTML5 on Ubuntu
1. Install emscripten by following [these instructions](https://kripken.github.io/emscripten-site/docs/getting_started/downloads.html#sdk-download-and-install)

3. Build the export template on the Godot source directory
```
scons platform=javascript tools=no target=release
```

# Godot Ubuntu Desktop File

1 Create Godot.desktop file at /usr/share/applications

```
[Desktop Entry]
Type=Application
Name=Godot Engine
GenericName=Game engine
Comment=2D and 3D game engine
Exec=/home/user1/Documents/Godot-executable/Godot_v3.0.6-stable_x11.64
Icon=/home/user1/Documents/Godot-executable/icon.png
```

# Godot 4.0 changes

- Texture repeat flag is no longer in the import settings.
- To export variables you need to use annotations combined with typing:
```
@export
var velocity: float
```
- Stretch Mode "2d" is now called "canvas_items"
