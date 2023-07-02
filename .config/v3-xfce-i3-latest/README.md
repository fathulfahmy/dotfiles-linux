# How to XFCE with i3WM
### Download
1. Download XFCE Distribution
2. Download `i3` only (`i3 status` `i3 lock` `dmenu` is not needed)

> :warning: Do not install preconfigured or distributed i3wm to avoid conflicts with XFCE settings  
> e.g.  
> **do** `sudo dnf install i3 --setopt=install_weak_deps=False`   
> **dont** `"i3 desktop"` or `@i3-desktop-environment`  

### Add i3WM Startup
3. Open `Session and Startup`
4. Select `Application Autostart`
5. Add
```
Name: i3
Description: Window Manager
Command: i3
Trigger: On login  
```

```
Name: xfsettingsd
Description: Xfwm Theme Workaround
Command: xfsettingsd --replace
Trigger: On login
```

### Disable XFCE Application Startup
6. Edit `Current Session`
```
Program: xfdesktop
Restart Style: Never
```

```
Program: xfwm4
Restart Style: Never
```
7. Restart

### Post configuration
8. Remove all XFCE keyboard shortcuts through XFCE `Keyboard`
9. Change theme through XFCE `Appearance`
10. Install `lightdm-gtk-greeter-settings` to change login screen theme
11. Change wallpaper through XFCE `Desktop`
12. Bind Print Screen button to `xfce4-screenshooter` ([.config/i3/config](https://github.com/fathulfahmy/dotfiles-linux/blob/main/.config/v3-xfce-i3-latest/i3/config))
13. Install `picom` if you are experiencing screen tearing ([.config/picom.conf](https://github.com/fathulfahmy/dotfiles-linux/blob/main/.config/v3-xfce-i3-latest/picom.conf))

### Reference
- https://forum.endeavouros.com/t/tutorial-easy-setup-endeavour-xfce-i3-tiling-window-manager/13171
- https://www.youtube.com/watch?v=nZTBxJ_gr8w
