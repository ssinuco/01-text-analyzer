# Analizador de texto

## Índice

* [1. Consideraciones generales](#1-consideraciones-generales)
* [2. Preámbulo](#2-preámbulo)
* [3. Funcionalidades](#3-funcionalidades)
* [4. Boilerplate](#4-boilerplate)
* [5. Objetivos de aprendizaje y Criterios de aceptación mínimos del proyecto](#5-objetivos-de-aprendizaje-y-criterios-de-aceptación-mínimos-del-proyecto)
* [6. Pruebas](#6-pruebas)
* [7. Pistas, tips y lecturas complementarias](#7-pistas-tips-y-lecturas-complementarias)

***

## 1. Consideraciones generales

* Este proyecto lo resolvemos de manera **individual**.
* El rango de tiempo estimado para completar el proyecto es de 1 a 3 Sprints.
* Enfócate en aprender y no solamente en "completar" el proyecto.
* Te sugerimos que no intentes saberlo todo antes de empezar a codear.
  No te preocupes demasiado ahora por lo que _todavía_ no entiendas.
  Irás aprendiendo.

## 2. Preámbulo

Un analizador de texto es una aplicación para extraer información útil de un
texto utilizando diversas técnicas, como el procesamiento del lenguaje
natural (NLP), el aprendizaje automático (ML) y el análisis estadístico.
Estas aplicaciones pueden proporcionar una variedad de métricas que brindan
información básica sobre la longitud y la estructura del texto como por
ejemplo, el conteo de palabras, el conteo de caracteres, el conteo de
oraciones y el conteo de párrafos. Otras métricas incluyen el análisis
de sentimientos, que utiliza técnicas de NLP para determinar el tono
general positivo, negativo o neutral del texto, y el análisis de
legibilidad, que utiliza algoritmos para evaluar la complejidad y la
legibilidad del texto.

En general, las aplicaciones de análisis de texto brindan información
valiosa y métricas sobre los textos que pueden ayudar a los usuarios a
tomar decisiones informadas y sacar conclusiones significativas.
Mediante el uso de estas herramientas de análisis, los usuarios pueden
obtener una comprensión más profunda de los textos.

## 3. Funcionalidades

En este proyecto implementarás un analizador de texto web para calcular
y mostrar métricas de un texto enviado por el usuario.

El listado de funcionalidades es el siguiente:

1. La aplicación debe permitir al usuario ingresar un texto escribiéndolo
en un cuadro de texto.

2. La aplicación debe calcular las siguientes métricas y actualizar el
resultado en tiempo real a medida que el usuario escribe su texto:

    - **Recuento de palabras**: la aplicación debe poder contar el número de
    palabras en el texto de entrada y mostrar este recuento al usuario
    - **Recuento de caracteres**: la aplicación debe poder contar el número de
    caracteres en el texto de entrada, incluidos espacios y signos de
    puntuación, y mostrar este recuento al usuario.
    - **Recuento de caracteres excluyendo espacios y signos de puntuación**:
    la aplicación debe poder contar el número de caracteres en el texto de
    entrada, excluyendo espacios y signos de puntuación, y mostrar este recuento
    al usuario.  
    - **Recuento de números**: la aplicación debe contar cúantos números hay en
    el texto de entrada y mostrar este recuento al usuario.
    - **Suma total de números**: la aplicación debe sumar todos los números que
    hay en el texto de entrada y mostrar el resultado al usuario.
    - **Longitud media de las palabras**: la aplicación debe calcular la
    longitud media de las palabras en el texto de entrada y mostrársela al usuario.

3. La aplicación debe permitir limpiar el contenido de la caja de texto haciendo
clic en un botón.

![Text analyzer demo](docs/images/text-analyzer-demo.gif "Text analyzer demo")

## 4. Boilerplate

La lógica del proyecto debe estar implementada completamente en JavaScript. En
este proyecto NO está permitido usar librerías o frameworks, solo JavaScript
puro también conocido como Vanilla JavaScript.

Para comenzar este proyecto tendrás que hacer un _fork_ y _clonar_ este
repositorio que contiene un _boilerplate_ con tests (pruebas). Un _boilerplate_
es la estructura básica de un proyecto que sirve como un punto de partida con
archivos y configuración inicial de dependencias y tests.

El boilerplate que les damos contiene esta estructura:

```text
./
├── .babelrc
├── .editorconfig
├── .eslintrc
├── .gitignore
├── README.md
├── package.json
├── src
│   ├── analyzer.js
│   ├── index.html
│   ├── index.js
│   └── style.css
└── test
    ├── .eslintrc
    └── analyzer.spec.js
```

### Descripción de scripts / archivos

* `README.md`: debes modificarlo para explicar la información necesaria para el
  uso de tu aplicación
  web, así como una introducción a la aplicación, su funcionalidad y decisiones
  de diseño que tomaron.
* `.github/workflows`: esta carpeta contine la configuracion para la ejecution
  de Github Actions. No debes modificar esta carpeta ni su contenido.
* `docs/images`: contiene las imagenes de este README.
* `read-only/`: esta carpeta contiene las pruebas de criterios mínimos de
  aceptación y end-to-end. No debes modificar esta carpeta ni su contenido.
* [`src/index.html`](./src/index.html): este es el punto de entrada a tu
  aplicación. Este archivo debe contener tu HTML.
* [`src/style.css`](./src/style.css): este archivo debe contener las reglas de
  estilo. Queremos que escribas tus propias reglas, por eso NO está permitido el
  uso de frameworks de CSS (Bootstrap, Materialize, etc).
* [`src/analyzer.js`](./src/analyzer.js): acá debes implementar el objeto
  `analyzer`, el cual ya está _exportado_ en el _boilerplate_. Este objeto
  (`analyzer`) debe contener seis métodos:
  - `analyzer.getWordCount(text)`: esta función debe retornar el recuento de
  palabras que se encuentran en el parámetro `text` de tipo `string`.
  - `analyzer.getCharacterCount(text)`: esta función debe retornar el recuento
  de caracteres que se encuentran en el parámetro `text` de tipo `string`.
  - `analyzer.getCharacterCountExcludingSpaces(text)`: esta función debe retornar
  el recuento de caracteres excluyendo espacios y signos de puntuación que se
  encuentran en el parámetro `text` de tipo `string`.
  - `analyzer.getNumberCount(text)`: esta función debe retornar cúantos números
  se encuentran en el parámetro `text` de tipo `string`.
  - `analyzer.getNumberSum(text)`: esta función debe retornar la suma de todos
  los números que se encuentran en el parámetro `text` de tipo `string`.
  - `analyzer.getAverageWordLength(text)`: esta función debe retornar la longitud
  media de palabras que se encuentran en el parámetro `text` de tipo `string`.

  Para ejemplo de uso de cada función recomendamos ver el archivo
  [`test/analyzer.spec.js`](./test/analyzer.spec.js).

* [`src/index.js`](./src/index.js): acá debes escuchar eventos del DOM, invocar
  los métodos del objeto `analyzer` según sea necesario y actualizar el resultado
  en la UI (interfaz de usuario).
* [`test/analyzer.spec.js`](./test/analyzer.spec.js): este archivo contiene las
pruebas unitarias para los métodos del objeto `analyzer`.

***

#### Deploy

Hacer que los sitios estén publicados (o _desplegados_) para que usuarias de
la web puedan acceder a él es algo común en proyectos de desarrollo de software.

En este proyecto, utilizaremos _Github Pages_ para desplegar nuestro sitio web.

El comando `npm run deploy` puede ayudarte con esta tarea y también puedes
 consultar su [documentación oficial](https://docs.github.com/es/pages).

## 5. Objetivos de Aprendizaje y Criterios de aceptación mínimos del proyecto

### HTML

* **Uso de HTML semántico**

  [ ] La aplicación tiene un encabezado conformado por un
  [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)
  que es padre de un
  [`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/h1)
  con texto `Analizador de texto`. Estos elementos no pueden tener
  atributos `id`, ni `name`, ni `class`.

  [ ] La aplicación usa un
  [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
  con un el atributo `name` en el valor `user-input` para permitir al usuario
  ingresar un texto. Este elemento no pueden tener
  atributos `id`, ni `class`.

  [ ] La aplicación usa un
  [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
  con 6 hijos [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li),
  uno para mostrar cada métrica. Estos elementos no pueden
  tener atributos `id` ni `name`.

  [ ] La aplicación tiene un pie de página conformado por un
  [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)
  que es padre de un
  [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
  que tiene como texto el nombre de la estudiante desarrolladora de la aplicación.
  Estos elementos no pueden tener atributos `id`, ni `name`, ni `class`.

  [ ] La aplicación usa un
  [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
  con el atributo `id` en el valor `reset-button` para permitir al usuario,
  mediante un clic, limpiar el contenido de la caja de texto.

### CSS

* **Uso de selectores de CSS**  

  [ ] La aplicación usa
  [`selectores CSS de tipo`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors#type_selectors)
  para darle estilo al
  [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)
  y al
  [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer).
  
  [ ] La aplicación usa
  [`selectores CSS de class`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors#class_selectors)
  para darle estilo al
  [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
  descrito anteriormente.
  y sus hijos
  [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li).
  
  [ ] La aplicación usa
  [`selectores de atributo`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors)
  para darle estilo al
  [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
  usando el atributo `name`.

  [ ] La aplicación usa
  [`selectores CSS de ID`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors#id_selectors)
  para darle estilo al
  [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
  con el atributo `id` en el valor `clear-button`.

* **Modelo de caja (box model): border, margen, padding**

  [ ] Las
  [`clases css`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors#class_selectors)
  de los
  [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)
  hijos del
  [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
  definen un estilo usando las propiedades del
  [modelo de caja](https://cssreference.io/box-model/),
  ([`background`](https://cssreference.io/backgrounds/),
  `border`,
  [`margin`](https://cssreference.io/property/margin/),
  [`padding`](https://cssreference.io/property/padding/)).

### Web APIs

* **Uso de selectores del DOM**

  [ ] La aplicación usa el
  [`selector del DOM querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector).

  [ ] La aplicación usa el
  [`selector del DOM getElementById`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById).
  
* **Manejo de eventos del DOM (listeners, propagación, delegación)**

  [ ] La aplicación registra un
  [Event Listener](https://developer.mozilla.org/en/docs/Web/API/EventTarget/addEventListener)
  para escuchar el evento `keyup` del `<textarea>` para actualizar las métricas
  cuando se haga escriba en el cuadro de texto.

  [ ] La aplicación registra un
  [Event Listener](https://developer.mozilla.org/en/docs/Web/API/EventTarget/addEventListener)
  para escuchar el evento `click` del `<button>` que limpia el contenido de la
  caja de texto.

* **Manipulación dinámica del DOM**
  [ ] La aplicación actualiza el atributo
  [`textContent`](https://developer.mozilla.org/es/docs/Web/API/Node/textContent)
  o
  [`innerHTML`](https://developer.mozilla.org/es/docs/Web/API/Element/innerHTML)
  de los `<div>` que mostrar las métricas del texto.

### JavaScript

* **Tipos de datos primitivos**

  [ ] La aplicación convierte valores tipo `string` a tipo `number`.

* **Strings (cadenas de caracteres)**

  [ ] La aplicación usa métodos para manipular strings como
  [`split`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split),
  [`trim`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim)
  o
  [`replace`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace).

* **Variables (declaración, asignación, ámbito)**

  [ ] La aplicación declara variables con
  [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
  y
  [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const).

  [ ] La aplicación NO declara variables con  `var`.

* **Uso de condicionales (if-else, switch, operador ternario, lógica booleana)**

  [ ] La aplicación usa el statement
  [`if..else`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
  para evaluar condiciones.

* **Uso de bucles/ciclos (while, for, for..of)**

  [ ] La aplicación usa el statement
  [`for`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
  para crear un bucle.

* **Funciones (params, args, return)**

  [ ] El objeto `analyzer` contiene un método `getWordCount` para calcular el
  recuento de palabras de un texto.

  [ ] El objeto `analyzer` contiene un método `getCharacterCount` para calcular
  el recuento de caracteres de un texto.

  [ ] El objeto `analyzer` contiene un método `getCharacterCountExcludingSpaces`
  para calcular el recuento de caracteres excluyendo espacios y signos de
  puntuación de un texto.

  [ ] El objeto `analyzer` contiene un método `getNumbersCount` para contar
  cúantos números hay en un texto.

  [ ] El objeto `analyzer` contiene un método `getNumbersSum` para la suma
  longitud media de los números en un texto.

  [ ] El objeto `analyzer` contiene un método `getAverageWordLength` para
  calcular la longitud media de las palabras en un texto.

* **Pruebas unitarias (unit tests)**

  [ ] Se pasan todas las pruebas unitarias.

* **Módulos de ECMAScript (ES Modules)**

  [ ] La aplicación usan
  [`import`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
  y
  [`export`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
  para importar y exportar valores desde un modulo JavaScript.

* **Uso de linter (ESLINT)**

  [ ] Al ejecutar el linter no se muestran errores de formato y estilo.

* **Uso de identificadores descriptivos (Nomenclatura y Semántica)**

  [ ] En el código se utilizan identificadores descriptivos para variables
  y funciones.

### Control de Versiones (Git y GitHub)

* **GitHub: Creación de cuenta y repos, configuración de llaves SSH**

  [ ] La estudiante creó una cuenta en Github.

  [ ] La estudiante configuró su cuenta de Github con una llave SSH.

* **Git: Control de versiones con git (clone, add, commit, push)**

  [ ] La estudiante creó un _fork_ para su proyecto.

  [ ] La estudiante clonó su repositorio usando una llave SSH.

  [ ] La estudiante creó _commits_ y los guardó en Github.

* **GitHub: Despliegue con GitHub Pages**

  [ ] La aplicación está desplegada en Github Pages.

### Centrado en el usuario

* **Diseñar y desarrollar un producto o servicio poniendo a las
usuarias en el centro**

### Diseño de producto

* **Crear prototipos de alta fidelidad que incluyan interacciones**

  [ ] La estudiante creó prototipos de alta fidelidad para la UI (interfaz gŕafica).

* **Seguir los principios básicos de diseño visual**

  [ ] Se tuvieron en cuenta las reglas básica del
  [diseño visual](https://coda.io/d/Bootcamp-UX-Contenido_dqkqk2rV9Z2/Reglas-basicas-de-diseno-visual_suVcO)
  para diseñar la UI (interfáz gráfica)

## 6. Pruebas

Este proyecto cuenta con 3 conjuntos de pruebas que te ayudarán a conocer si
cumples los criterios mínimos de aceptación.

### Pruebas unitarias

Una prueba unitaria es una técnica de prueba de software en la que se comprueba
que cada componente individual de un programa o sistema funciona correctamente
de manera aislada. En otras palabras, se prueba cada unidad de código por
separado para asegurarse de que cumpla con los requisitos y especificaciones.

Las pruebas unitarias de este proyecto ejecutarán los métodos `getWordCount`,
`getCharacterCount`, `getCharacterCountExcludingSpaces`, `getNumbersCount`,
`getNumbersSum` y `getAverageWordLength` con diferentes argumentos y se
confirmará que los valores retornados sean los esperados.

Puedes ejecutar estas pruebas con el comando `npm run test` como se muestra
en la siguiente imagen:

![npm run test](docs/images/npm-run-test.gif "npm run test")

El _boilerplate_ incluye tareas que ejecutan [eslint](https://eslint.org/) y
[htmlhint](https://github.com/yaniswang/HTMLHint) para verificar el `HTML` y
`JavaScript` con respecto a una guías de estilos. Ambas tareas se ejecutan
automáticamente antes de ejecutar las pruebas unitarias cuando usamos el comando
`npm run test`. En el caso de `JavaScript` estamos usando un archivo de
configuración de `eslint` que se llama `.eslintrc` que contiene un mínimo de
información sobre el parser que usar (qué version de JavaScript/ECMAScript), el
entorno (browser en este caso) y
las [reglas recomendadas (`"eslint:recommended`)](https://eslint.org/docs/rules/).
En cuanto a reglas/guías de estilo en sí,
usaremos las recomendaciones _por defecto_ de tanto `eslint` como `htmlhint`.

### Pruebas de criterios mínimos de aceptación

Estas pruebas analizarán tus archivos
[`index.html`](src/index.html),
[`index.js`](src/index.html),
[`analyzer.js`](src/analyzer.js)
y
[`style.css`](src/style.css)
para verificar que cumples con los
[criterios minimos de aceptacion](#5-objetivos-de-aprendizaje-y-criterios-de-aceptación-mínimos-del-proyecto).
Cada criterio esta relacionado con un objetivo de aprendizaje.

Puedes ejecutar todas estas pruebas con el comando `npm run test:oas`
como se muestra en la siguiente imagen:

![npm run test oas](docs/images/npm-run-test-oas.gif "npm run test oas")

Puedes ejecutar las pruebas de cada grupo de objetivos de aprendizaje de
manera individual con los siguientes comandos:

* `npm run test:oas-html`
* `npm run test:oas-css`
* `npm run test:oas-web-api`
* `npm run test:oas-js`

#### Pruebas end-to-end

Una prueba end-to-end (E2E) es una técnica de prueba de software en la que
se verifica el funcionamiento de todo el sistema desde el inicio hasta el
final. En otras palabras, se prueba el flujo completo del software, simulando
la interacción del usuario con la aplicación, para asegurarse de que todas las
partes del sistema funcionan correctamente en conjunto.

Puedes ejecutar estas pruebas con el comando `npm run test:e2e` como se muestra
en la siguiente imagen:

![npm run test e2e](docs/images/npm-run-test-e2e.gif "npm run test e2e")

### Github actions

Este repositorio usa una GitHub Action para ejecutar automáticamente
las pruebas unitarias, pruebas de criterios mínimos de aceptación y
y pruebas end-to-end cada vez que se hagas un _push_ en la rama
_main_ de tu repositorio.

Puedes consultar el resultado de esta Github Action
en la pestaña _Actions_ de tu repositorio en Github
como se muestra en la siguiente imagen:

![Github Action](docs/images/githubaction.gif "Github Action")

## 7. Pistas, tips y lecturas complementarias

### Prepara tu PC para trabajar

1. Antes que nada, asegúrate de tener un :pencil: editor de texto en
   condiciones, algo como [VS Code](https://code.visualstudio.com/).
2. Para ejecutar los comandos a continuación necesitarás una :shell:
   [UNIX Shell](../../topics/shell),
   que es un programita que interpreta líneas de comando (command-line
   interpreter) así como tener [git](../../topics/scm/01-git)
   instalado. Si usas un sistema operativo "UNIX-like", como GNU/Linux o MacOS,
   ya tienes una _shell_ (terminal) instalada por defecto (y probablemente `git`
   también). Si usas Windows puedes usar la versión completa de
   [Cmder](https://cmder.app/) que incluye
   [Git bash](https://git-scm.com/download/win).
3. Tus _coaches_ te compartirán un _link_ a un repo y te darán acceso de lectura.
   Debes realizar un :fork_and_knife:
   [fork](https://help.github.com/articles/fork-a-repo/) del repo.
4. :arrow_down: [Clona](https://help.github.com/articles/cloning-a-repository/)
   tu _fork_ a tu computadora (copia local).
5. 📦 Instala las dependencias del proyecto con el comando `npm install`. Esto
   asume que has instalado [Node.js](https://nodejs.org/) (que incluye
   [npm](https://docs.npmjs.com/)).
6. Si todo ha ido bien, deberías poder ejecutar las :traffic_light:
   pruebas unitarias (unit tests) con el comando `npm test`.
7. Para ver la interfaz de tu programa en el navegador, usa el comando
   `npm start` para arrancar el servidor web y dirígete a
   `http://localhost:5000` en tu navegador.
8. A codear se ha dicho! :rocket:

### Recursos y temas relacionados

Súmate al canal de Slack [#project-text-analyzer](https://claseslaboratoria.slack.com/archives/C03LXJ10WJD)
