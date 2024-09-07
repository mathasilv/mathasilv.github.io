Aqui está um exemplo de um arquivo `README.md` que você pode usar para o projeto:

```markdown
# Projeto de Monitoramento de Satélites com ESP32 e Display OLED

Este projeto utiliza um ESP32 conectado a um módulo GPS e um display OLED para monitorar satélites em tempo real usando dados TLE (Two-Line Element). O sistema também permite a navegação entre diferentes satélites e opções de menu por meio de botões.

## Funcionalidades

- **Monitoramento de Satélites:** Utiliza a biblioteca `Sgp4` para calcular e exibir a posição dos satélites com base em seus dados TLE.
- **Leitura de GPS:** A biblioteca `TinyGPS++` é usada para processar os dados de localização obtidos por um módulo GPS.
- **Interface OLED:** A interface gráfica é exibida em um display OLED de 128x64 pixels, controlado pela biblioteca `Adafruit_SSD1306`.
- **Navegação por Botões:** O sistema utiliza três botões para navegar entre menus e selecionar opções:
  - **Botão Próximo (GPIO 25):** Navega para o próximo item do menu.
  - **Botão Anterior (GPIO 26):** Navega para o item anterior do menu.
  - **Botão Selecionar (GPIO 27):** Confirma a seleção de um item no menu.
- **Atualização Automática:** O projeto utiliza um `Ticker` para realizar atualizações de dados temporizadas.

## Hardware Utilizado

- **ESP32**: Controlador principal do sistema.
- **Módulo GPS**: Para receber dados de localização.
- **Display OLED 128x64**: Para exibir as informações do satélite e GPS.
- **Botões**: Três botões conectados aos GPIOs 25, 26 e 27 para interação com o sistema.
- **Cabos e Conectores**: Para fazer a ligação entre o hardware.

## Estrutura de Dados

O projeto utiliza uma estrutura chamada `SatelliteData` para armazenar as informações de TLE dos satélites:
```cpp
struct SatelliteData {
    char name[20];
    char tle_line1[70];
    char tle_line2[70];
};
```

## Instalação e Configuração

1. **Bibliotecas Necessárias:**
   - [TinyGPS++](https://github.com/mikalhart/TinyGPSPlus)
   - [Sgp4](https://github.com/dnwrnr/sat)
   - [Adafruit GFX](https://github.com/adafruit/Adafruit-GFX-Library)
   - [Adafruit SSD1306](https://github.com/adafruit/Adafruit_SSD1306)

2. **Montagem de Hardware:**
   - Conecte o módulo GPS ao ESP32 nos pinos corretos.
   - Conecte o display OLED conforme as especificações I2C.
   - Conecte os botões aos GPIOs 25, 26 e 27.

3. **Compilação e Upload:**
   - Use o Arduino IDE ou PlatformIO para compilar o código e fazer o upload para o ESP32.

## Como Usar

1. Ligue o dispositivo e aguarde até que os dados GPS sejam adquiridos.
2. Use os botões para navegar pelos menus e selecionar o satélite que deseja monitorar.
3. O display OLED exibirá as informações do satélite selecionado, como sua órbita e posição atual.

## Licença

Este projeto está licenciado sob a [MIT License](https://opensource.org/licenses/MIT).
```

Esse arquivo `README.md` fornece uma visão geral do projeto, explicando as funcionalidades, os componentes utilizados, e como configurar o sistema. Pode ser personalizado conforme você adicionar mais funcionalidades.