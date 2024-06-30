# Relógio NTP com ESP8266

Este projeto consiste em um relógio NTP baseado em ESP8266 que sincroniza o tempo de um servidor NTP e o exibe em uma matriz LED 8x32 usando o driver MAX7219.

## Funcionalidades

- Sincronização automática de tempo via NTP (Protocolo de Tempo de Rede)
- Ajuste configurável do UTC para ajuste do fuso horário local
- Suporte para formatos de hora de 24 horas e 12 horas
- Ajuste dinâmico da intensidade com base no horário do dia

## Instalação e Configuração

### Requisitos de Hardware

- Placa ESP8266 (por exemplo, NodeMCU 1.0)
- Matriz LED MAX7219 8x32
- Fonte de alimentação para ESP8266 e Matriz LED

### Requisitos de Software

- Arduino IDE (ou IDE compatível)
- Bibliotecas necessárias:
  - ESP8266WiFi
  - DNSServer
  - ESP8266WebServer
  - WiFiManager
  - ArduinoJson
  - EEPROM
  - NTPClient
  - WiFiUdp

### Passos de Instalação

1. Clone ou baixe o repositório de [ESP8266-8x32-Matrix-clock](https://github.com/K1WIZ/ESP8266-8x32-Matrix-clock).
2. Abra o projeto na Arduino IDE.
3. Instale as bibliotecas necessárias listadas acima usando o Gerenciador de Bibliotecas na Arduino IDE.
4. Conecte sua placa ESP8266 e a Matriz LED MAX7219 conforme a configuração de pinos especificada no código (`DIN_PIN`, `CS_PIN`, `CLK_PIN`).
5. Compile e envie o sketch para sua placa ESP8266.

### Configuração

- Na primeira inicialização, o relógio criará um ponto de acesso WiFi chamado "NTP Clock Setup". Conecte-se a este ponto de acesso usando um dispositivo com um navegador da web.
- Abra um navegador da web e acesse `http://192.168.4.1`. Isso abrirá o portal de configuração do WiFiManager.
- Configure suas configurações de WiFi e opcionalmente defina o offset UTC e a preferência de formato de hora (24 horas ou 12 horas).
- Salve a configuração e o relógio se conectará à rede WiFi configurada e sincronizará automaticamente o tempo.

## Uso

Depois que o relógio estiver configurado e conectado ao WiFi:

- Ele sincronizará automaticamente o tempo a partir do servidor NTP configurado (`pool.ntp.org` por padrão).
- O tempo será exibido na matriz LED com ajustes dinâmicos de intensidade com base no horário do dia.
- O relógio suporta exibição de texto rolante para mensagens ou informações adicionais.
