# Убираем верхнюю панель в Alacritty

Ставим `xdotool`

Сохраняем следующий скрипт
```sh
#!/bin/bash
# Скрипт для скрытия верхней панели для текущего окна Alacritty

# Получаем идентификатор текущего окна
window_id=$(xdotool getactivewindow)

# Проверяем, что идентификатор окна не пустой
if [ -n "$window_id" ]; then
  # Применяем скрытие верхней панели для текущего окна
  xprop -id "$window_id" -f _MOTIF_WM_HINTS 32c -set _MOTIF_WM_HINTS "0x2, 0x0, 0x2, 0x0, 0x0"
fi
```


Добавляем в .bashrc |  .zshrc
`source /путь до скрипта/hide_panel.sh`
