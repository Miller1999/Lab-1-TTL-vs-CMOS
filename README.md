# Lab 01 - Comparación de tecnología CMOS vs TTL

## Integrantes

- Miller Javier Arias Quintero
- Juan Pablo Ruiz Sabogal
- Daniel Santiago Navarro Gil

## Tabla de contenidos

- [Lab 01 - Comparación de tecnología CMOS vs TTL](#lab-01---comparación-de-tecnología-cmos-vs-ttl)
  - [Integrantes](#integrantes)
  - [Tabla de contenidos](#tabla-de-contenidos)
  - [Objetivo](#objetivo)
  - [Recursos](#recursos)
  - [Procedimiento](#procedimiento)
    - [Parte 1](#parte-1)
    - [Parte 2](#parte-2)
    - [Parte 3](#parte-3)
  - [Referencias](#referencias)

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
   | | TTL 74LS04 | CMOS CD4069 |
   |:------------------------:|:-----------:|:-----------:|
   |**Voltaje de operación** | 5V | 3V - 15V |
   |**Consumo de energía** | 10mW/puerta | Rango de uA (Prácticamente nulo) |
   |**Velocidad de operación**| 10ns | 50 - 200ns |
   |**Impedancia de entrada** | Baja | Alta |
   |**Nivel lógico** | Voltajes especificos para "1" y "0" | Mayor rango debido a la flexibilidad del voltaje de operacion |
   |**Resistencia al ruido** | Menor resistencia al ruido | Mayor resistencia al ruido |
   |**Aplicaciones típicas** | Sistemas de alta velocidad | Sistemas de bajo consumo |
   |**Tiempo de subida (tr)** | 15ns | 20ns |
   |**Tiempo de bajada (tf)** | 15ns | 20ns |
   |**Tiempo de retardo (tPHL)**| 10ns | 50ns |
   |**Tiempo de retardo (tPLH)** | 9ns | 50ns |
   |**Input high voltage (VIH)** | 2V Min | 4V Min |
   |**Input low voltage (VIL)** | 0.8V Max | 1V Max |
   |**Output high voltage (VOH)** | 2.7V Min | 4.95V Min |
   |**Output low voltage (VOL)** | 0.5V Max | 0.05V Max |

   Cabe recalcar que los tiempos de bajada, subida y retardo son los valores típicos, pueden ser ligeramente más altos o más bajos (se mantiene el orden de magnitud).

2. Circuitos equivalentes

- TTL 74LS04
Para el TTL se maneja un circuito más primitivo pero bajo el mismo concepto que el CMOS, en este solo se emplea un transistor el cual cumple la función de abrirse o cerrarse dependiendo de el 0 o el 1 lógico que tendremos a la entrada, invirtiendo la salida.
<div style="display:flex; justify-content:center; align-items:center;">
   <img src="/assets/TTLEquivalente.png" style=""/>
</div>

- CMOS CD4069
  La palabra CMOS viene de complementary metal oxide semicondutor, lo que quiere decir que cada compuerta esta compuesta de dos transistores, un tipo n y un tipo p, los cuales tendrán la función de compuertas logicas. Dependiendo de la entrada, alguno de los dos transistores se polarizará y el otro se abrirá, lo que causa que se invierta el 0 o el 1 lógico a la entrada.

<div style="display:flex; justify-content:center; align-items:center;">
   <img src="/assets/CMOSEQUIVALENTE.png" style=""/>
</div>

3. Señal cuadrada de 1kHz (Simulación vs Real)

- TTL 74LS04
  - Simulación
    
    ![](/assets/Simulaciones/74LS.png)
    
  - Real

![](/assets/74LS04/F0000TEK.BMP)

EXPLICACION DE LA COMPARATIVA Y ENTRADA VS SALIDA SIMULADA

- CMOS CD4069

  - Simulación

  ![](/assets/Simulaciones/CD40.png)

  - Real

![](/assets/CD4069/F0001TEK.BMP)

EXPLICACION DE LA COMPARATIVA Y ENTRADA VS SALIDA SIMULADA

4. Tiempos

   Dado que los tiempos de subida y bajada no podian percibirse aún aumentando la escala en el osciloscopio, se usaron los cursores del mismo para tomar dichas medidas.

   |                              | TTL 74LS04 | CMOS CD4069 |
   | :--------------------------: | :--------: | :---------: |
   |  **Tiempo de subida (tr)**   |   1.6us    |    1.6us    |
   |  **Tiempo de bajada (tf)**   |   1.6us    |    1.6us    |
   | **Tiempo de retardo (tphl)** |  0.004498  |  0.004498   |
   | **Tiempo de retardo (tplh)** |  0.004962  |  0.004498   |

### Parte 2

1. Fan-in y Fan-out

   Para hallar el Fan-in se realiza el siguiente procedimiento:
   Para hallar el Fan-out se realiza el siguiente procedimiento:

   - TTL 74LS04
   - CMOS CD4069

2. Disipación de potencia
3. Circuitos de entrada y salida

### Parte 3

1. Oscilador en anillo
   
   ![](/assets/Osciladorgeneral.jpg)
   
   - Caracteristicas
3. Anillo de 3 compuertas
   Con este circuito:
   
   ![](/assets/Simulaciones/anillo3.png)
   
   - Simulación
   
     ![](/assets/Simulaciones/anillo3S.png)
     
   - Mediciones
     
     ![](/assets/Anillo3/F0014TEK.BMP)
     
5. Anillo de 5 compuertas
   Con este circuito:

   ![](/assets/Simulaciones/anillo5.png)

   - Simulación

     ![](/assets/Simulaciones/anillo5S.png)

   - Mediciones

     ![](/assets/Anillo5/F0013TEK.BMP)

6. Comparación anillo de 3 compuertas vs anillo de 5 compuertas

## Referencias

- [TTL 74LS04 Datasheet](https://www.alldatasheet.com/datasheet-pdf/view/5638/MOTOROLA/74LS04.html)
- [CMOS CD4069 Datasheet](https://www.alldatasheet.com/datasheet-pdf/view/50860/FAIRCHILD/CD4069.html)
