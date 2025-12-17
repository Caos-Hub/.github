<p align="center">
  <img src="https://raw.githubusercontent.com/Caos-Hub/.github/main/profile/assets/caos-hub-logo-blanco.png"
       alt="Caos Hub Logo"
       width="420" />
</p>

<p align="center">
  <strong>Embedded Systems · IoT · Industrial Communications</strong>
</p>


# Caos Hub  
_Embedded & IoT Technology Organization_


**Caos Hub** es una organización tecnológica dedicada al diseño y desarrollo de sistemas embebidos, plataformas IoT y soluciones de comunicación industrial.

Nuestro trabajo se centra en construir arquitecturas **modulares, escalables y
mantenibles**, pensadas para dispositivos en producción y despliegues de largo plazo.

---

## 🚀 Plataforma Central — Levix

**Levix** es la plataforma IoT y de firmware embebido desarrollada por Caos Hub,
diseñada principalmente para **ESP32**, con soporte para múltiples tecnologías de
comunicación y protocolos industriales.

### Capacidades principales
- Arquitectura de firmware modular (Arduino / ESP32)
- Soporte multi-conectividad:
  - WiFi y Ethernet
  - LoRa y XBee
  - RS485 / Modbus
- Abstracción de hardware para integración rápida
- Preparado para servicios en la nube:
  - MQTT
  - TLS
  - OTA (actualizaciones remotas)

---

## 🧩 Arquitectura General de la Plataforma Levix

```mermaid
flowchart TB
    CH[Caos Hub] --> L[Plataforma Levix]

    subgraph L [Levix Platform]
        OS[Levix OS\nFirmware Base ESP32]
        CM[Connectivity Manager]
        HAL[Hardware Abstraction Layer]

        OS --> CM
        OS --> HAL
    end

    subgraph COMMS [Comunicaciones]
        WIFI[WiFi / Ethernet]
        RF[LoRa / XBee]
        RS[RS485 / Modbus]
    end

    subgraph CLOUD [Servicios en la Nube]
        MQTT[MQTT Broker]
        OTA[OTA Updates]
        CLOUDAPP[Plataformas Cloud]
    end

    CM --> WIFI
    CM --> RF
    CM --> RS

    WIFI --> MQTT
    RF --> MQTT
    RS --> MQTT

    MQTT --> CLOUDAPP
    OTA --> OS
