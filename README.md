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

En caso de utilizar otro dispositivo distinto de la ESP32, mantener el orden y cablear con los correspondientes pines.

### Descripción del programa.
El programa de ejemplo envía y recibe 16 bytes en cada mensaje, primero se configura el sistema SPI, definiendo los pines de entradas y salidas, el modo, el máximo de bytes de transacción, y los buffers de envío y recepción, se limpian los buffers y se inicializa la comunicación. Dentro del bucle principal que se repite 10 veces, se realiza una transacción, la cual comienza por limpiar los buffers de contenido basura, luego se prepara el mensaje que será enviado del Slave al Master se configura la transacción, y finalmente se mandan y reciben los mensajes al mismo tiempo se realiza la verificación de errores, y se implementa un delay como ejemplo.

### Consideraciones de uso.
Este manejo de comunicación SPI es adecuado bajo ciertas circunstancias, por ejemplo, es ideal si el Master envía datos continuamente y no es relevante que el Slave alcance a recibir la totalidad de la información. Si se requiere que el proceso de comunicación sea totalmente simultaneo y el Slave reciba todos los datos, resulta necesario implementar el encolamiento, y un pin adicional que sirva como Handshake que le indique al master cuando el Slave esté listo para realizar otra transacción, sin embargo, este manejo además de ser más complejo demanda muchos más recursos el microcontrolador. Si se utiliza la configuración mostrada se recomienda realizar un correcto manejo y comprobación de los datos, pues si la distancia es muy grande o existen muchas perturbaciones al rededor la información se puede ver fácilmente comprometida o alterada.
