# 📚 Apuntes Completos del Sistema - AdoptaTuÁrbol

> **Plataforma de Adopción de Árboles**  
> Documentación técnica completa para estudio y certificación  
> Fecha: 5 de noviembre de 2025

---

## 📋 Tabla de Contenidos

1. [Descripción General del Proyecto](#descripción-general-del-proyecto)
2. [Estructura HTML](#estructura-html)
3. [Estilos CSS](#estilos-css)
4. [Funcionalidad JavaScript](#funcionalidad-javascript)
5. [Conceptos Clave para Certificación](#conceptos-clave-para-certificación)
6. [Mejores Prácticas Implementadas](#mejores-prácticas-implementadas)

---

## 🎯 Descripción General del Proyecto

### Objetivo
Crear una plataforma web interactiva para la adopción de árboles con las siguientes características:
- Sistema de navegación intuitivo
- Selector de tipos de árboles
- Catálogo visual de árboles disponibles
- Funcionalidad de adopción y donación
- Footer informativo con suscripción

### Tecnologías Utilizadas
- **HTML5**: Estructura semántica
- **CSS3**: Diseño y layout con Flexbox
- **JavaScript (Vanilla)**: Interactividad y manipulación del DOM

---

## 🏗️ Estructura HTML

### 1. Configuración del Documento (`<head>`)

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css/styles.css">
    <script src="js/script.js" defer></script>
</head>
```

#### Elementos Clave:
- **`charset="UTF-8"`**: Codificación de caracteres universales (soporte para tildes y caracteres especiales)
- **`viewport`**: Configuración responsive para dispositivos móviles
- **`defer`**: El script se ejecuta después de que el HTML esté completamente cargado

---

### 2. Header Principal

```html
<header>
    <h1>Tu plataforma favorita de adopcion de arboles</h1>
</header>
```

#### Propósito:
- Banner superior con título descriptivo
- Elemento semántico `<header>` para SEO

#### CSS Asociado:
```css
header {
    background-color: #4CAF50;
    color: rgb(0, 0, 0);
    padding: 10px 0;
    text-align: center;
}
```

---

### 3. Barra de Navegación

```html
<div class="barra-navegacion">
    <div class="titulo">
        <span class="color1">Adopta</span>
        <span class="color2">Tu</span>
        <span class="color3">Árbol</span>
    </div>
    <div class="menu">
        <button class="boton1">Adoptar</button>
        <button class="boton2">Donar</button>
    </div>
</div>
```

#### Estructura:
- **Contenedor principal**: `.barra-navegacion`
- **Título dividido**: Tres `<span>` con colores diferentes
- **Botones de acción**: Adoptar y Donar

#### CSS - Layout Flexbox:
```css
.barra-navegacion {
    display: flex;
    justify-content: space-between;  /* Separa título y botones */
    align-items: center;              /* Centrado vertical */
    height: 60px;
    margin-left: 200px;
    margin-right: 200px;
    padding: 10px 20px;
    border-bottom: 2px solid #000000;
    box-shadow: 0px 2px 0px 0px black;
}
```

#### Propiedades CSS Importantes:
- **`display: flex`**: Activa Flexbox
- **`justify-content: space-between`**: Distribuye espacio entre elementos
- **`align-items: center`**: Alineación vertical
- **`box-shadow`**: Sombra decorativa para profundidad

#### Estilo de Título Multicolor:
```css
.titulo {
    font-size: 50px;
    font-weight: bold;
    display: flex;
}
.color1 { color: #004d03; }  /* Verde oscuro */
.color2 { color: #00c807; }  /* Verde brillante */
.color3 { color: #448a46; }  /* Verde intermedio */
```

#### Botones con Efecto de Sombra:
```css
.boton1 {
    width: 120px;
    height: 52px;
    background-color: #0343006e;
    box-shadow: 3px 3px 0px 0px black;  /* Sombra desplazada */
    cursor: pointer;
}
.boton2 {
    width: 120px;
    height: 52px;
    background-color: #008b07;
    color: white;
    box-shadow: 3px 3px 0px 0px black;
    cursor: pointer;
}
```

**Concepto**: Box-shadow con desplazamiento 3D para estilo "neomorphism"

---

### 4. Selector de Árboles

```html
<div class="selector">
    <div>
        <span>Mostrando:</span>
        <span class="selector-arboles">Todos los árboles</span>
    </div>
    <select class="tipo-arbol" title="Seleccione el árbol">
        <option disabled selected hidden>Todos los árboles.</option>
        <option>Árboles frutales.</option>
        <option>Árboles ornamentales.</option>
        <option>Árboles de flor.</option>
    </select>
</div>
```

#### Elementos:
- **Display dinámico**: `.selector-arboles` muestra el filtro activo
- **Dropdown**: `<select>` con opciones de categorías
- **Primera opción oculta**: `disabled selected hidden` para placeholder

#### CSS - Espaciado con Gap:
```css
.selector {
    display: flex;
    justify-content: center;
    margin-top: 20px;
    font-size: 30px;
    gap: 450px;  /* Espacio entre elementos flex */
}
```

#### JavaScript Asociado:
```javascript
var cambiararbol = document.querySelector(".tipo-arbol");
var arbolSeleccionado = document.querySelector(".selector-arboles");
cambiararbol.addEventListener("change", function() {
    if(this.value === "Árboles frutales.") {
        arbolSeleccionado.innerText = this.value;
    } else if(this.value === "Árboles ornamentales.") {
        arbolSeleccionado.innerText = this.value;
    } else if(this.value === "Árboles de flor.") {
        arbolSeleccionado.innerText = this.value;
    }
});
```

**Concepto**: Event listener en `change` que actualiza el texto dinámicamente

---

### 5. Contenido Principal - Grid de Árboles

```html
<main class="contenido-principal">
    <div class="contenido-izquierda">
        <div class="cuadro-arbol">
            <img src="img/alamo.jpg" class="arbol" alt="Álamo">
            <div>
                <h2>Álamo</h2>
                <p>Árbol caducifolio, de hojas anchas...</p>
            </div>
            <button class="boton-adoptar">Adoptar</button>
        </div>
        <!-- Más árboles... -->
    </div>
    <div class="contenido-derecha">
        <!-- Árboles del lado derecho -->
    </div>
</main>
```

#### Estructura:
- **Contenedor principal**: `<main>` (elemento semántico)
- **Dos columnas**: `.contenido-izquierda` y `.contenido-derecha`
- **Tarjetas individuales**: `.cuadro-arbol`

#### CSS - Layout con Flexbox:
```css
.contenido-principal {
    padding: 20px;
    display: flex;
    justify-content: center;
}
.contenido-izquierda { float: left; }
.contenido-derecha { float: right; }
```

#### Tarjeta de Árbol:
```css
.cuadro-arbol {
    width: 500px;
    height: 250px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px;
    padding: 20px;
    border-radius: 5px;
    background-color: #e4e4e4;
    gap: 20px;  /* Espacio entre imagen, texto y botón */
}
```

#### Imagen con Estilo:
```css
.arbol {
    width: 200px;
    height: 150px;
    object-fit: cover;    /* Recorta imagen manteniendo proporción */
    border: 3px solid #000000;
}
```

**Concepto**: `object-fit: cover` mantiene aspecto de imagen sin distorsión

#### Botón Adoptar:
```css
.boton-adoptar {
    height: 40px;
    background-color: #79b07b;
    padding: 10px 20px;
    font-family: "Comic Sans MS", "Comic Sans", cursive;
    font-weight: bold;
    box-shadow: 2px 2px 0px 0px black;
    cursor: pointer;
}
```

#### JavaScript - Interactividad del Botón:
```javascript
var botoncambiar = document.querySelectorAll(".boton-adoptar");
botoncambiar.forEach(function(boton) {
    boton.addEventListener("click", function() {
        this.innerText = "Adoptado";
        this.style.backgroundColor = "#75ea21ff";
    });
});
```

**Conceptos Clave**:
- `querySelectorAll()`: Selecciona TODOS los elementos con esa clase
- `forEach()`: Itera sobre cada botón
- `this`: Referencia al elemento clickeado
- `innerText`: Cambia el texto del botón
- `style.backgroundColor`: Modifica CSS inline

---

### 6. Footer (Pie de Página)

```html
<footer class="pie">
    <div class="pie1">
        <h3>Contáctanos</h3>
        <p>Av. principal #123</p>
        <p>Ciudad Palma 10000</p>
        <p>Chile</p>
    </div>
    <div class="pie2">
        <ul>
            <li>Inicio</li>
            <li>Sobre nosotros</li>
            <li>Adopta un árbol</li>
            <li>Contacto</li>
            <li>Patrocinadores</li>
            <li>Proyectos</li>
        </ul>
    </div>
    <div class="pie3">
        <h3>Suscribete</h3>
        <input type="email" placeholder="Usuario@correo.com" class="correo">
        <input type="submit" value="Enviar" class="boton-enviar">
    </div>
</footer>
```

#### Estructura - Tres Secciones:
1. **Contacto** (`.pie1`): Información de dirección
2. **Navegación** (`.pie2`): Lista de enlaces
3. **Suscripción** (`.pie3`): Formulario de email

#### CSS - Flexbox con Proporciones:
```css
.pie {
    display: flex;
    background-color: #4CAF50;
    color: rgb(0, 0, 0);
}
.pie1 { flex: 1; }  /* 1 parte del espacio */
.pie2 { flex: 2; }  /* 2 partes (doble ancho) */
.pie3 { flex: 1; }  /* 1 parte del espacio */
```

**Concepto**: `flex: 1` distribuye espacio proporcionalmente (1:2:1)

#### Lista en Columnas:
```css
ul {
    list-style: none;
    column-count: 2;     /* Divide lista en 2 columnas */
    column-gap: 70px;    /* Espacio entre columnas */
}
```

**Concepto**: CSS Multi-column Layout para diseño de periódico

#### Input de Email:
```css
.correo {
    width: 250px;
    height: 30px;
    font-size: 16px;
    border: #000000 3px solid;
}
```

**Tipo de Input**: `type="email"` valida formato de correo automáticamente

---

## 🎨 Estilos CSS - Análisis Completo

### Tipografía Global

```css
body {
    font-family: "Comic Sans MS", "Comic Sans", cursive;
    margin: 0;
    background-color: #f4f4f4;
    color: #000000;
}
```

#### Propiedades:
- **`font-family`**: Fuente con fallbacks (Comic Sans → Comic Sans → cursive)
- **`margin: 0`**: Elimina márgenes por defecto del navegador
- **`background-color`**: Color de fondo general

---

### Sistema de Colores

| Color Hex   | Uso                    | Descripción           |
|-------------|------------------------|-----------------------|
| `#4CAF50`   | Header, Footer         | Verde principal       |
| `#004d03`   | Título palabra 1       | Verde muy oscuro      |
| `#00c807`   | Título palabra 2       | Verde brillante       |
| `#448a46`   | Título palabra 3       | Verde intermedio      |
| `#008b07`   | Botones CTA            | Verde acción          |
| `#79b07b`   | Botón adoptar          | Verde claro           |
| `#75ea21ff` | Botón adoptado (JS)    | Verde lima            |
| `#e4e4e4`   | Fondo tarjetas         | Gris claro            |
| `#f4f4f4`   | Fondo body             | Gris muy claro        |

---

### Propiedades Flexbox Utilizadas

#### 1. **`display: flex`**
Activa el modelo Flexbox en el contenedor.

```css
.barra-navegacion {
    display: flex;
}
```

#### 2. **`justify-content`**
Alinea elementos en el eje principal (horizontal).

```css
justify-content: space-between;  /* Espacio máximo entre elementos */
justify-content: center;         /* Centra elementos */
```

#### 3. **`align-items`**
Alinea elementos en el eje transversal (vertical).

```css
align-items: center;  /* Centrado vertical */
```

#### 4. **`gap`**
Espacio entre elementos flex (moderna alternativa a margins).

```css
gap: 20px;   /* 20px entre cada elemento hijo */
gap: 450px;  /* Separación grande en selector */
```

#### 5. **`flex`**
Define proporción de espacio que ocupa cada elemento.

```css
.pie1 { flex: 1; }  /* 25% del ancho */
.pie2 { flex: 2; }  /* 50% del ancho */
.pie3 { flex: 1; }  /* 25% del ancho */
```

---

### Efectos Visuales

#### Box Shadow (Sombras)
```css
box-shadow: 3px 3px 0px 0px black;
```

**Sintaxis**: `offset-x offset-y blur-radius spread-radius color`
- **3px**: Desplazamiento horizontal
- **3px**: Desplazamiento vertical
- **0px**: Sin difuminado (sombra sólida)
- **0px**: Sin expansión
- **black**: Color de sombra

#### Border Radius (Bordes Redondeados)
```css
border-radius: 5px;
```

---

### Propiedad `object-fit`

```css
.arbol {
    object-fit: cover;
}
```

**Valores posibles**:
- `cover`: Cubre área completa manteniendo proporción (puede recortar)
- `contain`: Imagen completa dentro del contenedor (puede dejar espacio)
- `fill`: Estira imagen para llenar contenedor (distorsiona)
- `none`: Tamaño original
- `scale-down`: El menor entre `none` y `contain`

---

### Pseudo-clases y Selectores

#### Cursor Pointer
```css
cursor: pointer;  /* Cambia cursor a manita en hover */
```

**Usabilidad**: Indica elementos clickeables

---

## ⚡ Funcionalidad JavaScript - Análisis Profundo

### 1. Alerta de Donación

```javascript
var botondonar = document.querySelectorAll(".boton2");
botondonar.forEach(function(boton) {
    boton.addEventListener("click", function() {
        alert("¡Gracias por donar a AdoptaTuÁrbol!");
    });
});
```

#### Desglose:
1. **`document.querySelectorAll(".boton2")`**: Selecciona TODOS los elementos con clase `.boton2`
2. **`forEach()`**: Itera sobre cada elemento de la NodeList
3. **`addEventListener("click", ...)`**: Añade listener de evento click
4. **`alert()`**: Muestra ventana emergente del navegador

#### Conceptos:
- **Event Listener**: Función que espera un evento específico
- **Callback Function**: Función que se ejecuta cuando ocurre el evento
- **Alert**: Ventana modal bloqueante (no recomendada en producción moderna)

---

### 2. Cambio de Estado del Botón Adoptar

```javascript
var botoncambiar = document.querySelectorAll(".boton-adoptar");
botoncambiar.forEach(function(boton) {
    boton.addEventListener("click", function() {
        this.innerText = "Adoptado";
        this.style.backgroundColor = "#75ea21ff";
    });
});
```

#### Desglose:
1. **`querySelectorAll(".boton-adoptar")`**: Selecciona todos los botones de adopción
2. **`this`**: Referencia al botón específico clickeado
3. **`innerText`**: Cambia el texto interno del elemento
4. **`style.backgroundColor`**: Modifica CSS inline (prioridad alta)

#### Conceptos:
- **`this` keyword**: En event listener, refiere al elemento que disparó el evento
- **DOM Manipulation**: Modificación de propiedades del elemento
- **Inline Styles**: Estilos aplicados directamente (mayor especificidad)

#### Ventajas de este enfoque:
- Feedback visual inmediato
- Estado persiste hasta reload de página
- No requiere backend

#### Mejora potencial:
```javascript
// Versión mejorada con toggle
boton.addEventListener("click", function() {
    if(this.innerText === "Adoptar") {
        this.innerText = "Adoptado";
        this.style.backgroundColor = "#75ea21ff";
    } else {
        this.innerText = "Adoptar";
        this.style.backgroundColor = "#79b07b";
    }
});
```

---

### 3. Selector Dinámico de Árboles

```javascript
var cambiararbol = document.querySelector(".tipo-arbol");
var arbolSeleccionado = document.querySelector(".selector-arboles");
cambiararbol.addEventListener("change", function() {
    if(this.value === "Árboles frutales.") {
        arbolSeleccionado.innerText = this.value;
    } else if(this.value === "Árboles ornamentales.") {
        arbolSeleccionado.innerText = this.value;
    } else if(this.value === "Árboles de flor.") {
        arbolSeleccionado.innerText = this.value;
    }
});
```

#### Desglose:
1. **`querySelector()`**: Selecciona PRIMER elemento (solo uno)
2. **`change` event**: Se dispara cuando cambia valor del `<select>`
3. **`this.value`**: Valor de la opción seleccionada
4. **Condicionales if/else**: Evalúa qué opción fue seleccionada
5. **`innerText`**: Actualiza texto mostrado

#### Conceptos:
- **Event "change"**: Específico para inputs, selects, textareas
- **`this.value`**: Obtiene valor actual del elemento select
- **DOM Traversal**: Acceso a otro elemento del DOM para modificarlo

#### Optimización posible:
```javascript
// Versión simplificada sin condicionales
cambiararbol.addEventListener("change", function() {
    arbolSeleccionado.innerText = this.value;
});
```

**Razón**: Todas las ramas del if hacen lo mismo, no es necesaria la condición.

---

## 🎓 Conceptos Clave para Certificación

### HTML5

#### 1. **Elementos Semánticos**
```html
<header>   - Encabezado de página o sección
<main>     - Contenido principal
<footer>   - Pie de página
<section>  - Sección temática de contenido
<article>  - Contenido independiente y auto-contenido
<nav>      - Navegación principal
```

**Ventajas**:
- Mejor SEO
- Accesibilidad mejorada
- Código más legible

#### 2. **Atributos Importantes**
```html
alt="descripción"        - Texto alternativo (accesibilidad)
title="tooltip"          - Tooltip al hacer hover
placeholder="texto"      - Texto de ayuda en inputs
defer                    - Script se ejecuta después del DOM
disabled                 - Deshabilita elemento
hidden                   - Oculta visualmente
selected                 - Opción pre-seleccionada
```

#### 3. **Tipos de Input**
```html
<input type="email">     - Validación de formato email
<input type="submit">    - Botón de envío de formulario
<input type="text">      - Texto simple
<input type="number">    - Solo números
<input type="date">      - Selector de fecha
```

---

### CSS3

#### 1. **Modelo de Caja (Box Model)**
```
┌─────────────────────────────────┐
│         Margin (exterior)       │
│  ┌───────────────────────────┐  │
│  │  Border (borde)           │  │
│  │  ┌─────────────────────┐  │  │
│  │  │  Padding (interno)  │  │  │
│  │  │  ┌───────────────┐  │  │  │
│  │  │  │   Content     │  │  │  │
│  │  │  │  (contenido)  │  │  │  │
│  │  │  └───────────────┘  │  │  │
│  │  └─────────────────────┘  │  │
│  └───────────────────────────┘  │
└─────────────────────────────────┘
```

#### 2. **Selectores CSS**
```css
.clase          - Selecciona por clase
#id             - Selecciona por ID
elemento        - Selecciona por etiqueta HTML
.padre .hijo    - Descendiente (cualquier nivel)
.padre > .hijo  - Hijo directo (un nivel)
elemento:hover  - Pseudo-clase (estado hover)
elemento::before - Pseudo-elemento
```

#### 3. **Especificidad CSS**
```
Inline styles (1000 puntos)    style="..."
IDs (100 puntos)               #miId
Clases (10 puntos)             .miClase
Elementos (1 punto)            div, p, h1
```

**Orden de prioridad**: Inline > ID > Clase > Elemento

#### 4. **Unidades CSS**
```css
px    - Píxeles (absoluto)
%     - Porcentaje (relativo al padre)
em    - Relativo al font-size del padre
rem   - Relativo al font-size del root (html)
vh/vw - Viewport height/width (1vh = 1% alto pantalla)
```

#### 5. **Flexbox - Propiedades del Contenedor**
```css
display: flex;              /* Activa Flexbox */
flex-direction: row;        /* row | column | row-reverse | column-reverse */
justify-content: center;    /* flex-start | flex-end | center | space-between | space-around */
align-items: center;        /* flex-start | flex-end | center | stretch | baseline */
flex-wrap: wrap;            /* nowrap | wrap | wrap-reverse */
gap: 20px;                  /* Espacio entre elementos */
```

#### 6. **Flexbox - Propiedades de los Hijos**
```css
flex: 1;                    /* Proporción de espacio (flex-grow) */
order: 2;                   /* Orden de aparición */
align-self: flex-end;       /* Alineación individual */
```

---

### JavaScript (ES5/ES6)

#### 1. **Selectores del DOM**
```javascript
document.querySelector(".clase")           // Primer elemento
document.querySelectorAll(".clase")        // Todos los elementos (NodeList)
document.getElementById("id")              // Por ID
document.getElementsByClassName("clase")   // Por clase (HTMLCollection)
document.getElementsByTagName("div")       // Por etiqueta
```

**Diferencia**: `querySelector` usa selectores CSS completos.

#### 2. **Event Listeners**
```javascript
elemento.addEventListener("evento", function() {
    // Código a ejecutar
});
```

**Eventos comunes**:
- `click` - Click del mouse
- `change` - Cambio en input/select
- `submit` - Envío de formulario
- `keypress` - Tecla presionada
- `mouseover` - Mouse sobre elemento
- `load` - Página cargada completamente

#### 3. **Manipulación del DOM**
```javascript
elemento.innerText = "nuevo texto";        // Cambia texto
elemento.innerHTML = "<b>HTML</b>";        // Cambia HTML interno
elemento.style.color = "red";              // Modifica CSS
elemento.classList.add("clase");           // Añade clase
elemento.classList.remove("clase");        // Elimina clase
elemento.classList.toggle("clase");        // Alterna clase
elemento.getAttribute("href");             // Obtiene atributo
elemento.setAttribute("href", "url");      // Modifica atributo
```

#### 4. **`this` Keyword**
```javascript
boton.addEventListener("click", function() {
    console.log(this);  // this = boton (elemento que disparó el evento)
});
```

**Importante**: En arrow functions `() =>`, `this` NO refiere al elemento.

#### 5. **Métodos de Array**
```javascript
array.forEach(function(elemento) {
    // Itera sobre cada elemento
});

array.map(function(elemento) {
    return elemento * 2;  // Crea nuevo array transformado
});

array.filter(function(elemento) {
    return elemento > 5;  // Crea nuevo array filtrado
});
```

#### 6. **Condicionales**
```javascript
if (condicion) {
    // código si es true
} else if (otraCondicion) {
    // código si segunda condición es true
} else {
    // código si todas son false
}

// Operadores de comparación
===   // Igualdad estricta (valor Y tipo)
!==   // Desigualdad estricta
>     // Mayor que
<     // Menor que
>=    // Mayor o igual
<=    // Menor o igual
```

#### 7. **Variables**
```javascript
var nombre = "valor";     // Scope de función (antiguo)
let nombre = "valor";     // Scope de bloque (moderno)
const nombre = "valor";   // Constante (no re-asignable)
```

---

## 💡 Mejores Prácticas Implementadas

### HTML
✅ **Uso de elementos semánticos** (`<header>`, `<main>`, `<footer>`)  
✅ **Atributos `alt` en imágenes** (accesibilidad)  
✅ **Script con `defer`** (carga optimizada)  
✅ **Estructura clara con comentarios**  

### CSS
✅ **Organización con comentarios de sección**  
✅ **Nombres de clases descriptivos**  
✅ **Uso de Flexbox para layouts**  
✅ **Diseño consistente con sistema de colores**  
✅ **Efectos visuales con box-shadow**  
✅ **Cursor pointer en elementos interactivos**  

### JavaScript
✅ **Nombres de variables descriptivos**  
✅ **Separación de concerns** (JS separado del HTML)  
✅ **Event listeners en lugar de inline handlers**  
✅ **Uso de `querySelectorAll` para múltiples elementos**  
✅ **Comentarios explicativos en código complejo**  

---

## 🚀 Mejoras Potenciales (Para Estudio Avanzado)

### 1. **Responsividad (Media Queries)**
```css
@media (max-width: 768px) {
    .barra-navegacion {
        margin-left: 20px;
        margin-right: 20px;
        flex-direction: column;
    }
}
```

### 2. **Accesibilidad Mejorada**
```html
<button aria-label="Adoptar árbol Álamo">Adoptar</button>
<img src="..." alt="Árbol Álamo en primavera con hojas verdes">
```

### 3. **LocalStorage (Persistencia)**
```javascript
// Guardar adopciones
localStorage.setItem("adoptados", JSON.stringify(arboles));

// Recuperar al cargar página
const adoptados = JSON.parse(localStorage.getItem("adoptados"));
```

### 4. **Fetch API (Conexión Backend)**
```javascript
fetch("/api/adoptar", {
    method: "POST",
    body: JSON.stringify({ arbol: "Álamo" }),
    headers: { "Content-Type": "application/json" }
})
.then(response => response.json())
.then(data => console.log(data));
```

### 5. **Animaciones CSS**
```css
.boton-adoptar {
    transition: background-color 0.3s ease;
}
.boton-adoptar:hover {
    transform: scale(1.05);
}
```

---

## 📖 Glosario de Términos

| Término | Definición |
|---------|------------|
| **DOM** | Document Object Model - Representación del HTML como árbol de objetos |
| **Flexbox** | Sistema de layout CSS unidimensional (fila o columna) |
| **Event Listener** | Función que espera un evento específico para ejecutarse |
| **Callback** | Función pasada como argumento a otra función |
| **NodeList** | Lista de nodos del DOM (resultado de querySelectorAll) |
| **Semantic HTML** | HTML que describe el significado del contenido |
| **Inline CSS** | Estilos aplicados directamente en el atributo style |
| **SEO** | Search Engine Optimization - Optimización para buscadores |
| **Responsive Design** | Diseño que se adapta a diferentes tamaños de pantalla |
| **Box Model** | Modelo de cajas CSS (content, padding, border, margin) |

---

## 🎯 Checklist para Certificación

### HTML
- [ ] Estructura básica (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>`)
- [ ] Elementos semánticos (`<header>`, `<main>`, `<footer>`, etc.)
- [ ] Formularios (`<form>`, `<input>`, `<select>`, `<textarea>`)
- [ ] Atributos de accesibilidad (`alt`, `title`, `aria-label`)
- [ ] Tipos de input (`email`, `number`, `date`, etc.)

### CSS
- [ ] Selectores (clase, ID, elemento, descendiente, hijo directo)
- [ ] Box Model (margin, padding, border, content)
- [ ] Flexbox (display flex, justify-content, align-items, gap)
- [ ] Posicionamiento (static, relative, absolute, fixed)
- [ ] Unidades (px, %, em, rem, vh, vw)
- [ ] Colores (hex, rgb, rgba, named colors)
- [ ] Tipografía (font-family, font-size, font-weight)
- [ ] Efectos (box-shadow, border-radius, transition)

### JavaScript
- [ ] Variables (var, let, const)
- [ ] Tipos de datos (string, number, boolean, array, object)
- [ ] Operadores (aritméticos, comparación, lógicos)
- [ ] Condicionales (if/else, switch)
- [ ] Bucles (for, while, forEach)
- [ ] Funciones (declaración, expresión, arrow functions)
- [ ] DOM (querySelector, querySelectorAll, getElementById)
- [ ] Eventos (addEventListener, tipos de eventos)
- [ ] Manipulación DOM (innerText, innerHTML, style, classList)
- [ ] This keyword

---

## 📚 Recursos Adicionales para Estudio

### Documentación Oficial
- [MDN Web Docs - HTML](https://developer.mozilla.org/es/docs/Web/HTML)
- [MDN Web Docs - CSS](https://developer.mozilla.org/es/docs/Web/CSS)
- [MDN Web Docs - JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript)

### Flexbox
- [CSS Tricks - Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - Juego interactivo

### JavaScript
- [JavaScript.info](https://javascript.info/)
- [Eloquent JavaScript](https://eloquentjavascript.net/)

---

## 🏆 Resumen Ejecutivo

### Tecnologías Dominadas
1. **HTML5**: Estructura semántica, formularios, multimedia
2. **CSS3**: Flexbox, box model, efectos visuales, responsive design
3. **JavaScript**: DOM manipulation, event handling, interactividad

### Patrones Implementados
- **Layout con Flexbox**: Distribución flexible de elementos
- **Event-Driven Programming**: Respuesta a acciones del usuario
- **Component-Based Design**: Tarjetas reutilizables
- **Progressive Enhancement**: Funcionalidad básica + JS para mejoras

### Habilidades Demostradas
✅ Estructuración semántica de contenido  
✅ Diseño visual con CSS moderno  
✅ Interactividad con JavaScript vanilla  
✅ Manejo de eventos del DOM  
✅ Manipulación dinámica de contenido  
✅ Diseño de interfaz consistente  

---

**Última actualización**: 5 de noviembre de 2025  
**Proyecto**: Plataforma AdoptaTuÁrbol  
**Propósito**: Material de estudio para certificación web

---

*Este documento está diseñado para ser una referencia completa que cubre todos los conceptos, técnicas y mejores prácticas utilizadas en el proyecto. Úsalo como guía de estudio y consulta rápida para tu certificación.*
