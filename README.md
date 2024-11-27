# Lab 01 - Comparación de tecnología CMOS vs TTL
## Integrantes
- Miller Javier Arias Quintero
- Juan Pablo Ruiz Sabogal
- Santiago N
## Tabla de contenidos
- [Objetivo](#Objetivo)
- [Recursos](#Recursos)
- [Procedimiento](#Procedimiento)
  - [Parte 1](#Parte-1)
  - [Parte 2](#Parte-2)
  - [Parte 3](#Parte-3)
## Objetivo
- Identificar las características de un dispositivo fabricado en diferentes tecnologías.
## Recursos
- Negador TTL 74LS04
- Negador CMOS CD4069
- Simulador
- Modelos spice
- Datasheets
## Procedimiento
### Parte 1
1. Especificaciones tecnicas
   |                          | TTL 74LS04  | CMOS CD4069 |
   |:------------------------:|:-----------:|:-----------:|
   |**Voltaje de operación**  | 5V          | 3V - 15V    |
   |**Consumo de energía**    | 10mW/puerta | Rango de uA (Prácticamente nulo) |
   |**Velocidad de operación**| 10ns        | 50 - 200ns  |
   |**Impedancia de entrada** | Baja        | Alta        |
   |**Nivel lógico**          | Voltajes especificos para "1" y "0" | Mayor rango debido a la flexibilidad del voltaje de operacion |
   |**Resistencia al ruido**  | Menor resistencia al ruido          | Mayor resistencia al ruido   |
   |**Aplicaciones típicas**  | Sistemas de alta velocidad          | Sistemas de bajo consumo    |
   |**Tiempo de subida (tr)**  |      15ns     |  20ns      |
   |**Tiempo de bajada (tf)**    |      15ns   |      20ns   |
   |**Tiempo de retardo (tPHL)**|   10ns    |   50ns      |
   |**Tiempo de retardo (tPLH)** |  9ns      |      50ns   |
   |**Input high voltage (VIH)**  |  2V Min        |  4V Min    |
   |**Input low voltage (VIL)** |    0.8V Max    |    1V Max    |
   |**Output high voltage (VOH)** |  2.7V Min    |    4.95V Min     |
   |**Output low voltage (VOL)** |    0.5V Max    |   0.05V Max     |

   Cabe recalcar que los tiempos de bajada, subida y retardo son los valores típicos, pueden ser más altos o más bajos.
   
3. Circuitos equivalentes
- TTL 74LS04
     
  Para el TTL se maneja un circuito más primitivo pero bajo el mismo concepto que el CMOS, en este solo se emplea un transistor el cual cumple la función de abrirse o cerrarse dependiendo de el 0 o el 1 lógico que tendremos a la entrada, invirtiendo la salida.

IMAGEN

- CMOS CD4069
     
  La palabra CMOS viene de complementary metal oxide semicondutor, lo que quiere decir que cada compuerta esta compuesta de dos transistores, un tipo n y un tipo p, los cuales tendrán la función de compuertas     logicas. Dependiendo de la entrada, alguno de los dos transistores se polarizará y el otro se abrirá, lo que causa que se invierta el 0 o el 1 lógico a la entrada.

IMAGEN

3. Simulacion con señal cuadrada de 1kHz
   - TTL 74LS04
   - CMOS CD4069
4. Tiempos
   
   |                          | TTL 74LS04  | CMOS CD4069 |
   |:------------------------:|:-----------:|:-----------:|
   |**Tiempo de subida (tr)**  |           |       |
   |**Tiempo de bajada (tf)**    |         |         |
   |**Tiempo de retardo (tphl)**|          |         |
   |**Tiempo de retardo (tplh)** |         |         |

### Parte 2 
1. Fan-in y Fan-out
   El calcúlo del Fan-out se realiza de la siguiente manera:
   - TTL 74LS04
   - CMOS CD4069
2. Disipación de potencia
3. Circuitos de entrada y salida
### Parte 3
1. Oscilador en anillo
   - Caracteristicas
2. Anillo de 3 compuertas
   - Simulación
   - Mediciones
3. Anillo de 5 compuertas
   - Simulación
   - Mediciones
4. Comparación 
## Referencias

  * [TTL 74LS04 Datasheet](https://www.alldatasheet.com/datasheet-pdf/view/5638/MOTOROLA/74LS04.html)
  * [CMOS CD4069 Datasheet](https://www.alldatasheet.com/datasheet-pdf/view/50860/FAIRCHILD/CD4069.html)
  

