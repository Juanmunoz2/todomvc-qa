# Pruebas manuales del portal React de TodoMVC

Proyecto de QA Engineering: análisis de requisitos, diseño y ejecución de casos de prueba manuales sobre la aplicación TodoMVC.



## 1\. Información general

* **Nombre del proyecto:** Pruebas manuales en TodoMVC
* **Fuente del proyecto:** app de práctica de código abierto (lista de tareas)
* **Link a la fuente original:**

  * App a testear: https://todomvc.com/examples/react/dist/#/
  * Especificación usada como requisitos: https://github.com/tastejs/todomvc/blob/master/app-spec.md

## 

## 2\. Objetivo

Verificar que las funciones básicas de una lista de tareas (agregar, completar, editar, filtrar y borrar) funcionen como describe la especificación de TodoMVC.

**Riesgo que se busca prevenir:** que una persona pierda tareas o vea un estado incorrecto, por ejemplo una tarea completada que aparece como pendiente, o tareas que desaparecen al recargar la página.



## 3\. Plan de trabajo

* \[x] **1. Exploración inicial (análisis de requisitos):** usar la app y leer la especificación para extraer los requisitos (ver sección 6).
* \[x] **2. Preparación (diseño de casos de prueba):** escribir casos de prueba vinculados a cada requisito.
* \[x] **3. Construcción (ejecución de pruebas):** ejecutar cada caso a mano y registrar el resultado real.
* \[x] **4. Evaluación:** calcular la cobertura de requisitos y reportar los bugs encontrados.





## 4\. Preguntas clave

Preguntas para hacerme antes de dar el proyecto por terminado:

1. ¿Qué pasaría si un bug hace que las tareas se pierdan al recargar la página en producción?
2. ¿Cada requisito de la especificación tiene al menos un caso de prueba?
3. ¿Los bugs encontrados están descritos de forma que otra persona pueda reproducirlos sin preguntarme nada?

\---

## 5\. Qué se hizo y cómo

* **Tipos de pruebas aplicadas:** pruebas funcionales manuales basadas en requisitos y pruebas exploratorias. 
* **Herramientas usadas:** navegador web y sus herramientas de desarrollo (en este caso Google Chrome)
* **Criterio de aceptación:** un caso se considera **Aprobado** si el resultado real coincide con el resultado esperado; si no coincide, es **NO APROBADO** y se reporta como bug.

## 

## 6\. Resultados

### 6.1 Requisitos



1. sin tareas, la lista y el pie de página están ocultos.

Al abrir la app por primera vez solo debes ver el campo para escribir. No deben verse la flecha de “marcar todas”, el contador ni los filtros. Aparecen al agregar la primera tarea y desaparecen al borrar la última.



2\. el campo de texto tiene el foco al cargar.

Al abrir la página puedes escribir de inmediato, sin hacer clic en el campo.



3\. Enter crea la tarea.

Escribes algo, presionas Enter y la tarea aparece en la lista. El campo queda vacío, listo para la siguiente.



4\. Se recortan los espacios y no se crean tareas vacías.

Si escribes “ Estudiar “ (con espacios a los lados), se guarda como “Estudiar”. Si dejas el campo vacío o escribes solo espacios y presionas Enter, no pasa nada.



5\. La casilla marca la tarea como completada.

Cada tarea tiene una casilla a la izquierda. Al marcarla, el texto se tacha. Al desmarcarla, la tarea vuelve a estar activa.



6\. Doble clic para editar.

Haces doble clic sobre el texto de una tarea y se convierte en un campo editable con el texto actual.



7\. Botón para eliminar al pasar el mouse.

La X (a la derecha de la tarea) solo aparece cuando pones el mouse encima. Al hacer clic, la tarea se borra.



8\. Cómo se guarda una edición.

Cuando editas, el cambio se guarda de dos formas: presionando Enter o haciendo clic fuera del campo. El texto también se recorta, igual que en R-04. Si borras todo el texto y confirmas, la tarea se elimina.



9\. Al presionar Esc se cancela la edición.

Si empiezas a editar, cambias el texto y presionas Esc, la tarea mantiene su texto original.



10\. El contador de pendientes.

