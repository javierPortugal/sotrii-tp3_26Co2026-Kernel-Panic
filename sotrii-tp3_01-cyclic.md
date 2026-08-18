# sotrii-tp3_01-cyclic
#### Planificar cada uno de los siguientes sistemas de tareas periódicas ejecutadas por un Cyclic Scheduling. Asignar prioridades. Determinar Factor de Uso, Hiperperiodo, Período Secundario. Desarrollar el Test de Garantía correspondiente a lo planificado. Dibujar el Diagrama de Gantt de lo planificado.

## Sistema 1
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 4    |
|T2      | 2  |  5   |
|T3      | 5  | 20   |

01. Hay que asignar las Prioridades.\
Las prioridades se asignan inversamente proporcionales a sus periodos \(T\)

- Prioridad 1 (Alta): T1
- Prioridad 2 (Media): T2
- Prioridad 3 (Baja): T3

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{4} + \frac{2}{5} + \frac{5}{20} = 0.25 + 0.40 + 0.25 = \mathbf{0.90}$$

- Test de Garantía Inicial: Como $$\(U = 0.90 \leq 1\)$$, el sistema es potencialmente planificable.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(4,5,20)=\mathbf{20}\)$$

04. Periodo Secundario o Tamaño de Trama (f\)\
Para determinar el tamaño del frame (f\), se deben cumplir tres condiciones fundamentales:

 a. $$(f \geq \max(C_i) \implies f \geq 5\)$$\
 b. $$H \pmod f = 0 \implies 20 \pmod f = 0$$ (Posibles  valores: 5, 10, 20)\
 c. $$(2f - \text{mcd}(T_i, f) \leq D_i\)$$ para toda tarea.
   - Si probamos con \(f = 5\) para T1:
     
   $$(2(5)-\text{mcd}(4,5)=10-1=9\not{\le }4\)$$ (Falla).

Como ningún frame entero satisface las tres condiciones de manera directa, se requiere dividir las tareas quedando: $$T_31a$$ (C=1), $$T_2a$$ (C=1)\),  $$T_2b$$ (C=1) y T3 dividido en 5 tareas, $$T_3a$$,  $$T_3b$$,  $$T_3c$$,  $$T_3d$$,  $$T_3e$$, con C=1.

- Seleccionamos \(f = 1\) (divisor de 20):
   - T1: $$\(2(1) - \text{mcd}(4, 1) = 1 \leq 4\)$$ (Cumple)
   - T2: $$\(2(1) - \text{mcd}(5, 1) = 1 \leq 5\)$$ (Cumple)
   - T3: $$\(2(1) - \text{mcd}(20, 1) = 1 \leq 20\)$$ (Cumple)

- El periodo Secundario Optimo es f = 1
  
   
05. Cronograma y Diagrama de Gantt (Ciclo de 0 a 20)Con \(f = 1\), hay 20 frames en el hiperperiodo.

- Marco 0: T1(inst 0: 0-1)
- Marco 1: T2(inst 0, parte 1/2: 0-1)
- Marco 2: T2(inst 0, parte 2/2: 0-1)
- Marco 3: T3(inst 0, parte 1/5: 0-1)
- Marco 4: T1(inst 1: 0-1)
- Marco 5: T2(inst 1, parte 1/2: 0-1)
- Marco 6: T2(inst 1, parte 2/2: 0-1)
- Marco 7: T3(inst 0, parte 2/5: 0-1)
- Marco 8: T1(inst 2: 0-1)
- Marco 9: T3(inst 0, parte 3/5: 0-1)
- Marco 10: T2(inst 2, parte 1/2: 0-1)
- Marco 11: T2(inst 2, parte 2/2: 0-1)
- Marco 12: T1(inst 3: 0-1)
- Marco 13: T3(inst 0, parte 4/5: 0-1)
- Marco 14: T3(inst 0, parte 5/5: 0-1)
- Marco 15: T2(inst 3, parte 1/2: 0-1)
- Marco 16: T1(inst 4: 0-1)
- Marco 17: T2(inst 3, parte 2/2: 0-1)
- Marco 18: (vacio)
- Marco 19: (vacio)


Diagrama de Gantt


|Marco|   M1  |  M2 | M3 | M4 |
| :----- | :--:| :--:| :--:|:--:|
|Tiempo  |0  --  5|    -- 10 |  -- 15|  -- 20|
|T1  C=1 | x | x |  x x | x |
|T2   C=2     | xx  | xx   |  x  x  | x  x | 
|T3  C=5      |  xx |  xx |   x|   |  
|Ocio (-)     |  |   |   |  --| 

## Sistema 2
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 6    |
|T2      | 2  |  10  |
|T3      | 2  | 18   |

01. Hay que asignar las Prioridades (Rate Monotonic).\
Las prioridades se asignan inversamente proporcionales a sus periodos \(T\)

- Prioridad 1 (Alta): T1
- Prioridad 2 (Media): T2
- Prioridad 3 (Baja): T3

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{6} + \frac{2}{10} + \frac{2}{18} = 0.1667 + 0.20 + 0.1111 = \mathbf{0.4778}$$

- Test de Garantía Inicial: Como $$\(U  \leq 1\)$$, el sistema es holgadamente asegurable.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(6,10,18)=\mathbf{90}\)$$

04. Periodo Secundario o Tamaño de Trama (f\)\
Para determinar el tamaño del frame (f\), se deben cumplir tres condiciones fundamentales:

 a. $$f \geq \max(1,2,2) \implies f \geq 2\$$\
 b. $$90 \pmod f = 0$$\
 c. Comprobacion para $$f = 2$$

   - T1: $$\(2(2) - \text{mcd}(6, 2) = 4 - 2 = 2 \leq 6\)$$ (Cumple)
   - T2: $$\(2(2) - \text{mcd}(10, 2) = 4 - 2 = 2 \leq 10\)$$ (Cumple)
   - T3: $$\(2(2) - \text{mcd}(18, 2) = 4 - 2 = 2 \leq 18\)$$ (Cumple)

