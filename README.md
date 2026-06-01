# Controle de Servo Motor e Display OLED com ESP32

Este é um projeto de sistemas embarcados desenvolvido em MicroPython para praticar o controle de atuadores (Servo Motor PWM), saídas visuais (Display OLED I2C e LEDs) e leitura de botões com resistores internos de *pull-up*.

![Interface do Projeto](https://github.com/joaotorresdev/SERVO-ESP32/blob/main/print%20servo.png)

## 🚀 Sobre o Projeto

O projeto consiste num sistema interativo simulado no Wokwi onde o utilizador controla a rotação de um servo motor e o estado de LEDs através de dois botões de pressão. O estado atual da ação ("Luz acesa" ou "luz apagada") é exibido em tempo real num display OLED SSD1306, servindo como um protótipo de automação ou controlo de acesso.

## 🛠️ Tecnologias Utilizadas

* MicroPython
* Placa de Desenvolvimento ESP32
* Display OLED SSD1306 (I2C)
* Micro Servo Motor (PWM)

## 💻 Como Funciona o Código

O fluxo do programa roda dentro de um laço infinito (`while True`) que monitoriza constantemente as entradas digitais, estando dividido em três etapas principais:

1. **Inicialização de Periféricos:** Configura os pinos dos LEDs como saída, os botões como entrada com *pull-up* ativado, inicializa a comunicação I2C para o display e define a frequência de 50Hz no pino PWM do servo.
2. **Ação do Botão Azul (Opção 1):** Ao pressionar o botão azul, o display é limpo e exibe a mensagem "Luz acesa", o LED verde liga-se temporariamente e a função `mover_servo(0)` altera o ciclo de trabalho para posicionar o servo em 0 graus.
3. **Ação do Botão Verde (Opção 2):** Ao pressionar o botão verde, o display exibe "luz apagada", o LED vermelho pisca e a função `mover_servo(90)` reajusta o sinal PWM para posicionar o servo de volta aos 90 graus.
