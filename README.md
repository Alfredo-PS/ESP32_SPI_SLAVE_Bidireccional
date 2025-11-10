# ESP32 SPI Slave Bidireccional

## SPI Slave
El presente código sirve para configurar la ESP32 como esclavo para la comunicación por SPI, permitiendo el envió y recepción de datos, programado por medio de ESP-IDF SDK Espressif.

## Conexiones.

| ESP32 Master  | ESP32 Slave   |
| ------------- |:-------------:|
| MOSI   23     | MOSI   23     |
| MISO   19     | MISO   19     |
| SCLK   18     | SCLK   18     |
| CS     5      | CS     5      | 
| GND           | GND           |

En caso de utilizar otro dispositivo distinto de la ESP32, mantener el orden y cablear con los correspondientes pines
