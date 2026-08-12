
# sotrii-tp3_02-monolitic
#### Planificar cada uno de los siguientes sistemas de tareas periódicas ejecutadas por un Rate Monolitic Scheduling. Asignar prioridades. Determinar Factor de Uso, Hiperperiodo, Período Secundario. Desarrollar el Test de Garantía correspondiente a lo planificado. Dibujar el Diagrama de Gantt de lo planificado.



## Sistema 1

01. Hay que asignar las Prioridades.
 
- Las prioridades se asignan de acuerdo al criterio: Menor periodo = Mayor prioridad
- Prioridad 1  T1
- Prioridad 2  T2
- Prioridad 3  T3

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{4} + \frac{2}{5} + \frac{5}{20} = 0.25 + 0.40 + 0.25 = \mathbf{0.90}$$


03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(4,5,20)=\mathbf{20}\$$

04. Periodo Secundario o Tamaño de Trama (f\)\ : 5
Para el enfoque ciclico equivalente con fragmentacion

Test de Garantía RMS: Como $$\(U = 0.90 \gt 0.78\)$$, analizamos el analisis de tiempo de respuesta (RTA)
- $$R_1 = 1 \leq 4 (Correcto) $$
- $$R_2 = 2 + [3/4] x 1 = 3 \leq 5 (Correcto)$$
- $$R_3 = 5 + [15/4] x 1 + [15/5] x 2 = 15 \leq 20 (Correcto)$$

El sistema es totalmente Planificable

05. Diagrama de Gantt

|Tiempo  |0  -  1|  - 2 |  - 3|  - 4|  - 5|  - 6| -7|-8|-9|-10|-11|-12|-13|-14|-15|-16|-17|
| :----- | :--:| :--:| :--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|T1     | T1  |    |  |   | T1|  |  |  | T1  |  |  |  |  T1|  |  |  | T1 |
|T2     |   |  T2  |  T2 |  |   | T2 | T2 |  |  |  |T2 | T2  |  |  |  | T2 |  |
|T3     |   |   |   |  T3 |   |   |  | T3 |  | T3 |  |  |  | T3 | T3  |  |  |
|Ocio (-) |  | |  |   |   |  |  |  |  |  |  |  |  |  |  |  |  |


## Sistema 2

01. Hay que asignar las Prioridades.
 
- Las prioridades se asignan de acuerdo al criterio: Menor periodo = Mayor prioridad
- Prioridad 1  T1
- Prioridad 2  T2
- Prioridad 3  T3

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{6} + \frac{2}{10} + \frac{2}{18} = 0.1667 + 0.2000 + 0.1111 = \mathbf{0.4778}$$


03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(6,10,18)=\mathbf{90}\$$

04. Periodo Secundario o Tamaño de Trama (f\)\ : 3
Para el enfoque ciclico equivalente con fragmentacion

Test de Garantía RMS: Como $$\(U = 0.4778 \leq 0.78\)$$, analizamos el analisis de tiempo de respuesta (RTA)

El sistema es automaticamente Planificable

05. Diagrama de Gantt

|Tiempo  |0  -  1|  - 2 |  - 3|  - 4|  - 5|  - 6| -7|-8|-9|-10|-11|-12|-13|-14|-15|-16|-17|
| :----- | :--:| :--:| :--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|T1     | T1  |    |  |   | |  | T1 |  |   |  |  |  |  T1|  |  |  |  |
|T2     |   |  T2  |  T2 |  |   |  |  |  |  |T2 |T2 |  |  |  |  |  |  |
|T3     |   |   |   |  T3 |T3  |   |  | T3 |  | T3 |  |  |  | T3 | T3  |  |  |
|Ocio (-) |  | |  |   |   | -  |  | - | - |  -|  |  |  | - | - | - |-  |





## Sistema 3

01. Hay que asignar las Prioridades.
 
- Las prioridades se asignan de acuerdo al criterio: Menor periodo = Mayor prioridad
- Prioridad 1  T1
- Prioridad 2  T2
- Prioridad 3  T3
- Prioridad 4  T4

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{8} + \frac{3}{15} + \frac{4}{20} + \frac{6}{22} = 0.125 + 0.2000 + 0.2000 + 0.2727 = \mathbf{0.7977}$$


03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(8,15,20, 22)=\mathbf{1320}\$$

04. Periodo Secundario o Tamaño de Trama (f\)\ : 4
Para el enfoque ciclico equivalente con fragmentacion

Test de Garantía RMS: Como $$\(U = 0.7977 \leq 0.756\)$$, analizamos el analisis de tiempo de respuesta (RTA)

El sistema es totalmente Planificable

05. Diagrama de Gantt

|Tiempo  |0  -  1|  - 2 |  - 3|  - 4|  - 5|  - 6| -7|-8|-9|-10|-11|-12|-13|-14|-15|-16|-17|
| :----- | :--:| :--:| :--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|T1     | T1  |    |  |   | |  |  |  |  T1 |  |  |  |  |  |  |  | T1  |
|T2     |   |  T2  |  T2 | T2 |   |  |  |  |  |   |   |  |  |  |  | T2 |  |
|T3     |   |   |   |   |T3  | T3  | T3 | T3 |  |  |  |  |  |    |     |  |  |
|T4     |   |   |   |   |   |   |  |  |  | T4 |T4 | T4 | T4 | T4 | T4  |  |  |
|Ocio (-) |  | |  |   |   |   |  |  |  |  |  |  |  |  |  |  |  |




## Sistema 4

01. Hay que asignar las Prioridades.
 
- Las prioridades se asignan de acuerdo al criterio: Menor periodo = Mayor prioridad
- Prioridad 1  T1
- Prioridad 2  T2
- Prioridad 3  T3
- Prioridad 4  T4

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{0.5}{4} + \frac{1}{5} + \frac{2}{10} + \frac{9}{24} = 0.125 + 0.2000 + 0.2000 + 0.375 = \mathbf{0.90}$$


03. Hiperperiodo (H\)
El periodo mayor o ciclo mayor es el mínimo común múltiplo de los periodos:

$$H=\text{mcm}(4,5,10,24)=\mathbf{120}\$$

04. Periodo Secundario o Tamaño de Trama (f\)\ : 2
Para el enfoque ciclico equivalente con fragmentacion

Test de Garantía RMS: Como $$\(U = 0.90 \gt 0.756\)$$, analizamos el analisis de tiempo de respuesta (RTA)

El sistema es totalmente Planificable

05. Diagrama de Gantt

|Tiempo  |0  -  1|  - 2 |  - 3|  - 4|  - 5|  - 6| -7|-8|-9|-10|-11|-12|-13|-14|-15|-16|-17|
| :----- | :--:| :--:| :--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|T1     | T1  |    |  |   | T1|  |  |  |  T1 |  |  |  | T1 |  |  |  | T1  |
|T2     |  0.5 |  T2  |    |   |   | T2 |  |  |  |   | T2  |  |  |  |  | T2 |  |
|T3     |   |  0.5 | T3  | T3  |  |   |  |  |  |  |  | T3 | T3 |    |     |  |  |
|T4     |   |   |   | 0.5 | 0.5  | 0.5  | T4 | T4 | 0.5 | T4 |  |   | 0.5 | T4 | T4  | 0.5 |  0.5|
|Ocio (-) |  | |  |   |   |   |  |  |  |  |  |  |  |  |  |  |  |

