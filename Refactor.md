Mejorar el diseño del código sin cambiar su comportamiento. Solo es posible sin miedo gracias a que tienes pruebas (TDD) que te avisan si rompes algo

- **Definición:** Es un ==cambio en la estructura interna del software== para hacerlo más fácil de entender y más barato de modificar, ==**sin cambiar su comportamiento observable** .==
    
- **El objetivo:** Luchar contra la "entropía del software" (deuda técnica). No es añadir funcionalidad, es mantenimiento preventivo
Regla de tres
- primero hazlo
- Hazlo de nuevo, mal, pero se tolera
- Refactor, hazlo bien 
Es importante a largo plazo, te solventa la deuda técnica y terminas con un código que se puede modificar fácilmente

**Los Dos Sombreros (The Two Hats):**
==Nunca debes refactorizar y añadir funcionalidad a la vez.== O tienes puesto el sombrero de "Añadir función" (tests rotos, código sucio permitido) o el de "Refactorizar" (tests verdes, limpieza), pero no ambos.

## [[Bad smells]]
Son posibles casos en los que haya que aplicar un refactor


