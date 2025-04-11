# 📡 EasyPic Project

Projet de système embarqué basé sur un microcontrôleur **PIC 18F87K22**, conçu pour lire des données depuis un capteur à ultrasons et les transmettre via **Bluetooth**.

## 👥 Présenté par

Peter & Adja

## 🎯 Objectif

Mettre en place un système capable de :
- Lire les données d’un **capteur de distance**.
- Calculer la distance en temps réel.
- Transmettre les résultats sans fil via **Bluetooth (HC-05)**.

## 🧰 Technologies utilisées

- 🧠 **Microcontrôleur** : PIC 18F87K22 (architecture 8 bits)
  - Flash : 128 Ko
  - RAM : 4 Ko
  - Périphériques intégrés : UART, ADC 10 bits, Timers, I²C, SPI
- 🧪 **Capteur à ultrasons** (SRF04 ou similaire)
  - Portée : 2 à 400 cm
  - Précision : ±3 mm
  - Alimentation : 5V
- 📶 **Module Bluetooth HC-05**
  - Protocole : SPP (Serial Port Profile)
  - Transmission : UART à 9600 bauds
- 💻 **Logiciel de développement** : MikroC
- 🔧 **Carte de prototypage** : EasyPIC

## 🧱 Architecture du système

- Le capteur reçoit une impulsion de **10 µs** via la broche **Trigger**.
- Il émet un **ultrason** et attend le retour (rebond sur un obstacle).
- Le capteur envoie un signal **Echo** dont la durée est mesurée par le PIC.
- Le PIC calcule la distance à l’aide de la formule :

```c
distance = durée × 340 / 2;
# Easypic-18FK22
