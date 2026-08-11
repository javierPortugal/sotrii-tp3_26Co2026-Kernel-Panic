# sotrii-tp3_01-cyclic
#### Planificar cada uno de los siguientes sistemas de tareas periódicas ejecutadas por un Cyclic Scheduling. Asignar prioridades. Determinar Factor de Uso, Hiperperiodo, Período Secundario. Desarrollar el Test de Garantía correspondiente a lo planificado. Dibujar el Diagrama de Gantt de lo planificado.

## Sistema 1
|Tarea |   C  |  T = D  |
| :----- | :--------------------- | :------: | 
|T1     |  1  | 4    |
|T2      | 2  |  5   |
|T3      | 5  | 2    |

01. Hay que asignar las Prioridades (Rate Monotonic).\
Las prioridades se asignan inversamente proporcionales a sus periodos \(T\)

- Prioridad 1 (Alta): T1\
- Prioridad 2 (Media): T2\
- Prioridad 3 (Baja): T3

02. Factor de Uso

$$U = \sum \frac{C_i}{T_i} = \frac{1}{4} + \frac{2}{5} + \frac{5}{20} = 0.25 + 0.40 + 0.25 = \mathbf{0.90}$$

- Test de Garantía Inicial: Como \(U = 0.90 \leq 1\), el sistema es potencialmente planificable.

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

Como ningún frame entero satisface las tres condiciones de manera directa debido al gran tamaño de \(C_3 = 5\), se requiere dividir la tarea T3 en sub-tareas más pequeñas. Dividimos T3 en tres partes: $$T_3a$$ (C=2), $$T_3b$$ (C=2)\) y $$T_3c$$ (C=1).
- Nuevo $$\max(C_i) = 2\$$.
- Seleccionamos \(f = 2\) (divisor de 20):
   - T1: $$\(2(2) - \text{mcd}(4, 2) = 2 \leq 4\)$$ (Cumple)
   - T2: $$\(2(2) - \text{mcd}(5, 2) = 3 \leq 5\)$$ (Cumple)
   
05. Cronograma y Diagrama de Gantt (Ciclo de 0 a 20)Con \(f = 2\), hay 10 frames en el hiperperiodo. Las subtareas de T3 se distribuyen en los espacios libres:
  - Frame 1 [0-2]: Ejecuta T1 (1) y T2 (1)
  - Frame 2 [2-4]: Ejecuta T2 (1) y $$T_3a$$ (1)
  - Frame 3 [4-6]: Ejecuta T1 (1) y $$T_3a$$ (restante 1)
  - Frame 4 [6-8]: Ejecuta T2 (2)
  - Frame 5 [8-10]: Ejecuta T1 (1) y $$T_3b$$ (1)
  - Frame 6 [10-12]: Ejecuta T2 (2)
  - Frame 7 [12-14]: Ejecuta T1 (1) y $$T_3b$$ (restante 1)
  - Frame 8 [14-16]: Ejecuta T2 (2)
  - Frame 9 [16-18]: Ejecuta T1 (1) y $$T_3c$$ (1)
  - Frame 10 [18-20]: Ejecuta T2 (2)
