# Tutorial-Bluetooth-HC-05
Tutorial Bluetooth HC-05 com duas Placas NUCLEO-F401RE
# Introdução:
Esse tutorial tem o objetivo de introduzir o leitor a utilizar o módulo Bluetooth HC-05 para a comunicação entre duas placas NUCLEO-F401RE. Esse tutorial será dividido em três partes. A primeira parte será dedicada a entender como conectar dois módulos entre si. A segunda parte será uma prática com LED para aprender as ligações elétricas e como é passado a informação entre os módulos checar. Por último, apresentar funções interessantes para projetos mais complexos. 
# Começando com o HC-05
O módulo Bluetooth HC-05 é um transmissor de informação. Para que dois módulos consigam comunicar entre si é preciso que um dos módulos seja o mestre e o outro o servo. O mestre irá, sempre que ligado, procurar pelo servo, e vice-versa. Para que isso ocorra utilizamos a FT232RL USB to TTL, essa placa juntamente com o Teraterm permitem que dois módulos se reconheçam e interajam entre si. Abaixo está um link para ajudar a com a configuração do módulo.

[utilizando a FT232RL e o Teraterm para configurar o HC-05](https://www.arduinoecia.com.br/modulo-bluetooth-hc-05-conversor-ftdi/)



![image](https://github.com/user-attachments/assets/a65120a2-5fe1-4ad7-94e0-9a7bc2eb8a8f)

Agora que a configuração esta feita, podemos partir para a primeira prática e ver os módulos funcionando!
# Primeira prática: LED
Antes de tudo, é preciso realizar as conexões corretas entre o módulo e a placa núcleo. O VCC do módulo pode ser alimentado pelo 3.3V da placa, o GND do módulo no GND da placa, o RXD é p receptor de informações e na placa núcleo é o pino PA_10 e o TXD que é o transmissor é o pino PA_9. A foto abaixo mostra o mapa de pinos da NUCLEO-401RE para auxiliar-los nas conexões.

![image](https://github.com/user-attachments/assets/df690810-7d15-4b23-81ac-c86b935ecd67)


![image](https://github.com/user-attachments/assets/2424c8d0-1b5f-4a13-8020-2011685e0021)

Agora podemos rodar o primeiro código utilizando os módulos como comunicação entre as placas. O objetivo é pressionar o botão do usuário em uma placa e acender o LED da outra placa, sem conexões físicas!
A informção passada pelos módulos é em formato de char e existem 
```C++
DigitalIn(D1);