El tamaño de trama seleccionado es $$f = 2$$
   
05. Cronograma y Diagrama de Gantt
   Dado que H = 90 la ejecucion se repite de forma ciclica organizada en rafagas de frames de tamaño 2:
  - Frame 1 [0-2]: Ejecuta T1 (1) y T2 (1)
  - Frame 2 [2-4]: Ejecuta T2 (1) y T3 (1)
  - Frame 3 [4-6]: Ejecuta T3 (1), Libre (1)
  - Frame 4 [6-8]: Ejecuta T1 (1), Libre (1)
  - ....el patron continua.....

|Marco|   M1  |  M2 | M3 | M4 | M5  |  M6  |
| :----- | :--:| :--:| :--:|:--:|:--:|:--:|
|Tiempo  |0  --  3|  -- 6 |  -- 9|  -- 12|  -- 15|  -- 18|
|T1  C=1    | x  |    | x |   | x |  |
|T2   C=2     | xx  |    |   | xx |   |  |
|T3  C=2      |   |  xx |   |   |   |   |
|Ocio (-)     |  | -|  --|  - |   --|  ---|







## Sistema 3
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 8    |
|T2      | 3  |  15  |
|T3      | 4  | 20   |
|T4      | 6 | 22   |

01. Hay que asignar las Prioridades (Rate Monotonic).\
Las prioridades se asignan inversamente proporcionales a sus periodos \(T\)

- Prioridad 1 (Alta): T1
- Prioridad 2 (Media): T2
- Prioridad 3 (Media): T3
- Prioridad 4 (Baja): T4

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{8} + \frac{3}{15} + \frac{4}{20}  + \frac{6}{22} = 0.125 + 0.20 + 0.20 + 0.2727 = \mathbf{0.7977}$$

- Test de Garantía Inicial: Como $$\(U  \leq 1\)$$, el sistema cumple la condicion de suficiencia de tiempo de CPU.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(8,15,20, 22)=\mathbf{1320}\)$$

04. Periodo Secundario o Tamaño de Trama (f\)\
Para determinar el tamaño del frame (f\), se deben cumplir tres condiciones fundamentales:

 a. $$f \geq \max(1,3,4,6) \implies f \geq 6\$$\
 b. Para que se cumpla la restriccion de T1 ($$D_1=8$$) evaluamos el divisor f = 8:
 
   - T1: $$\(2(8) - \text{mcd}(8, 8) = 16 - 8 = 8 \leq 8\)$$ (Cumple)
   - T2: $$\(2(8) - \text{mcd}(15, 8) = 16 - 1 = 15 \leq 15\)$$ (Cumple)
   - T3: $$\(2(8) - \text{mcd}(20, 8) = 16 - 4 = 12 \leq 12\)$$ (Cumple)
   - T4: $$\(2(8) - \text{mcd}(22, 8) = 16 - 2 = 14 \leq 14\)$$ (Cumple)
   - 1320 (mod 8) = 0 (Cumple)

El tamaño de trama seleccionado es $$f = 8$$
   
05. Cronograma y Diagrama de Gantt

  - [0-1]: Ejecuta T1 completa rafaga de 1
  - [1-4]: Ejecuta T2 completa rafaga de 3
  - [4-8]: Ejecuta T3 completa rafaga de 4
  - [8-12]: en t = 8 se reactiva T1


|Marco  |   M1  |  M2 | M3 | M4 | M5 | M6 |
| :----- | :--:| :--:| :--:|:--:|:--:|:--:|
|Tiempo  |0  --  4|    -- 8 |  -- 12|  -- 16  | --20 |   --24|
|T1  C=1    | x  |    | x  |   | x  |   |
|T2   C=3     | xxx  |    |   | x  | xx  |   |
|T3  C=4      |  | xxxx   |   |   |   | xx  |
|T4  C=6     |  |    | xx  | xx  |   |  xx |
|Ocio (-)     |  |    | -  | -  | -  |   |






## Sistema 4
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  2  | 6    |
|T2      | 2  |  8  |
|T3      | 4  | 12   |
|T4      | 4 | 24   |

01. Hay que asignar las Prioridades (Rate Monotonic).\
Las prioridades se asignan inversamente proporcionales a sus periodos \(T\)

- Prioridad 1 - T1
- Prioridad 2 - T2
- Prioridad 3 - T3
- Prioridad 4 - T4

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{2}{6} + \frac{2}{8} + \frac{4}{12}  + \frac{4}{24} = 0.3333 + 0.2500 + 0.3333 + 0.1667 = \mathbf{1.0833}$$

- Test de Garantía Inicial: Como $$\(U  \leq 1\)$$, el sistema NO CUMPLE la condicion de suficiencia de tiempo de CPU, ya que es estrictamente mayor que 1 (100%).


- El sistema 4 NO es factible (No planificable)



## Describir configuración de FreeRTOS para cumplir con Cyclic Scheduling.

- Debemos de poner los siguientes valores en 0 para que freeRTOs se vuelva estrictamente cooperativo en el archivo FreeRTOSConfig.h (ninguna tarea se ejecutara a menois que la tarea anterior termnine voluntariamente o el planificador lo decida)

/* Desactiva la expropiación automática */

#define configUSE_PREEMPTION                      0 

/* Desactiva el reparto de tiempo entre tareas de igual prioridad */

#define configUSE_TIME_SLICING                    0



