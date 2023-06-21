# Различные шорткаты которые можно забиндить

## Albert

`albert toggle`   -> Super

## UN/HIDE TOP PANE

HIDE
```xprop -f _MOTIF_WM_HINTS 32c -set _MOTIF_WM_HINTS "0x2, 0x0, 0x2, 0x0, 0x0"```
-> CTRL+SUPER+9
UNHIDE
```xprop -f _MOTIF_WM_HINTS 32c -set _MOTIF_WM_HINTS "0x2, 0x0, 0x1, 0x0, 0x0"```
-> CTRL+SUPER+0

## Alacritty + Ranger

`zsh -c "source ~/.zshrc && alacritty --command=ranger"`
-> SUPER+E
