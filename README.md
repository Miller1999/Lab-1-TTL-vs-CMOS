# Lab 01 - Comparación de tecnología CMOS vs TTL
## Integrantes
- Miller Javier Arias Quintero
- Juan Ruiz
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
   |**Consumo de energía**    | Rango de mA | Rango de uA |
   |**Velocidad de operación**| 10ns        | 50 - 200ns  |
   |**Impedancia de entrada** | Baja        | Alta        |
   |**Nivel lógico**          | Voltajes especificos para "1" y "0" | Mayor rango debido a la flexibilidad del voltaje de operacion |
   |**Resistencia al ruido**  | Menor resistencia al ruido          | Mayor resistencia al ruido   |
   |**Aplicaciones típicas**  | Sistemas de alta velocidad          | Sistemas de bajo consumo    |
   
3. Circuitos equivalentes
   - TTL 74LS04
   - CMOS CD4069
4. Simulacion con señal cuadrada de 1kHz
   - TTL 74LS04
   - CMOS CD4069
6. Tiempos
   - TTL 74LS04
   - CMOS CD4069
### Parte 2 
1. Fan-in y Fan-out
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

## Referencias
* [TTL 74LS04 Datasheet]([https://github.com/johnnycubides/qucs-tutorial-examples](https://www.alldatasheet.com/datasheet-pdf/view/5638/MOTOROLA/74LS04.html))
* [CMOS CD4069 Datasheet]([https://github.com/johnnycubides/qucs-tutorial-examples](https://www.alldatasheet.com/datasheet-pdf/view/50860/FAIRCHILD/CD4069.html))
  

