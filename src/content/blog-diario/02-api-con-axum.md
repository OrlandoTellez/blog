---
titulo: Desarrollando api con Axum
fecha: 21/12/2025
dia: día 2
descripcionPrevia: Hoy me enfoqué en prácticar el desarrollo de API con Axum(Rust).
layout: "../../layouts/PlantillaArticulos.astro"
---

# Desarrollando api con axum(Framework backend de Rust)

#### Fecha: 21 de diciembre del 2025

El día de hoy me quise divertir un rato, por cierto estoy seguro que no lo he comentado antes, pero estoy en un curso de rust, lo estoy aprendiendo a profundidad, quiero realmente entender como funciona y ser experto en rust, creo que voy bien encaminado, voy agarrandole el ritmo a los cursos que estoy viendo, ya he visto lo que son los tipos de datos, las condicionales, los ciclos, las funciones, el ownership, borrowing, punteros, referencias, crates, traits, macros... todos esos conceptos ya poco a poco los voy asimilando y se me están quedando y los veo ya en mi día a día como desarrollador.

Resulta que estos días estoy programando las apis con Axum, que es un framework de rust, es bastante rápido y me gusta la sensación de estar escribiendo código y al mismo tiempo entenderlo, realemente pienso que me ha estado ayudando a consolidar las bases porque me obliga a entender mucho mejor como funcionan las cosas, osea ya sé que hay lenguajes que abstraen menos la lógica, pero para subir de nivel no es necesario empezar por lo más dificil. Ya tengo mucha experiencia en el stack de JavaScript, realmente nodeJs me gusta mucho, pero desde que estoy con Rust siempre he querido sacarlo provecho al lenguaje y todo lo que me ofrece, entonces ahi fue donde descubrí axum, estuve leyendo la documentación para ver como era, intente aplicar una arquitectura de modelo-vista-controlador solo que sin las vistas porque mi intención es hacerlas con React, ese es otro dato sobre mí, soy React Developer, ya estoy muy acostumbrado y es mi zona segura en el desarrollo, frameworks como astro también me gustan, aunque prácticamente si se sabe HTML, CSS Y JAVASCRIPT se sabe astro.

Pero bueno, como estaba diciendo, axum me ha ayudado a entender mejor las cosas, y realmente me aporta mucho en conocimiento, he visto como crear un servidor, crear las rutas, usar los controladores, crear modelos, hacer validaciones, y pues aún tengo pendiente los servicios e implementación con la base de datos, eso en los próximos días lo estaré documentando.

## Programación Estructurada, Concurrente y paralela

He reforzado el día de hoy lo que son conceptos que están presentes en el día a día de un programador pero que no se suelen dar enfasis en aprenderlos a profundidad, en esta caso me refiero a la programación estructurada y la programación concurrente y paralela. Entenderlo es importante para saber que hay muchas otras formas de trabajar en la programación, hay muchas técnicas que se podrían implementar dependiendo el caso.

No es nada del otro mundo, pero ahora si me preguntan ya podría dar una respuesta con una base consolidada.

Básicamente la programación estructurada es aquella en la que las tareas se hacen de manera secuencial, una detrás de otra, es decir, tarea B no puede ejecutarse si tarea A no se ha ejecutado antes. Este es un paradigma de programación y su enfoque es ser secuencial a no ser que se especifique lo contrario en el código, pero en esencial eso es. Pero esto realmente no es nada del otro mundo.

Pero ahora si viene lo intereseante, la programación concurrente y paralela, quiero comenzar con la concurrente, esta es aquella en donde las tareas se ejecutan simultaneamente de manera tan rápida que parece que se hacen al mismo tiempo, sin embargo aquí está el truco, cuando un programa está ejecutándose y realizando varias tareas, lo que sucede es que por periodos muy imperceptibles de tiempo se van alternando entre las tareas hasta que se terminen, es decir, es como si un programador este en el backend, en el frontend, en la base de datos y en el diseño de una página al mismo tiempo, solo que por milisegundos va alternando y avanzando en cada tarea hasta que las termina todas, esto sucede tan rápido que da la sensación de que es instantaneo. Una frase muy acertada sería "Manejar muchas cosas a la vez".

En cambio, la programación paralela es literalmente hacer todo al mismo tiempo fisico, es decir, tarea A empieza al mismo tiempo que tarea B, no se van alternando entre tareas, sino que se realizan de manera paralela al mismo tiempo, para ellos se aprovecha los núcleos del cpu físico, en mi caso mi procesador i3-12100 tiene 8 núcleos, entonces el núcleo 1 ejecuta tarea A, y núcleo 7 ejecuta tarea B, todo al mismo tiempo. Una frase asertada sería "Hacer muchas cosas a la vez"

Ahora bien, hay definiciones más técnicas que esta, sin embargo no hay necesidad de profundizar tanto en un blog diario, ya tengo planeado hacer artículos más especializados explicando más a detalle, acordemonos que el propósito del blog es documentar todo lo que hago en el día y todo lo que voy aprendiendo, así que es normal que me confunda en alguna que otra cosa.
