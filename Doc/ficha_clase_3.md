# Ficha de trabajo – Clase 3

## Identificación

- **Nombre:** Alessandro Dini
- **Sección:** COMPLETAR
- **Fecha:** 19/08/2026
- **Compañero(a) de trabajo:** Germán Rojas
- **Repositorio individual:** poos-p13c3-alessDini

# Parte 0. Punto de partida validado

Este caso representa el **mínimo esperado al finalizar la Clase 2**. Se utilizará como evidencia común para comenzar el diseño orientado a objetos. No reemplaza la entrega individual de la ficha anterior.

## Funcionalidad

Captura básica de una criatura.

## Actor principal

Entrenador.

## Necesidad

Capturar una criatura salvaje disponible utilizando una cápsula de su inventario.

## Entradas

- Criatura seleccionada.
- Disponibilidad de la criatura.
- Distancia entre el entrenador y la criatura.
- Cantidad de cápsulas.
- Probabilidad de captura.

## Proceso

1. Verificar que la criatura esté disponible.
2. Verificar que se encuentre dentro de la distancia permitida.
3. Verificar que el entrenador tenga cápsulas.
4. Consumir una cápsula.
5. Determinar si la captura tiene éxito.
6. Registrar la criatura si la captura es exitosa.
7. Informar el resultado.

## Salidas

- Captura exitosa.
- Captura fallida.
- Mensaje de rechazo por criatura no disponible.
- Mensaje de rechazo por distancia.
- Mensaje de rechazo por falta de cápsulas.
- Cantidad actualizada de cápsulas.

## Reglas

- Solo se puede intentar capturar una criatura por operación.
- Cada intento válido consume una cápsula.
- Un intento rechazado no consume cápsulas.
- La criatura se registra únicamente si la captura tiene éxito.
- La criatura debe estar disponible y dentro de la distancia permitida.

## Dentro del alcance

- Selección de la criatura.
- Validaciones de disponibilidad, distancia e inventario.
- Consumo de la cápsula.
- Resolución del intento.
- Registro de la criatura.
- Información del resultado.

## Fuera del alcance

- GPS real.
- Combates.
- Animaciones.
- Intercambio de criaturas.
- Funciones sociales.

## Criterios de aceptación

### Criterio 1: intento sin cápsulas

- **Dado** que el entrenador no tiene cápsulas,
- **cuando** intenta capturar una criatura,
- **entonces** el sistema rechaza la acción, no modifica el inventario e informa que no hay cápsulas disponibles.

### Criterio 2: intento válido

- **Dado** que la criatura está disponible, se encuentra dentro de la distancia permitida y el entrenador tiene cápsulas,
- **cuando** realiza un intento de captura,
- **entonces** el sistema consume exactamente una cápsula, determina el resultado e informa si la captura tuvo éxito o falló.

### Criterio 3: criatura fuera de rango

- **Dado** que la criatura se encuentra fuera de la distancia permitida,
- **cuando** el entrenador intenta capturarla,
- **entonces** el sistema rechaza la acción, no consume cápsulas e informa que la criatura está fuera de rango.

### Criterio 4: captura exitosa

- **Dado** que el entrenador realiza un intento válido,
- **cuando** el resultado de la captura es exitoso,
- **entonces** la criatura se registra en su colección y el sistema informa la captura exitosa.

---


# Tarjetas de clase y responsabilidades


## Clase Plantilla

- **Nombre:** Entrenador
- **Responsabilidad principal:** Capturar pokemones
- **Atributos necesarios:** Nombre, nivel, género
- **Métodos posibles:** Lanzar pokebola, atacar con pokemón, capturar pokemón
- **Clase con la que necesita colaborar:** Criatura, Inventario
- **Regla o criterio de aceptación (justifica) :** Criterio 3, porque si es que la criatura está fuera de rango no puede intentar capturarla, y criterio 4, porque él está involucrado en la captura y si es exitosa o no le afecta directamente
- **Responsabilidad que no debería asumir:** Si la captura es exitosa o no, la capacidad máxima de pokebolas que posee

## Clase Plantilla

- **Nombre:** Criatura
- **Responsabilidad principal:** Evitar ser capturada
- **Atributos necesarios:** Elemento, nivel, tipo, rareza
- **Métodos posibles:** Huir, atacar, defenderse
- **Clase con la que necesita colaborar:** Entrenador, Inventario
- **Regla o criterio de aceptación que la justifica:** Criterio 2, ya que depende de si la criatura está disponible o no
- **Responsabilidad que no debería asumir:** Ser atacada

## Clase Plantilla

- **Nombre:** Inventario
- **Responsabilidad principal:** Almacenar pokebolas y criaturas
- **Atributos necesarios:** Capacidad máxima de objetos, tipo de objeto, cantidad de cada objeto
- **Métodos posibles:** Almacenar objetos, ordenar objetos por tipo  o cantidad, eliminar objetos, usar objetos
- **Clase con la que necesita colaborar:** Entrenador, Criatura
- **Regla o criterio de aceptación que la justifica:** Criterio 1, ya que tienen que haber pokebolas disponibles para realizar un intento de captura
- **Responsabilidad que no debería asumir:** Capturar pokemones


## Comprobación de coherencia

1. ¿Existe una clase que concentre casi todas las acciones? ¿Cuál y qué responsabilidad debería trasladarse?

   **Respuesta:** Entrenador, porque tiene conexión directa con el pokemón y el inventario, y la responsabilidad que debería trasladarse es la de almacenar objetos y criaturas en el inventario

2. ¿Existe un método en una clase que no posee los datos necesarios para realizarlo?

   **Respuesta:** COMPLETAR

Elige una de tus clases y crea dos objetos con estados distintos.

- **Clase seleccionada:** COMPLETAR

| Atributo | Objeto 1: `COMPLETAR` | Objeto 2: `COMPLETAR` |
|----------|-----------------------|-----------------------|
| COMPLETAR | COMPLETAR | COMPLETAR |
| COMPLETAR | COMPLETAR | COMPLETAR |
| COMPLETAR | COMPLETAR | COMPLETAR |

- **Método que ambos objetos pueden ejecutar:** COMPLETAR
- **¿Qué comparten por pertenecer a la misma clase?:** COMPLETAR
- **¿Qué cambia entre ambos objetos?:** COMPLETAR

---

# Trazabilidad con los criterios de aceptación

Relaciona cada comportamiento esperado con las responsabilidades propuestas.

| Criterio | ¿Qué información se necesita? | ¿Qué clase debería conocerla? | ¿Qué acción debe realizarse? | ¿Qué clase debería realizarla? |
|----------|-------------------------------|-------------------------------|------------------------------|--------------------------------|
| Sin cápsulas | COMPLETAR | COMPLETAR | COMPLETAR | COMPLETAR |
| Intento válido | COMPLETAR | COMPLETAR | COMPLETAR | COMPLETAR |
| Fuera de rango | COMPLETAR | COMPLETAR | COMPLETAR | COMPLETAR |
| Captura exitosa | COMPLETAR | COMPLETAR | COMPLETAR | COMPLETAR |

## Pregunta de análisis

¿Existe algún criterio de aceptación que no pueda cumplirse con las clases y responsabilidades propuestas?

**Respuesta y ajuste necesario:** COMPLETAR