Abajo a la izquierda aparece cuántas tareas faltan por completar, con el plural correcto: “0 items left”, “1 item left” y “2 items left”. Fíjate en que con una sola tarea dice “item” y no “items”.



11\. Marcar todas.

La flecha a la izquierda del campo de texto marca todas las tareas como completadas de una vez. Si ya están todas completadas, al hacer clic las deja todas activas.



12\. La flecha de “marcar todas” se mantiene sincronizada.

Si marcas una por una todas las tareas, esa flecha se marca sola. Si luego desmarcas una, la flecha también se desmarca. Después de usar “Clear completed”, debe quedar desmarcada.



13\. Filtro “Clear completed”.

Es el botón de abajo a la derecha. Borra solo las tareas completadas y deja las activas. Si no hay ninguna completada, el botón no se ve.



14\. Las tareas se guardan.

Si recargas la página (F5), las tareas siguen ahí con su estado (activas o completadas). En cambio, si recargas mientras estás editando una tarea, la edición no se guarda y la tarea vuelve a verse normal.



15\. Filtros y rutas.

Abajo hay tres filtros: All (todas), Active (pendientes) y Completed (completadas). Cada uno cambia la dirección de la página (#/, #/active y #/completed) y el filtro en uso aparece resaltado.



16\. La lista se actualiza con el filtro activo.

Si estás en el filtro Active y marcas una tarea como completada, esa tarea debe desaparecer de la vista, porque ya no es activa.



17\. El filtro se mantiene al recargar.

Si estás en el filtro Completed y recargas la página, sigues viendo el filtro Completed y no vuelves a All.



### 6.2 Casos de prueba 

ID	CASO

CS-01	Agregar un texto en el campo de texto y luego presionar la tecla Enter

CS-02	Presionar Enter con el campo de texto vacío

CS-03	Agregar texto en el campo de texto con espacios a los lados

CS-04	Agregar espacios como texto en el campo de texto

CS-05	Empezar a agregar una tarea desde el campo de texto

CS-06	Ingresar a la pagina sin visualizar otras interfaces

CS-07	Marcar una tarea agregada como completada

CS-08	Desmarcar una tarea completada

CS-09	Hacer doble clic en el titulo de una tarea agregada

CS-10	Guardar el titulo de una tarea agregada al presionar el boton Enter

CS-11	Guardar el titulo de una tarea agregada al hacer clic fuera del campo del texto editado

CS-12	"

Editar dejando el campo de texto vacio de una tarea agregada"

CS-13	"

Editar el titulo de una tarea agregada y presionar la tecla esc"

CS-14	Pasar el mouse sobre una tarea y hacer clic en la X

CS-15	Revisar el contador con 0, 1 y 2 tareas pendientes

CS-16	Usar la flecha de "marcar todas" las tareas a la vez

CS-17	Marcar y desmarcar una por una todas las tareas de una lista 

CS-18	Usar "Clear completed" y revisar si las tareas no completadas estan en la lista

CS-19	Recargar la pagina  con tareas activas y completadas

CS-20	Usar los filtros All, Active y Completed que aparecen en la pagina 

CS-21	Con el filtro Active, marcar una tarea agregada

CS-22	Recargar la pagina estando en el filtro Completed

CS-23	Entrar a editar una tarea y recargar sin guardar el texto



\---

## 7\. Conclusiones

* **Qué aprendí:** a convertir una especificación en requisitos, a diseñar casos de prueba vinculados a cada uno y a medir la cobertura. También aprendí a distinguir un bug de sus consecuencias: un solo problema (la persistencia al recargar) afectó tres casos, así que lo reporté como un único bug y marqué los otros dos casos como bloqueados.
* **Qué mejoraría con más tiempo o recursos:** repetir las pruebas fallidas en otra implementación y otro navegador para confirmar el origen de los bugs, probar en celular y automatizar los casos más repetitivos (agregar, editar y borrar tareas).
* **Qué mencionaría en una entrevista:** que cada caso está vinculado a un requisito (trazabilidad), que reporté dos bugs con pasos reproducibles y evidencia, y que supe separar un bug de los casos que quedaron bloqueados por él.



## 

