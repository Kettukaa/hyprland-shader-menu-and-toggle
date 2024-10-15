
# Hyprland Shader Menu & Toggle
This is my shoddy attempt at managing shaders in hyprland. It's not pretty, but it does the job I need and fixes some short comings of hyprshade's CLI.

Please review the scripts before running them on your system.

![](assets/output.gif)

# Requirements
This requires rofi and hyprshade to work.

# Install

1. Move all scripts to `/usr/local/bin`
```bash
sudo cp dim_filter /usr/local/bin/.
sudo cp shader_search /usr/local/bin/.
sudo cp toggle_shader /usr/local/bin/.
```

2. Make all of them executable 
```bash
chmod +x /usr/local/bin/dim_filter
chmod +x /usr/local/bin/shader_search
chmod +x /usr/local/bin/toggle_shader
```

3. Fill `~/.config/hypr/shaders/` with your personal shaders 

4. Add your binds
```bash
# toggle the current shader off and on
bind = SUPER SHIFT, S, exec, /usr/local/bin/toggle_shader

# open up shader search dialog
bind = SUPER, S, exec, /usr/local/bin/shader_search

# toggle shaders properly for screenshots - sort of
bind = SUPER SHIFT, 107, exec, /usr/local/bin/toggle_shader off; grimblast --freeze copysave area ~/Pictures/screenshots/$(date +%Y-%m-%d_%H-%M-%S).png; /usr/local/bin/toggle_shader
```
