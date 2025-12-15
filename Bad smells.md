1. **Código Duplicado (Duplicated Code):** El olor número 1. Si ves la misma estructura en dos sitios, unifícala.
    
    - _Solución:_ `Extract Method`, `Pull Up Field`.
        
2. **Método Largo (Long Method):** Si un método ocupa más de una pantalla, es difícil de leer.
    
    - _Solución:_ `Extract Method`, `Replace Temp with Query` .
        
3. **Clase Grande (Large Class):** Una clase con demasiadas variables de instancia o demasiados métodos. Hace demasiadas cosas.
    
    - _Solución:_ `Extract Class` .
        
4. **Lista de Parámetros Larga (Long Parameter List):** Métodos con 4, 5 o más parámetros son difíciles de usar.
    
    - _Solución:_ `Introduce Parameter Object` (agrupar parámetros en un objeto) .
        
5. **Obsesión por los Primitivos (Primitive Obsession):** Usar tipos básicos (`int`, `string`) para conceptos complejos como dinero, teléfonos o rangos.
    
    - _Solución:_ `Replace Data Value with Object` .
        
6. **Grupos de Datos (Data Clumps):** Datos que siempre viajan juntos (ej: x, y, z o start_date, end_date).
    
    - _Solución:_ `Extract Class` .
        

#### Olores de Cambio (Problemas al mantener)

7. **Cambio Divergente (Divergent Change):** Cuando **una** clase se tiene que cambiar por **muchas** razones diferentes (ej: cambias la DB y tocas la clase; cambias la UI y tocas la misma clase). Viola la cohesión.
    
    - _Solución:_ `Extract Class` .
        
8. **Cirugía de Escopeta (Shotgun Surgery):** Lo opuesto al anterior. Cuando **un** cambio pequeño te obliga a tocar **muchas** clases pequeñas a la vez.
    
    - _Solución:_ `Move Method/Field` (juntar lo que cambia en un solo sitio) .
        
9. **Jerarquías de Herencia Paralelas (Parallel Inheritance Hierarchies):** Cada vez que creas una subclase de A, tienes que crear obligatoriamente una subclase de B.
    
    - _Solución:_ Mover métodos para que una jerarquía refiera a la otra y eliminar la duplicidad .
        

#### Olores de Dispensables (Cosas que sobran)

10. **Clase Perezosa (Lazy Class):** Una clase que no hace lo suficiente para justificar su existencia.
    
    - _Solución:_ `Collapse Hierarchy`, `Inline Class` .
        
11. **Generalidad Especulativa (Speculative Generality):** Código puesto "por si acaso" lo necesitamos en el futuro (YAGNI).
    
    - _Solución:_ Eliminarlo (`Collapse Hierarchy`, `Remove Parameter`) .
        
12. **Campo Temporal (Temporary Field):** Una variable de clase que solo se usa en situaciones muy específicas o solo tiene valor durante un momento.
    
    - _Solución:_ `Extract Class` para esos casos específicos .
        
13. **Comentarios (Comments):** A menudo se usan como "desodorante" para tapar código que no se entiende. Si necesitas explicar _qué_ hace el código, refactoriza para que el código se explique solo.
    
    - _Solución:_ `Extract Method` con un buen nombre .
        

### Olores de Acoplamiento (Malas relaciones)

14. **Envidia de Características (Feature Envy):** Un método de la clase A usa más datos de la clase B que de la suya propia.
    
    - _Solución:_ `Move Method` (lleva el método a donde están los datos) .
        
15. **Cadenas de Mensajes (Message Chains):** El famoso `a.getB().getC().getD().hacerAlgo()`. Si cambia la estructura, se rompe todo.
    
    - _Solución:_ `Hide Delegate` .
        
16. **Hombre Intermedio (Middle Man):** Una clase que solo delega trabajo a otra sin hacer nada útil.
    
    - _Solución:_ `Remove Middle Man` .
        
17. **Intimidad Inapropiada (Inappropriate Intimacy):** Clases que saben demasiado de los detalles privados de otras.
    
    - _Solución:_ `Move Method`, `Extract Class` .
        
18. **Clase de Datos (Data Class):** Clases que solo tienen atributos y métodos get/set, pero nada de lógica. Son "tontas".
    
    - _Solución:_ `Move Method` (mover lógica a esa clase) .
        
19. **Clases Alternativas con Interfaces Diferentes:** Dos clases hacen lo mismo pero tienen métodos con nombres distintos.
    
    - _Solución:_ `Rename Method` .
        
20. **Clase de Biblioteca Incompleta:** Necesitas algo de una librería pero no puedes modificarla.
    
    - _Solución:_ `Introduce Local Extension` .
        
21. **Sentencias Switch (Switch Statements):** Un gran `switch` o `if-else` basado en tipos. Es un síntoma de falta de polimorfismo.
    
    - _Solución:_ `Replace Conditional with Polymorphism`