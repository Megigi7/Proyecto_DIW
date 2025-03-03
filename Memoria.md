# Proyecto DIW: Escuela de Magia para Gatos
- María Alves Mascareña
- 27.02.25

Este proyecto consiste en la creacion de una página web temátizada usando bootstrap personalizado, cuidando que el diseño sea responsive, usando contenido multimedia optimizado y cumpliendo los requerimiento de accesibilidad y usabilidad

## Parte 1: Web personalizada con Bootstrap
#### Estructura básica y organización del documento HTML

Antes de comenzar a estructurar la página web, añadí estos cambios en la seacción `<head>`:

- Título descriptivo para la página (`<title>Escuela de Magia para Gatos</title>`)
- Favicon personalizado mediante `<link rel="icon" type="image/png" href="img/logo.png">`
- Enlaces a hojas de estilo externas:
  - Bootstrap CSS: `<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">`
  - Mis estilos personalizados: `<link href="scss/styles.css" rel="stylesheet">`
  - Font Awesome para iconos: `<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">`
  - Animate.css para animaciones: `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>`
    
![image](https://github.com/user-attachments/assets/64bac2a0-36d5-4015-a063-65abc5e3e4a0)



#### Barra de navegación (Navbar)

He implementado la barra de navegación utilizando el componente Navbar de Bootstrap con las siguientes características:

```html
<nav class="navbar navbar-expand-lg navbar-light bg-pastel-magenta fixed-top">
```

Aquí, estoy usando:
- `navbar-expand-lg`: Hace que el menú se colapse en dispositivos con pantallas menores que large (lg)
- `navbar-light`: Aplica un esquema de colores claro para los elementos de navegación
- `bg-pastel-magenta`: Mi color personalizado definido en SASS
- `fixed-top`: Mantiene la barra de navegación fija en la parte superior de la pantalla durante el desplazamiento

Dentro del navbar he incluido:
- Un logo con texto utilizando `navbar-brand`
- Un botón para dispositivos móviles con atributos de accesibilidad:
  ```html
  <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
  ```
- Un contenedor para los elementos de navegación que se colapsará en dispositivos móviles:
  ```html
  <div class="collapse navbar-collapse bg-pastel-magenta" id="navbarNav">
  ```
- Una lista de elementos de navegación usando `navbar-nav` y `nav-item`:
  ```html
  <ul class="navbar-nav ms-auto">
      <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Inicio</a>
      </li>
      <!-- más elementos de navegación -->
  </ul>
  ```

![image](https://github.com/user-attachments/assets/7e793421-ffe3-4498-a49f-78ca6158e067)

  

#### Hero Section

Para la sección principal de bienvenida, he creado una hero section:

```html
<section class="hero-section text-center text-white py-5">
```

He utilizado:
- `text-center`: Para centrar el contenido horizontalmente
- `text-white`: Para establecer el texto en color blanco
- `py-5`: Padding vertical de 5

Dentro de esta sección, he incluido:
- Un título con la clase `display-4` para darle mayor visibilidad
- Un subtítulo con la clase `lead` como texto introductorio
- Un botón de llamada a la acción con clases personalizadas que redirije a la sección "#modalidades":
  ```html
  <a href="#modalidades" class="btn btn-pastel-pink btn-lg">Explora Nuestros Cursos</a>
  ```

![image](https://github.com/user-attachments/assets/37dc04d2-847a-449e-91ac-042777c0744c)


#### Sección "Sobre nosotros"

Para esta sección, he usado:

```html
<section id="nosotros" class="container my-5">
```

- `container`: Proporciona un ancho máximo al contenido y lo centra en la página
- `my-5`: Margin vertical de nivel 5

He implementado un diseño de dos columnas usando el sistema grid de Bootstrap:

```html
<div class="row align-items-center">
    <div class="col-lg-6 animate__animated animate__fadeInLeft">
        <!-- Contenido de la primera columna -->
    </div>
    <div class="col-md-6 animate__animated animate__fadeInRight d-none d-lg-block">
        <!-- Contenido de la segunda columna -->
    </div>
</div>
```

Aquí, estoy usando:
- `row`: Establece una fila en el sistema grid
- `align-items-center`: Alinea verticalmente los elementos al centro
- `col-lg-6`: Cada columna ocupa la mitad del ancho en pantallas grandes
- `animate__animated animate__fadeInLeft/Right`: Animaciones de entrada desde los laterales
- `d-none d-lg-block`: Hace que la imagen sea visible solo en pantallas grandes
La primera columna tiene como fondo la imagen de el pergamino que hace que tenga ese aspecto mágico

![image](https://github.com/user-attachments/assets/5203c024-1103-4051-81c2-2305d227872b)


#### Sección "Modalidades"

Para mostrar los diferentes cursos, he utilizado cards de Bootstrap organizadas en una cuadrícula responsive:

```html
<div class="row row-cols-1 row-cols-md-2 row-cols-lg-4">
```

Esta estructura establece:
- 1 columna en dispositivos móviles pequeños
- 2 columnas en dispositivos medianos
- 4 columnas en dispositivos grandes

Cada card sigue esta estructura:

```html
<div class="col mb-4">
    <div class="card h-100 shadow">
        <img src="img/hada.png" class="card-img-top" alt="Hechizos de Hadas">
        <div class="card-body d-flex flex-column">
            <h5 class="card-title">Hechizos de Hadas</h5>
            <p class="card-text">...</p>
            <a href="#contacto" class="btn btn-pastel-purple mt-auto mb-2">Me interesa!</a>
        </div>
    </div>
</div>
```

He utilizado:
- `h-100`: Para que todas las cards tengan la misma altura
- `shadow`: Para añadir una sombra sutil que da profundidad
- `d-flex flex-column`: Para organizar el contenido verticalmente
- `mt-auto`: Para empujar el botón hacia abajo (siempre al final del card)

![image](https://github.com/user-attachments/assets/33e46233-0c5e-4c28-98a8-95c7228c147b)


#### Sección "Profesores Destacados"

Para esta sección he creado un diseño personalizado basado en CSS Grid que complementa las capacidades de Bootstrap:

```html
<section id="profesores" class="container-fluid my-5 profesores-section">
    <div class="profesores-grid">
        <!-- Tarjetas de profesores -->
    </div>
</section>
```

Cada profesor se presenta en una tarjeta con efecto flip:

```html
<div class="profesor-card">
    <div class="profesor-content">
        <div class="profesor-front">
            <!-- Contenido frontal -->
        </div>
        <div class="profesor-back">
            <!-- Contenido trasero -->
        </div>
    </div>
</div>
```

Este efecto se logra mediante CSS personalizado que complementa Bootstrap, permitiendo mostrar información adicional cuando el usuario interactúa con la tarjeta.

![image](https://github.com/user-attachments/assets/99492cd6-d2f9-4b51-8ed9-0d2620d9336c)


#### Sección "Actividades Extraescolares"

He implementado un carrusel de Bootstrap para mostrar las diferentes actividades:

```html
<section id="actividades" class="bg-pastel-blue text-white py-5">
    <div id="actividadesCarousel" class="carousel slide" data-bs-ride="carousel">
        <!-- Carrusel -->
    </div>
</section>
```

El carrusel incorpora:
- Varios ítems con imágenes y descripciones
- Controles de navegación:
  ```html
  <button class="carousel-control-prev" type="button" data-bs-target="#actividadesCarousel" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
  </button>
  ```
- Clases de accesibilidad como `visually-hidden` para lectores de pantalla

![image](https://github.com/user-attachments/assets/6788fc9d-f8d9-4b03-bab3-0709e25d1e59)


#### Sección "Michiartistas"

En esta sección he combinado contenido multimedia de diferentes tipos:

```html
<section id="michiartistas" class="container my-5">
    <div class="row">
        <!-- Vídeos embebidos y canvas -->
    </div>
</section>
```

He incluido:
- Videos de YouTube mediante iframes
- Un canvas interactivo creado con JavaScript:
  ```html
  <canvas id="magicCanvas" width="500%" height="315" class="bg-white"></canvas>
  ```

![image](https://github.com/user-attachments/assets/1353a083-f900-4867-b897-9310a6e96d20)



#### Sección "Contacto"

Para el formulario de contacto, he utilizado los componentes de formulario de Bootstrap:

```html
<section id="contacto" class="container my-5">
    <form id="contactForm" onsubmit="sendEmail(event)">
        <!-- Campos del formulario -->
    </form>
</section>
```

Cada campo sigue la estructura recomendada por Bootstrap:

```html
<div class="mb-3">
    <label for="nombre" class="form-label">Nombre</label>
    <input type="text" class="form-control" id="nombre" name="nombre" required>
</div>
```

He añadido validación básica con el atributo `required` y una función JavaScript para gestionar el envío

![image](https://github.com/user-attachments/assets/d4fadd99-e090-4137-a953-88c073a642b0)


#### Footer

He completado la estructura con un footer sencillo pero informativo:

```html
<footer class="bg-pastel-purple text-white text-center py-4">
    <!-- Contenido del footer -->
</footer>
```

Incluye:
- Copyright
- Enlaces a redes sociales utilizando iconos de Font Awesome:
  ```html
  <a href="#" class="text-white"><i class="fab fa-instagram"></i></a>
  ```

![image](https://github.com/user-attachments/assets/74e53db3-0fe4-4447-a0d7-9561a30b95fa)


## Parte 2: Contenido multimedia

#### Imágenes

He utilizado numerosas imágenes a lo largo del sitio web, todas optimizadas para su uso en la web:

- **Logo y favicon**: 
  ```html
  <img src="img/logo.png" alt="Logo" width="30" height="30" class="d-inline-block align-text-top">
  ```
  Especificando dimensiones directamente en el HTML para evitar saltos de contenido durante la carga.

- **Imágenes responsivas**: 
  ```html
  <img src="img/escuela2.png" class="img-fluid rounded mb-4" alt="Gatos aprendiendo magia">
  ```
  Utilizando `img-fluid` para que se adapten al tamaño del contenedor.

- **Imágenes en cards**: 
  ```html
  <img src="img/hada.png" class="card-img-top" alt="Hechizos de Hadas">
  ```
  Optimizadas para mantener una relación de aspecto consistente.

- **Imágenes de profesores**: 
  ```html
  <img src="img/bizcocho.jpg" alt="Profesora Luna">
  ```
  En formato JPG por tratarse de fotografías.

#### Vídeos

He incorporado vídeos de YouTube mediante iframes:

```html
<iframe width="100%" height="315" src="https://www.youtube.com/embed/i-NgtMk_tCA?si=p4LRNTGkHs_t0Kdn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

Características:
- Ancho responsive (width="100%")
- Atributos de accesibilidad (title)
- Configuración de permisos (allow)

#### Canvas interactivo

He implementado un dibujo de un gato utilizando la API Canvas de HTML5:

```html
<canvas id="magicCanvas" width="500%" height="315" class="bg-white"></canvas>
```

El JavaScript asociado realiza el dibujo del gato con la función `drawStar` que crea estrellas personalizadas:

#### Animaciones

He utilizado dos tipos de animaciones:

1. **Animate.css** para efectos de entrada:
   ```html
   <div class="col-lg-6 animate__animated animate__fadeInLeft">
   ```
   Aplicando clases como `animate__fadeInLeft`, `animate__fadeInRight` y `animate__fadeInDown`.

2. **Efectos CSS personalizados** para las tarjetas de profesores, que tienen una animación de volteo al pasar el cursor sobre ellas.


## Parte 3: Accesibilidad y usabilidad

### Implementación de principios de accesibilidad

#### Estructura semántica

He utilizado etiquetas HTML5 semánticas para mejorar la accesibilidad:
- `<nav>` para la navegación
- `<section>` para cada sección de contenido
- `<footer>` para el pie de página
- Encabezados jerárquicos (`<h1>`, `<h2>`, etc.) organizados lógicamente

#### Atributos ARIA

He incluido diversos atributos ARIA para mejorar la experiencia de usuarios con lectores de pantalla:
- `aria-controls`: Indica qué elemento es controlado por otro
- `aria-expanded`: Indica el estado de expansión de elementos colapsables
- `aria-label`: Proporciona etiquetas para elementos sin texto visible
- `aria-current="page"`: Indica la página actual en la navegación

Ejemplo:
```html
<button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
```

#### Texto alternativo

Todas las imágenes cuentan con texto alternativo descriptivo:
```html
<img src="img/escuela2.png" class="img-fluid rounded mb-4" alt="Gatos aprendiendo magia">
```

#### Contraste de colores

He seleccionado colores que proporcionan suficiente contraste:
- Texto blanco (`text-white`) sobre fondos oscuros o de color
- Elementos de fondo claro con texto oscuro para asegurar la legibilidad

#### Navegación por teclado

Los elementos interactivos son accesibles mediante teclado:
- Enlaces con foco visible
- Orden lógico de tabulación
- Uso de `visually-hidden` para texto solo para lectores de pantalla:
  ```html
  <span class="visually-hidden">Previous</span>
  ```

### Usabilidad

#### Navegación consistente

La barra de navegación permanece fija (`fixed-top`) para facilitar el acceso a todas las secciones del sitio desde cualquier punto.

#### Feedback visual

Los elementos interactivos proporcionan feedback visual:
- Botones con estilos hover
- Tarjetas de profesores con efecto de volteo
- Elementos activos con indicadores visuales

#### Legibilidad

La legibilidad se mantiene lo más óptima posible:
- Texto con tamaño adecuado
- Espaciado suficiente entre elementos
- Fondos texturados sutiles que no interfieren con la lectura

#### Diseño responsive

El diseño se adapta a diferentes tamaños de pantalla:
- Menú colapsable en dispositivos móviles
- Cambios en la disposición de columnas según el tamaño de pantalla
- Ocultación selectiva de elementos en pantallas pequeñas mediante clases como `d-none d-lg-block`

#### Formularios usables

El formulario de contacto sigue buenas prácticas:
- Etiquetas claras asociadas con los campos mediante `for` e `id`
- Validación con mensajes de error
- Botón de envío distintivo

#### Análisis con herramientas web
Desde esta página web 
  > https://wave.webaim.org/
hemos realizado un análisis de nuestra web. Nos ha devuelto los siguientes resultados:
![image](https://github.com/user-attachments/assets/6b0a2614-a62c-4fe4-85a1-bdb3f6b44b44)
- 3 errores: Links vacíos de rrss que no se usan
- 24 errores de contrastes: Elementos mejorables como botones y títulos
Por lo demás, nuestra página web cumple con los requisitos


## Implementación de SASS y personalización de Bootstrap

Para cumplir con los requisitos de personalización mediante SASS, he creado un archivo de estilos personalizado que define:

### Colores personalizados

He creado variables SASS para definir mi paleta de colores:
```scss
$pastel-pink: #FFB6C1;
$pastel-blue: #87CEEB;
$pastel-purple: #CCCCFF;
$pastel-magenta: #FFD1DC;
```

### Clases personalizadas

He extendido Bootstrap creando clases para mis colores:
```scss
.bg-pastel-pink {
    background-color: $pastel-pink;
}

.btn-pastel-purple {
    background-color: $pastel-purple;
    color: white;
    &:hover {
        background-color: darken($pastel-purple, 10%);
    }
}
```

### Estilos para componentes personalizados

He creado estilos específicos para elementos como las tarjetas de profesores:
```scss
.profesor-card {
    perspective: 1000px;
    // etc
}

.profesor-content {
    transition: transform 0.6s;
    transform-style: preserve-3d;
    // etc
}
```

## Conclusión

A lo largo de este proyecto, he aplicado una amplia gama de tecnologías y técnicas para crear un sitio web que no solo cumple con los requisitos de la práctica, sino que también ofrece una experiencia de usuario atractiva y accesible:

1. He utilizado Bootstrap como framework base, aprovechando su sistema de grid, componentes y utilidades para crear un diseño responsive y consistente.

2. He personalizado Bootstrap mediante SASS, creando una identidad visual única con colores pastel que refuerzan la temática mágica.

3. He incorporado diversos tipos de contenido multimedia (imágenes, vídeos, canvas) optimizados para web.

El desarrollo de esta página web me ha ayudado a sensibilizarme con los requisitos 

5. He implementado principios de accesibilidad siguiendo las pautas WCAG, asegurando que el sitio sea usable por personas con diferentes capacidades.

6. He añadido interactividad mediante JavaScript para mejorar la experiencia de usuario.

La "Escuela de Magia para Gatos" es un ejemplo de cómo se pueden combinar estas tecnologías para crear un sitio web moderno, accesible y visualmente atractivo, cumpliendo con todos los requisitos establecidos en el enunciado de la práctica.

## Organización con Trello
Comienzo del proyecto:  12/02/2025
![image](https://github.com/user-attachments/assets/09525f0a-8407-4aae-8283-402dc42bc09b)

Creación de estructura web junto a contenido multimedia: 14/02/2025 - 20/02/2025
![image](https://github.com/user-attachments/assets/c9d1af2e-1f79-416f-9877-ccbd7b2ba36c)

Adaptación de la web siguiendo las pautas de accesibilidad y usabilidad: 20/02/25 - 22/02/205
![image](https://github.com/user-attachments/assets/36470e5f-d5f3-4684-9012-427e1e959e7f)

Finalización del proyecto: 22/02/2025
![image](https://github.com/user-attachments/assets/6e4a0235-0b02-47b8-9325-2a0068decc4d)

## Bibliografía
- Documentación eniun proporcionada en moodle
