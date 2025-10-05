ESP32-S3 with 7-inch RGB display
Version of esp required:
Tools → Board → Boards Manager
Then click dropdown → Select 2.0.14 → Install



Required Libraries
WiFiManager by tzapu (version 0.16.0)cd esp32-7inch-display
lvgl by kisvegabor (version 8.3.11)docker-compose up esp32-web-ide
LVGL Configuration```

Copy `PixPayApp/lv_conf.h` to `Documents/Arduino/libraries/lv_conf.h`
