# 🌡️ Sistema de Monitoramento Ambiental IoT (Farmacêutico)

![Banner do Projeto](https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExaTZ3am54NnZpdWZ4NHNuZXJ5ZWZ2cTF6ZmhrcnZsdzg5NXM2bXV5NiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/5x4bARYgmAqKv2hMjM/giphy.gif)
*(Substitua o link acima por uma imagem de capa legal do seu projeto ou um print do Wokwi)*

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-3C5280?style=for-the-badge&logo=eclipse-mosquitto&logoColor=white)
![Codespaces](https://img.shields.io/badge/GitHub%20Codespaces-181717?style=for-the-badge&logo=github&logoColor=white)

> **Status do Projeto:** ✅ Concluído (Avaliação Prática SENAI - Bloco 01)

## 📖 Sobre o Projeto
Este projeto consiste em um sistema **ciber-físico** desenvolvido para monitorar a temperatura e umidade de ambientes críticos de logística farmacêutica. O objetivo é garantir a integridade de insumos sensíveis através da coleta de dados em tempo real e processamento em nuvem.

Devido a restrições de infraestrutura local, este projeto foi adaptado para rodar inteiramente em ambiente **Cloud** (GitHub Codespaces), demonstrando flexibilidade e resiliência técnica.

---

## ⚙️ Arquitetura da Solução

O fluxo de dados segue o modelo **Publish/Subscribe**:

1.  **Sensor DHT22** coleta a temperatura.
2.  **ESP32** processa e envia via Wi-Fi.
3.  **Broker MQTT** (HiveMQ) recebe a mensagem.
4.  **Backend Java** (Codespaces) assina o tópico e processa o alerta.

---

## 🛠️ Hardware e Eletrônica

O projeto foi prototipado utilizando o simulador **Wokwi**.

| Componente | Função | Conexão (GPIO) |
| :--- | :--- | :--- |
| **ESP32 DevKit** | Microcontrolador Wi-Fi | N/A |
| **DHT22** | Sensor de Temp/Umidade | GPIO 15 |
| **Resistor 10kΩ** | Pull-up do Sensor | Entre VCC e Data |

### 🔌 Esquema Elétrico
![Esquema Elétrico Wokwi](https://ibb.co/23NBXJ3v)
*(Coloque aqui o print das conexões no Wokwi)*

---

## 💻 Software e Configurações

### 1. Firmware (ESP32 / C++)
Utiliza a biblioteca `PubSubClient` para comunicação MQTT.
* **Broker:** `broker.hivemq.com`
* **Porta:** `1883`
* **Tópico:** `senai/ryhan/temperatura`

### 2. Backend (Java / Maven)
Aplicação console desenvolvida para rodar no **GitHub Codespaces**. Utiliza a biblioteca `Eclipse Paho`.
* **Feature:** Conexão persistente com Client ID dinâmico.
* **Feature:** Alerta visual no log quando `Temp > 30.0°C`.

---

## 🚀 Como Executar

### Pré-requisitos
* Conta no GitHub.
* Acesso ao [Wokwi](https://wokwi.com).

### Passo 1: Hardware (Simulação)
1.  Acesse o projeto no Wokwi (insira o link do seu projeto público aqui).
2.  Verifique se o `ssid` está como `"Wokwi-GUEST"`.
3.  Inicie a simulação.

### Passo 2: Backend (Java)
1.  Clone este repositório.
2.  Abra no **GitHub Codespaces**.
3.  Execute o comando:
    ```bash
    mvn clean compile exec:java
    ```

---

## 📊 Evidências de Teste

Aqui estão as provas de funcionamento do sistema integrado:

### ✅ Teste de Conexão e Recebimento
![Log do Console Java](https://ibb.co/B5tmr3fx)
*(Print do terminal do Codespaces mostrando: "Temperatura: 40.5C")*

---

## 👨‍💻 Autor

**Ryhan Gabriel Schutz**
* **Curso:** Técnico em Cibersistemas - SENAI/SC
* **Turma:** T TCPA 2025/1 INT1
* **Contato:** Linkedin : Ryhan Schutz


---
*Desenvolvido com foco em agilidade e adaptação técnica. "Be Water".* 🌊