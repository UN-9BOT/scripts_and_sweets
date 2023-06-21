# Убираем постоянно работающие вентиляторы

- Host: Modern 14 B4MW
- Kernel: 6.3.8-arch1-1
- CPU: AMD Ryzen 5 4500U with Radeon Graphics (6) @ 2.375GHz

Ставим 'yay isw'
Меняем конфиг 'sudoedit /etc/isw.conf'
```sh
[14DKEMS1]
# B4MW
# 14DKEMS1.105
address_profile = MSI_ADDRESS_DEFAULT
fan_mode = 140
battery_charging_threshold = 100
# CPU
cpu_temp_0 = 62
cpu_temp_1 = 68
cpu_temp_2 = 72
cpu_temp_3 = 77
cpu_temp_4 = 80
cpu_temp_5 = 90
cpu_fan_speed_0 = 0
cpu_fan_speed_1 = 50
cpu_fan_speed_2 = 65
cpu_fan_speed_3 = 73
cpu_fan_speed_4 = 80
cpu_fan_speed_5 = 90
cpu_fan_speed_6 = 100
# GPU
gpu_temp_0 = 62
gpu_temp_1 = 68
gpu_temp_2 = 72
gpu_temp_3 = 77
gpu_temp_4 = 80
gpu_temp_5 = 90
gpu_fan_speed_0 = 45
gpu_fan_speed_1 = 50
gpu_fan_speed_2 = 65
gpu_fan_speed_3 = 72
gpu_fan_speed_4 = 80
gpu_fan_speed_5 = 85
gpu_fan_speed_6 = 100
```


ПЕРЕЗАГРУЖАЕМСЯ!

можем запускать ручками чтобы проверить что работает - 'sudo isw -w 14DKEMS1'

Для добавления в автозагрузку:

создаем sh файл:
'nano .isw.sh'

добавляем:

```sh
#!/usr/bin/env bash
sudo isw -w 14DKEMS1
```

Добавляем демона
`sudoedit /etc/systemd/system/isw.service`

```sh
[Unit]
Description=Custom Service

[Service]
ExecStart=/home/un9bot/.config/script/isw.sh

[Install]
WantedBy=default.target
```

Включаем его:
`sudo systemctl daemon-reload`
`sudo systemctl enable isw.service`
`sudo systemctl start isw.service`



