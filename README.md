# Sistema_Alarmes_IOT

### Configuração do Servidor para Sistema de Alarme IoT

Este tutorial guiará você passo a passo na configuração do servidor para um sistema de alarme IoT utilizando MQTT, ESP32, Node-RED e HiveMQ.

#### Pré-requisitos:

- **ESP32**
- **Broker MQTT** (neste exemplo, utilizaremos o HiveMQ)
- **Node-RED** instalado e configurado
- **Acesso à internet** para comunicação entre as placas e o servidor

### Usando o Wowki para placas onlines e simular o teste
 1. Acesse os links abaixo através do Wowki:
    - Placa1 ->
    - Placa2 -> 
### Configuração do Broker MQTT

1. **Credenciais do HiveMQ**:
   - Host: `broker.hivemq.com`
   - Porta: `1883` para conexões sem TLS
   - Tópicos: `alarme/movimento` para envio de informações de movimento do sensor PIR.

### Configuração da Placa ESP32 Fisíca
1. **Upload do Código**:
   - Faça o upload do código(arquivo salvo na pasta "códigos" para a ESP32 usando o Arduino IDE.
   - Conecte a ESP32 à rede Wi-Fi e verifique se ela está enviando dados para o broker.
     
2. **Placa1 - ESP32**:
   - Conecte o VCC no 3V3 da placa.
   - Conecte o output no pino 12.
   - Conecte o GND no GND da placa.

3. **Placa2 - ESP32**:
   - Conecte o buzzer no pino 2.

              APAGAR ISSO DPS:
   - MUDAR O PINO DO BUZZER NO PROJETO! O LED ESTA NO 2 E O BUZZER NAO TA CONECTADO AINDA!

### Configuração do Node-RED

1. **Adição do Nó MQTT**:
   - No Node-RED, adicione os nós MQTT para se conectar ao broker HiveMQ.
   - Configure o nó MQTT com o host do HiveMQ e o tópico configurado (`alarme/movimento`).

2. **Criação de Dashboard**:
   - Instale o pacote do dashboard no Node-RED:
   - Adicione widgets ao painel para monitorar o estado do alarme, como gráficos ou indicadores de movimento.

3. **Configuração dos Nós**:
   - Adicione nós de função para manipular os dados recebidos e, se necessário, enviar comandos de volta ao ESP32.
