# Exemplos com ESP8266

Para utilizarmos o ESP8266 na Arduino IDE, deveremos adicionar a placa personalizada na IDE, para isto basta ir em Arquivo > Preferências e na aba configurações adicionar mais uma URL no campo URLs adicionais para Gestores de Placas.

URL: http://arduino.esp8266.com/stable/package_esp8266com_index.json

Após a adição ir no menu ferramentas e no menu gerenciar placas dentro do item placas, no gerenciador procurar por **esp8266** by **ESP8266 Community**. Após o download a placa está pronta para o uso.

## Pinagem do ESP8266

Segue o desenho esquemático dos pino no NODEMCU ESP8266:

<p align="center">
  <img src="https://i.stack.imgur.com/yT4hb.png">
</p>

# Dentro deste repositórios temos os seguintes projetos

## esp8266-matrix-led

Este é um exemplo obtido da biblioteca Parola modificado, onde cria um servidor web conectado na Wifi configurada e ao acessar este servidor web podemos alterar a mensagem exibida na matriz de leds, bem como o tipo da mensagem (Nomal ou Invertida), se a mensagem vai rolar pra direita o pra esquerda e sua velocidade. Neste exemplo precisamos das seguintes bibliotecas:

- [MD_Parola](https://github.com/MajicDesigns/MD_Parola)
- [MD_MAX72XX](https://github.com/MajicDesigns/MD_MAX72XX)

Estas bibliotecas podem ser instaladas diretamente de dentro da IDE do Arduíno, a única alteração que tive que fazer para os exemplos funcionarem normalmente foi trocar o tipo de hardware e a quantidade de dispositivos (Até pelo tamanho da minha matriz).

De:

```c
#define HARDWARE_TYPE MD_MAX72XX::PAROLA_HW
#define MAX_DEVICES 8
```

Para:

```c
#define HARDWARE_TYPE MD_MAX72XX::FC16_HW
#define MAX_DEVICES 4
```

Para que os caracteres sejam mostrados corretamente, pois utilizando o `PAROLA_HW` os caracteres
