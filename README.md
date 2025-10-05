1) Core do ESP32 (versão exigida)

Arduino IDE aberto

Vá em Tools → Board → Boards Manager…

Pesquise esp32 (Espressif Systems)

No dropdown de versão, selecione 2.0.14 → Install

Depois selecione a placa em Tools → Board → ESP32 → ESP32S3 Dev Module.

2) Bibliotecas necessárias (versões fixas)

Instale via Sketch → Include Library → Manage Libraries…:

WiFiManager — autor tzapu — versão 0.16.0

lvgl — autor kisvegabor — versão 8.3.11

LovyanGFX — versão 1.2.7

Dica: escolha a versão exata no dropdown da Library Manager.

3) Copiar configuração do LVGL

Copie seu arquivo de config do projeto para o local que o Arduino encontra por padrão:

Origem: PixPayApp/lv_conf.h

Destino (Windows):
C:\Users\<SEU_USUARIO>\Documents\Arduino\libraries\lv_conf.h

macOS: ~/Documents/Arduino/libraries/lv_conf.h

Linux: ~/Arduino/libraries/lv_conf.h ou ~/Documents/Arduino/libraries/lv_conf.h

Se a pasta libraries não existir, crie. Se já existir um lv_conf.h, substitua pelo seu.

4) (Opcional) Ambiente via Docker

Se você usa o workspace com IDE web:

cd esp32-7inch-display
docker-compose up esp32-web-ide
# ou, em versões novas do Docker:
docker compose up esp32-web-ide

5) Ajustes comuns de Tools (ESP32-S3 + display 7" RGB)

CPU Frequency: 240 MHz

PSRAM: OPI PSRAM / Enabled (se disponível na sua placa)

Flash Mode: QIO (80 MHz)

Partition Scheme: “Default 4MB with spiffs (1.2MB APP/1.5MB SPIFFS)” (ou o que seu projeto exigir)

Essas opções podem variar por placa, mas acima é o mais comum para o ESP32-8048S070 (Sunton) 7", 800×480 RGB.

6) Compilar e enviar

Conecte a placa, escolha a porta em Tools → Port

Sketch → Verify/Compile

Sketch → Upload

Notas rápidas

O display de 7" Sunton (ESP32-8048S070) é RGB 800×480; mantenha a config do LovyanGFX 1.2.7 para esse painel (pinos, porches, etc.) como no seu código.

O lv_conf.h controla coisas como LV_COLOR_DEPTH, LV_TICK_CUSTOM, cache de fontes, etc. Garanta que está compatível com 800×480 e sua integração com LovyanGFX.

Fixar as versões (Core 2.0.14, LVGL 8.3.11, LovyanGFX 1.2.7, WiFiManager 0.16.0) evita incompatibilidades.
