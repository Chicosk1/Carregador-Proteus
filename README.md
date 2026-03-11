# Projeto do Carregador

Este repositório contém o projeto de um carregador, desenvolvido utilizando o software Proteus.

---

## Visão Geral do Projeto

O circuito recebe uma tensão alternada do secundário de um transformador, converte para corrente contínua através de uma ponte retificadora, filtra os ruídos e regula a saída para exatos 12V utilizando o circuito integrado LM7812. A placa de circuito impresso foi projetada para ter um design compacto e funcional.

---

## Especificações Físicas da PCB

* **Formato:** Retangular
* **Dimensões:** 80 mm x 40 mm
* **Camadas:** Face simples (Bottom Copper)

---

## Lista de Componentes (BOM)

* **J1 (SIL-100-02):** Conector de entrada para a tensão AC do transformador.
* **BR1 (BRIDGE):** Ponte de diodos para retificação de onda completa.
* **C2 (CAP-ELEC - 1uF):** Capacitor eletrolítico para a filtragem inicial.
* **U1 (7812):** Regulador de tensão linear positivo de 12V.
* **C1 (CAP - 1nF):** Capacitor para filtragem de ruídos de alta frequência na saída.
* **R1 (Resistor - 1k):** Resistor limitador de corrente.
* **D1 (LED):** Diodo emissor de luz vermelho atuando como indicador de painel.
* **J2 (CONN-SIL2):** Conector de saída fornecendo os 12V DC regulados.

---

## Como o Circuito Funciona

O funcionamento desta fonte é dividido em quatro estágios de fontes lineares:

1. **Entrada de Energia:** A tensão AC entra pelo conector **J1**, sem polaridade definida, indo direto para a ponte retificadora.
2. **Retificação:** A ponte **BR1** converte a corrente alternada em corrente contínua pulsante, "rebatendo" os ciclos negativos da onda para o lado positivo.
3. **Filtragem Principal:** O capacitor eletrolítico **C2** armazena energia e a libera durante as quedas da onda pulsante. Isso nivela a tensão, criando uma linha DC com uma pequena ondulação residual.
4. **Regulação e Saída:** Essa tensão pré-filtrada entra no pino *VI* (Input) do regulador **7812**. Ele atua dissipando o excesso de tensão em forma de calor e garantindo que o pino *VO* (Output) entregue fixos 12V. O capacitor **C1** estabiliza essa saída contra transientes rápidos. Ao final, a energia passa pelo limitador **R1** para acender o **LED** indicativo e chega ao conector **J2** pronta para uso.