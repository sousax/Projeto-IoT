# Projeto de IoT: Estufa Inteligente com ESP32 e ThingSpeak

![Estufa Inteligente](https://img.shields.io/badge/IoT-Estufa%20Inteligente-green)
![Platform](https://img.shields.io/badge/Plataforma-Wokwi-purple)
![Microcontroller](https://img.shields.io/badge/MCU-ESP32-orange)

## 📖 Descrição do Projeto

Este projeto consiste em um sistema de Internet das Coisas (IoT) para o monitoramento remoto de temperatura e umidade de um ambiente de cultivo indoor (estufa). Utilizando um microcontrolador ESP32 e um sensor DHT22, o sistema coleta dados vitais para a saúde das plantas e os envia em tempo real para a plataforma de nuvem ThingSpeak, onde podem ser visualizados através de gráficos públicos.

---

## 🎯 Contexto do Problema

O cultivo de plantas em ambientes fechados (indoor) tem se popularizado, seja para hortaliças em apartamentos ou para espécies que exigem condições climáticas controladas. O sucesso desse cultivo depende diretamente de um ambiente estável. Variações bruscas de temperatura e umidade podem estressar as plantas, atrasar seu crescimento, e até mesmo favorecer o surgimento de pragas e doenças, como fungos. Monitorar essas variáveis manualmente é ineficiente e propenso a falhas. Portanto, a automação desse monitoramento via IoT é fundamental para garantir as condições ideais de forma contínua, otimizando a saúde das plantas e o uso de recursos como água e energia.

---

## 🛠️ Tecnologias Utilizadas

* **Microcontrolador:** ESP32
* **Sensor:** DHT22 (Temperatura e Umidade)
* **Plataforma de Simulação:** Wokwi Simulator
* **Plataforma de Nuvem (IoT):** ThingSpeak
* **Linguagem de Programação:** C++ (Arduino Framework)
* **Bibliotecas:** `WiFi.h`, `ThingSpeak.h`, `DHT.h`
* **Documentação e Versionamento:** Git e GitHub

---

## ⚙️ Explicação de Funcionamento

O sistema opera da seguinte forma:
1.  **Leitura dos Sensores:** O ESP32, através do pino GPIO 15, realiza a leitura dos dados de temperatura (em Celsius) e umidade relativa do ar (%) a partir do sensor DHT22.
2.  **Conexão Wi-Fi:** O microcontrolador se conecta à rede Wi-Fi configurada (no caso da simulação, a rede `Wokwi-GUEST`).
3.  **Envio para a Nuvem:** A cada 20 segundos, o ESP32 envia os valores lidos para um canal público no ThingSpeak, utilizando a biblioteca oficial `ThingSpeak.h` e a API de escrita do canal.
4.  **Visualização dos Dados:** Os dados são armazenados e exibidos em tempo real no canal do ThingSpeak, através de dois gráficos (um para temperatura e outro para umidade), que podem ser acessados publicamente por qualquer navegador.

---

## 📸 Capturas de Tela e Links

Aqui estão os principais componentes do projeto em funcionamento.

**Circuito no Wokwi:**
*(Tire um print do seu circuito no Wokwi e adicione aqui)*
![Circuito no Wokwi](./img/wokwi_circuito.png)

**Gráficos no ThingSpeak:**
*(Tire um print dos seus gráficos no ThingSpeak mostrando os dados e adicione aqui)*
![Gráficos no ThingSpeak](./img/thingspeak_grafico.png)

---

## 🚀 Como Replicar o Projeto

Você pode acessar e replicar este projeto seguindo os links abaixo:

* **Link para o Projeto no Wokwi:**
    `[COLE AQUI O LINK PÚBLICO DO SEU PROJETO WOKWI]`

* **Link para o Canal no ThingSpeak:**
    `[COLE AQUI O LINK PÚBLICO DO SEU CANAL THINGSPEAK]`

**Instruções:**
1.  Abra o projeto no Wokwi.
2.  No arquivo `sketch.ino`, insira o ID do seu próprio canal ThingSpeak e sua Chave de API de Escrita (Write API Key) nas variáveis `myChannelNumber` e `myWriteAPIKey`.
3.  Inicie a simulação. Os dados começarão a ser enviados para o seu canal.
4.  Para simular diferentes condições, clique no sensor DHT22 no Wokwi e altere os valores de temperatura e umidade.

---

## 📂 Código-Fonte

O código-fonte completo e comentado está localizado no diretório `/src` deste repositório.

[Link para o código-fonte](./src/sketch.ino)
