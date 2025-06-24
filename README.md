# Projeto de IoT: Sistema Inteligente de Alerta de Alagamento

![Flood Alert](https://img.shields.io/badge/IoT-Alerta%20de%20Alagamento-blue)
![Platform](https://img.shields.io/badge/Plataforma-Wokwi-purple)
![Microcontroller](https://img.shields.io/badge/MCU-ESP32-orange)

## 📖 Descrição do Projeto

Este projeto é um sistema de Internet das Coisas (IoT) projetado para fornecer alertas prévios sobre riscos de alagamento. Utilizando um microcontrolador ESP32 e um sensor ultrassônico HC-SR04, o sistema monitora o nível da água em pontos estratégicos e envia os dados em tempo real para a plataforma de nuvem ThingSpeak, permitindo a visualização remota e a criação de um histórico para análises preventivas.

---

## 🎯 Contexto do Problema

Alagamentos em áreas urbanas são eventos cada vez mais frequentes e devastadores, causando prejuízos materiais e riscos à vida. A falta de um alerta prévio impede que moradores e a defesa civil tomem ações preventivas. Este projeto propõe um sistema de monitoramento de baixo custo que mede o nível da água em tempo real, fornecendo dados cruciais para um sistema de alerta precoce. A automação desse monitoramento via IoT é uma ferramenta poderosa para criar uma resposta rápida e organizada da comunidade frente a um risco iminente.

---

## 🛠️ Tecnologias Utilizadas

* **Microcontrolador:** ESP32
* **Sensor:** HC-SR04 (Sensor Ultrassônico de Distância)
* **Plataforma de Simulação:** Wokwi Simulator
* **Plataforma de Nuvem (IoT):** ThingSpeak
* **Linguagem de Programação:** C++ (Arduino Framework)
* **Bibliotecas:** `WiFi.h`, `ThingSpeak.h`

---

## ⚙️ Explicação de Funcionamento

O sistema opera da seguinte forma:
1.  **Instalação Virtual:** O sensor HC-SR04 é posicionado virtualmente acima do ponto a ser medido. A constante `DISTANCIA_CHAO_SECO_CM` no código representa a distância do sensor ao chão quando não há água.
2.  **Medição:** O sensor emite um pulso ultrassônico e mede o tempo que ele leva para retornar. Com base nesse tempo, o ESP32 calcula a distância até a superfície (que pode ser o chão ou a água).
3.  **Cálculo de Nível:** O código converte a distância medida em um percentual de nível de água. Por exemplo, se a distância medida diminui, significa que o nível da água está subindo, e o percentual aumenta.
4.  **Envio para a Nuvem:** A cada 20 segundos, o ESP32 envia os dados de "Distância (cm)" e "Nível da Água (%)" para um canal público no ThingSpeak.
5.  **Visualização:** Os dados são exibidos em tempo real em gráficos no ThingSpeak, permitindo o acompanhamento remoto do risco de alagamento.

---

## 📸 Capturas de Tela e Links

* **Circuito no Wokwi:**
*(Tire um print do seu circuito no Wokwi e adicione aqui)*
![Circuito no Wokwi]![image](https://github.com/user-attachments/assets/7a671c6e-54ad-4956-81ed-0004bfc54ec8)


* **Gráficos no ThingSpeak:**
*(Tire um print dos seus gráficos no ThingSpeak e adicione aqui)*
![Gráficos no ThingSpeak]![image](https://github.com/user-attachments/assets/9492c66e-4da9-49af-a61e-938fd934cd51)


---

## 🚀 Como Replicar o Projeto

* **Link para o Projeto no Wokwi:**
    !`(https://wokwi.com/projects/434651680429040641)`

* **Link para o Canal no ThingSpeak:**
    !`(https://thingspeak.mathworks.com/channels/2996766)`

**Instruções:**
1.  Abra o projeto no Wokwi.
2.  No arquivo `sketch.ino`, insira o ID do seu próprio canal ThingSpeak e sua Chave de API de Escrita.
3.  Ajuste a variável `DISTANCIA_CHAO_SECO_CM` se desejar simular uma altura de instalação diferente.
4.  Inicie a simulação. Clique no sensor HC-SR04 e arraste o controle deslizante para simular a subida e descida do nível da água.

---

## 💡 Melhorias Futuras (Não implementadas)
Este projeto pode ser expandido com as seguintes funcionalidades em uma versão física:
* **Alertas Ativos:** Integração com Telegram, MQTT ou e-mail para enviar notificações automáticas.
* **Autonomia Energética:** Uso de painel solar e bateria para instalação em locais remotos.
* **Comunicação Robusta:** Uso de LoRaWAN para áreas sem cobertura Wi-Fi.
