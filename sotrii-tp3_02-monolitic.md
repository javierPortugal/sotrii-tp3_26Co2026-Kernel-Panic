

###Planificar cada uno de los siguientes sistemas de tareas periódicas ejecutadas por un Rate Monolitic Scheduling. Asignar prioridades. Determinar Factor de Uso, Hiperperiodo, Período Secundario. Desarrollar el Test de Garantía correspondiente a lo planificado. Dibujar el Diagrama de Gantt de lo planificado.



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

