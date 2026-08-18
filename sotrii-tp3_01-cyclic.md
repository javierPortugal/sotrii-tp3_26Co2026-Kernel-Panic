# sotrii-tp3_01-cyclic
#### Planificar cada uno de los siguientes sistemas de tareas periódicas ejecutadas por un Cyclic Scheduling. Asignar prioridades. Determinar Factor de Uso, Hiperperiodo, Período Secundario. Desarrollar el Test de Garantía correspondiente a lo planificado. Dibujar el Diagrama de Gantt de lo planificado.

## Sistema 1
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 4    |
|T2      | 2  |  5   |
|T3      | 5  | 20   |



02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{4} + \frac{2}{5} + \frac{5}{20} = 0.25 + 0.40 + 0.25 = \mathbf{0.90}$$

- Test de Garantía Inicial: Como $$\(U = 0.90 \leq 1\)$$, el sistema es potencialmente planificable.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(4,5,20)=\mathbf{20}\$$

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

![image alt](https://github.com/javierPortugal/sotrii-tp3_26Co2026-Kernel-Panic/blob/f6bb51b3feadc966a7daeb2733fc077df72d0f84/gantt_sistema_1_ciclico.png)




## Sistema 2
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 6    |
|T2      | 2  |  10  |
|T3      | 2  | 18   |



02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{6} + \frac{2}{10} + \frac{2}{18} = 0.1667 + 0.20 + 0.1111 = \mathbf{0.4778}$$

- Test de Garantía Inicial: Como $$\(U = 0.4778 \leq 1\)$$, el sistema es planificable.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(6,10,18)=\mathbf{90}\$$

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


  - Marco 0: T1(inst 0: 0-1)
  - Marco 1: T2(inst 0: 0-2)
  - Marco 2: T3(inst 0: 0-2)
  - Marco 3: T1(inst 1: 0-1)
  - Marco 4: (vacio)
  - Marco 5: T2(inst 1: 0-2)
  - Marco 6: T1(inst 2: 0-1)
  - Marco 7: (vacio)
  - Marco 8: (vacio)
  - Marco 9: T1(inst 3: 0-1)
  - Marco 10: T2(inst 2: 0-2)
  - Marco 11: T3(inst 1: 0-2)
  - Marco 12: T1(inst 4: 0-1)
  - Marco 13: (vacio)
  - Marco 14: (vacio)
  - Marco 15: T1(inst 5: 0-1)
  - Marco 16: T2(inst 3: 0-2)
  - Marco 17: (vacio)
  - Marco 18: T1(inst 6: 0-1)
  - Marco 19: T3(inst 2: 0-2)
  - Marco 20: T2(inst 4: 0-2)
  - Marco 21: T1(inst 7: 0-1)
  - Marco 22: (vacio)
  - Marco 23: (vacio)
  - Marco 24: T1(inst 8: 0-1)
  - Marco 25: T2(inst 5: 0-2)
  - Marco 26: (vacio)
  - Marco 27: T1(inst 9: 0-1)
  - Marco 28: T3(inst 3: 0-2)
  - Marco 29: (vacio)
  - Marco 30: T1(inst 10: 0-1)
  - Marco 31: T2(inst 6: 0-2)
  - Marco 32: (vacio)
  - Marco 33: T1(inst 11: 0-1)
  - Marco 34: (vacio)
  - Marco 35: T2(inst 7: 0-2)
  - Marco 36: T1(inst 12: 0-1)
  - Marco 37: T3(inst 4: 0-2)
  - Marco 38: (vacio)
  - Marco 39: T1(inst 13: 0-1)
  - Marco 40: T2(inst 8: 0-2)
  - Marco 41: (vacio)
  - Marco 42: T1(inst 14: 0-1)
  - Marco 43: (vacio)
  - Marco 44: (vacio)

Diagrama de Gantt

![image alt]( https://github.com/javierPortugal/sotrii-tp3_26Co2026-Kernel-Panic/blob/6aa94267706c7d6f302177348ba4042cfe237933/gantt_sistema_2_ciclico.png)



## Sistema 3
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 8    |
|T2      | 3  |  15  |
|T3      | 4  | 20   |
|T4      | 6 | 22   |



02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{8} + \frac{3}{15} + \frac{4}{20}  + \frac{6}{22} = 0.125 + 0.20 + 0.20 + 0.2727 = \mathbf{0.7977}$$

- Test de Garantía Inicial: Como $$\(U = 0.7977 \leq 1\)$$, el sistema cumple la condicion de suficiencia de tiempo de CPU.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(8,15,20, 22)=\mathbf{1320}\$$

04. Periodo Secundario o Tamaño de Trama (f\)\

El tamaño de trama seleccionado es $$f = 1$$
   
05. Cronograma y Diagrama de Gantt

    ![image alt](https://github.com/javierPortugal/sotrii-tp3_26Co2026-Kernel-Panic/blob/58833e5c317d880a8b321c74a40149de7e901ef5/gantt_sistema_3_ciclico.png)






## Sistema 4
|Tarea |   C  |  T = D  |
| :----- | :---------- | :------: |  
|T1      | 0.500 |  4  | 
|T2      | 1     |  5  |
|T3      | 2     | 10  |
|T4      | 9     | 24  |



02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{0.5}{4} + \frac{1}{5} + \frac{2}{10}  + \frac{9}{24} = 0.125 + 0.200 + 0.200 + 0.375 = \mathbf{0.900}$$

- Test de Garantía Inicial: Como $$\(U = 0.90 \leq 1\)$$, el sistema cumple la condicion de suficiencia de capacidad de procesamiento para ser planificable.

03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(4,5,10,24)=\mathbf{120}\$$

04. Periodo Secundario o Tamaño de Trama (f\)\

El tamaño de trama seleccionado es $$f = 1$$
   
05. Cronograma y Diagrama de Gantt

    ![image alt](https://github.com/javierPortugal/sotrii-tp3_26Co2026-Kernel-Panic/blob/1d85754bbe96c5cd063f35eaef37c645d65f5943/gannt_sistema_4_ciclico.png)



## Describir configuración de FreeRTOS para cumplir con Cyclic Scheduling.

/* Desactiva la expropiación automática */

#define configUSE_PREEMPTION                      0 

// utilizar taskYIELD() cuando las tareas terminen



