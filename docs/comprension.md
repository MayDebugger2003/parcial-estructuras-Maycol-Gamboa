# Comprensión del diseño — Enunciado C
**Nombre:** Maycol Estiven Gamboa Sandoval
**Fecha:** 19/10/2026

Responde con tus palabras, basándote en `docs/UML-final.md`. Respuestas
concisas (2–4 líneas por pregunta). Evidencia que entendiste el contrato
**antes** de programar.

---

### 1. Herencia y polimorfismo
¿Por qué `Curso` es una clase abstracta y no concreta? Menciona qué método
obliga a cada subclase a implementar y qué gana el sistema con eso.

> _Tu respuesta:_Curso es abstracta porque representa un concepto general que no puede instanciarse por sí mismo.  
Cada tipo de curso (básico, avanzado, laboratorio, electiva, etc.) tiene una forma distinta de calcular su dificultad, por lo que la clase base no puede definir una implementación única.

---

### 2. Composición vs. agregación
Explica la diferencia entre `PlanEstudios ◆— Curso` (composición) y
`Facultad ◇— PlanEstudios` (agregación). ¿Qué pasaría con los cursos si se
elimina el plan? ¿Y con los planes si se elimina la facultad?

> _Tu respuesta:_En PlanEstudios ◆— Curso (composición), los cursos son creados dentro del plan y dependen completamente de él.
Si se elimina el plan, los cursos también desaparecen.

En Facultad ◇— PlanEstudios (agregación), la facultad solo almacena planes creados externamente.
Si se elimina la facultad, los planes siguen existiendo.

---

### 3. Asociación
En `Estudiante — Curso`, ¿quién es dueño de quién? ¿Por qué se modela como
N:M y no como composición?

> _Tu respuesta:_ninguno esdueño del otro porque la relación Estudiante–Curso se modela como asociación N:M, nunca como composición
 
---

### 4. Dependencia
¿Por qué `Recomendador` **depende** de `HistorialAcademico` en lugar de
**tenerlo** como atributo? ¿Qué ventaja tiene pasar el servicio como
parámetro?

> _Tu respuesta:_Recomendador depende de HistorialAcademico porque no necesita poseerlo, solo usarlo temporalmente para ejecutar la recomendación.
Pasar el servicio como parámetro evita acoplamiento innecesario, hace el código más flexible, más testeable y más reutilizable.

---

### 5. Listas
En este proyecto se usan dos estructuras distintas:
- `int[] notas` en `Estudiante`
- `ArrayList<Curso>` en `PlanEstudios` y `Estudiante`

Explica por qué en cada caso se eligió esa estructura y no la otra. ¿Qué
pasa si el estudiante intenta registrar más notas que la capacidad del
arreglo?

> _Tu respuesta:_La razón por la que el proyecto usa dos estructuras distintas (int[] y ArrayList<Curso>) es debido a que cada una resuelve un problema diferente y tiene usos diferentes según el tipo de dato y lo que se espera que haga el dato.
> Int[] sirve para en Estudiantes porque se necesitan una cantidad fijas de notas y s enecesita que le codigo sea simple
> ArrayList<Curso> en Planestudios y Estudiantes porque permite agregar una cantidad variable de cursos y permite flexibilidad y operaciones dinamicas