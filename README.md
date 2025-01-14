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
  - [Marco Teórico](#marco-teórico)
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

## Marco Teórico

### Inversor

Es un circuito que realiza la función logica NOT, lo que significa que invierte el 0 o el 1 lógico de la entrada, si la entrada es un 1 lógico, la salida es un 0, y viceversa.

![](https://github.com/Miller1999/Lab-1-TTL-vs-CMOS/blob/main/assets/NOT.png)

Los circuitos integrados que estamos manejando están compuestos de varias compuertas logicas NOT. Para el caso del TTL (Transistor Transistor-Logic) 74LS04 es el integrado mas anticuado que estamos manejando ya que este usa el tipo de transistor BJT, logrando altas velocidades de conmutación. Por otro lado, el CMOS (Complementary Metal-Oxide-Semiconductor) usa MOSFET's para realizar la negación, este tiene un consumo considerablemente mas bajo y opera en rangos más amplios de voltaje.
### Fan-in y Fan-out

Estos parámetros son importantes respecto al diseño de circuitos digitales ya que nos brindan información sobre la cantidad maxima de conexiones que podemos realizar a cada compuerta.

El fan-in representa la máxima cantidad de entradas que puede manejar la compuerta. En el caso de los inversores esta suele ser 1

El fan-out representa la máxima cantidad de entradas que puede alimentar la salida de la compuerta sin degradar las señales. Los TTL tienen un Fan-out estandar de 10, mientras que los CMOS tienen un estandar de 400 dado su bajo consumo de corriente en la entrada. Se calcula de la siguiete manera:

![](https://github.com/Miller1999/Lab-1-TTL-vs-CMOS/blob/main/assets/fan%20out.png)

### Tiempo de subida y bajada

Los tiempos de subida y bajada hacen referencia a la rapidez con la que una señal (en este caso cuadrada) cambia entre estados logicos, siendo el tiempo de subida el tiempo que tarda de pasar de un valor bajo (10%) a un valor alto (90%), y el de bajada de un valor alto (90%) a un valor bajo (10%). Experiemntalmente se puede medir directamente desde el osciloscopio. 

### Anillo Lógico

Un anillo lógico u oscilador de anillo es un circuito en el cual conectamos varias compuertas de manera impar (es decir, 3,5,7,etc) y conectamos la salida de la última compuerta con la entrada de la primer compuerta que inicia el anillo, por medio de este podemos analizar tiempo de propagación y frecuencia de oscilación.

![](https://github.com/Miller1999/Lab-1-TTL-vs-CMOS/blob/main/assets/anillo%20formula.png)
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

- Explicación y comparación

En escencia la compuerta NOT invierte la señal volviendo los 0 a 1 y viceversa. Comparando la señal de entrada y de salida se demuestra lo anterior explicado, y al comparar la simulacion con la prueba real no hay una variación considerable, ya que ambas muestran los mismos resultados.

- CMOS CD4069

  - Simulación

  ![](/assets/Simulaciones/CD40.png)

  - Real

![](/assets/CD4069/F0001TEK.BMP)

- Explicación y comparación

la explicacion en el caso del CMOS es igual a la del TTL, y comparando la señal de entrada y de salida se demuestra lo anterior explicado, y al comparar la simulacion con la prueba real no hay una variación considerable, ya que ambas muestran los mismos resultados.
   |                              | TTL 74LS04 | CMOS CD4069 |
   | :--------------------------: | :--------: | :---------: |
   |  **$V_{IH}$**                |   - 0.2 V  |    - 0.2 V    |
   |  **$V_{IL}$**               |   5.2 V    |    5.2 V   |
   |  **$V_{OH}$**                |   0.2 V    |  0.2 V   |
   |  **$V_{OL}$**                 |  4.8 V     |  4.8 V   |

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

   Para hallar el Fan-out se realiza el procedimiento descrito en el marco teórico:
   - TTL 74LS04
     
     ![](https://github.com/Miller1999/Lab-1-TTL-vs-CMOS/blob/main/FAN%20OUT%20TTL.png)

    Para el Fan-in = 1.
   
   - CMOS CD4069
     Para el CMOS se halla un Fan-out muy alto, esto se debe a que en su tecnología las corrientes de entrada son muy bajas (en el orden los pico o de los microamperios), por lo cual a una sola salida se puede conectar muchas entradas
     
     ![](https://github.com/Miller1999/Lab-1-TTL-vs-CMOS/blob/main/faN%20OUT%20CD4069.png)
  
     Igualmente para CMOS el Fan-in = 1.
     
2. Disipación de potencia
  - TTL 74LS04
    
      Con valores de $I_{CC} = 2mA$ y $V_{DD} = 5V$, obtenemos una potencia estatica de $10mW$
        
  - CMOS CD4069

      Usando una carga de 15pF, obtenemos una potencia dinamica de $0.375mW$, siendo esta la dominante no es necesario calcular la potencia estatica

### Parte 3

1. Oscilador en anillo
   Se hace conectando en serie varias compuertas NOT, donde cada compuerta NOT invierte la señal que recibe, generando un retardo debido al tiempo de propagación de cada compuerta. Luego, la salida de la última compuerta se conecta a la entrada de la primera, creando un bucle continuo.
   
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

  La mayor diferencia entre los dos anillos es la frecuencia, ya que esto depende del numero de compuertas que se usen, en este caso se evidencia que el anillo de 5 compuertas tiene una amplitud mas grande debido a la suma de los desfases de las compuertas, por esto tiene una frecuencia mas baja.

   Siendo n el numero de compuertas usadas en nuestro anillo. Por lo cual es lógico esperar que la frecuencia del anilo de 5 compuertas sea menor al anillo de 3 compuertas.

## Referencias

- [TTL 74LS04 Datasheet](https://www.alldatasheet.com/datasheet-pdf/view/5638/MOTOROLA/74LS04.html)
- [CMOS CD4069 Datasheet](https://www.alldatasheet.com/datasheet-pdf/view/50860/FAIRCHILD/CD4069.html)
