*****************************************************
*                                                   *
*  Guía de Uso - Biblioteca de Componentes UI       *
*                                                   *
*****************************************************
1. Estructura del Proyecto

/demo
    └─ index.html             # Página demo con ejemplos funcionales
/styles
    ├─ variables/variables.css # Variables CSS (colores, tipografías, espaciados)
    ├─ base/base.css           # Estilos base (reset, tipografía, layout general)
    └─ components/components.css # Estilos de los componentes UI (botones, tarjetas, etc.)
/README.md                      # Docuemntos de guia de la biblioteca
----------------------------------------------------------------------------------------------------


2. Cómo importar los estilos
Para usar esta biblioteca en tu proyecto, importa los archivos CSS en el <head> de tu HTML en este orden:


<link rel="stylesheet" href="styles/variables/variables.css" />
<link rel="stylesheet" href="styles/base/base.css" />
<link rel="stylesheet" href="styles/components/components.css" />
Es importante importar primero las variables, luego los estilos base, y finalmente los estilos de componentes para que los estilos hereden correctamente.

---------------------------------------------------------------------------------------------------------

3. Descripción y estructura de los componentes
Botones
Clases: .btn, .btn--primario, .btn--secundario

Estados: :hover, :disabled

Ejemplo:

<button class="btn btn--primario">Primario</button>
<button class="btn btn--secundario">Secundario</button>
<button class="btn" disabled>Desactivado</button>
Tarjetas
Contenedor .card

Elementos internos .card__titulo, .card__contenido

Ejemplo:

html
Copiar código
<div class="card">
  <h3 class="card__titulo">Título</h3>
  <p class="card__contenido">Contenido de la tarjeta</p>
</div>
Formularios
Clases: .formulario

Elementos nativos: <input>, <select>, <checkbox>, <button>

Ejemplo:

<form class="formulario">
  <input type="text" placeholder="Nombre" />
  <select>
    <option>Opción 1</option>
    <option>Opción 2</option>
  </select>
  <label><input type="checkbox" /> Acepto términos</label>
  <button class="btn btn--primario" type="submit">Enviar</button>
</form>
Navbar responsivo
Contenedor .navbar

Menú .navbar__menu con enlaces <a>

Ejemplo:

<header class="navbar">
  <h1 class="navbar__title">Título</h1>
  <nav class="navbar__menu">
    <a href="#inicio">Inicio</a>
    <a href="#componentes">Componentes</a>
  </nav>
</header>
Modal (ventana emergente)
Contenedor .modal

Contenido .modal__contenido

Clase para mostrar .modal--visible

Ejemplo:


<button onclick="document.querySelector('.modal').classList.add('modal--visible')" class="btn btn--primario">Abrir Modal</button>

<div class="modal">
  <div class="modal__contenido">
    <span onclick="document.querySelector('.modal').classList.remove('modal--visible')" class="modal__cerrar">&times;</span>
    <h3>Modal</h3>
    <p>Contenido modal...</p>
  </div>
</div>
Tooltip
Elemento con clase .tooltip

Usa atributo data-tooltip para texto emergente

Ejemplo:


<button class="tooltip" data-tooltip="Texto de ayuda">Pasa el mouse</button>
Acordeón
Contenedor .acordeon

Ítems con .acordeon__item

Botón .acordeon__cabecera que alterna el contenido .acordeon__contenido

Ejemplo:


<div class="acordeon">
  <div class="acordeon__item">
    <button class="acordeon__cabecera">Título</button>
    <div class="acordeon__contenido">Contenido desplegable</div>
  </div>
</div>
<script>
  document.querySelectorAll('.acordeon__cabecera').forEach(btn => {
    btn.addEventListener('click', () => {
      btn.classList.toggle('activo');
      let contenido = btn.nextElementSibling;
      contenido.style.display = contenido.style.display === 'block' ? 'none' : 'block';
    });
  });
</script>

------------------------------------------------------------------------------------------

4. Responsividad y accesibilidad
El diseño usa media queries para adaptar el menú navbar a pantallas pequeñas.

Los botones y enlaces tienen estados hover y focus para accesibilidad.

Modal y acordeón tienen interacción por teclado y ratón.

Las variables CSS permiten personalizar colores y tipografías fácilmente.

