## Auditoría a Pablo Escandon (Ficha N.º 11)

## 1. Tabla de requisitos 

| Requisito | Esperaba | Encontré | Resultado |
| :--- | :--- | :--- | :--- |
| **Taller mecánico** | Contenido organizado para presentar el taller, sus servicios, una tabla y un formulario. | El proyecto incluye una cabecera, contenido principal, secciones de servicios, una tabla y un formulario. | Cumple |
| **Teléfono con `pattern`** | Un campo de teléfono con un patrón que valide el formato solicitado para celulares ecuatorianos. | El campo de teléfono incluye `type="tel"` y `pattern` en `index.html`, líneas 156–164. Acepta el formato nacional que empieza con `09` y el internacional que empieza con `+593`, seguidos de nueve dígitos. El patrón valida el formato escrito, pero no confirma que el número exista o esté activo. | Cumple |
| **Breakpoint de 768 px** | Una regla `@media (min-width: 768px)` que reorganice el diseño en pantallas más anchas. | La regla está en `css/estilos.css`, línea 270. A partir de ese ancho cambia la distribución de los servicios y del área de contacto. | Cumple |
| **Menú sin clases ni IDs** | Un menú cuyos estilos se apliquen con selectores estructurales y de atributo, sin depender de clases ni IDs. | Los elementos del menú no tienen clases ni IDs. En `css/estilos.css` se usan selectores de elementos y el atributo `href`, por ejemplo `header nav ul li a[href^="#"]`. | Cumple |


## 2. Informe de auditoría

| N.º | Requisito | Ubicación (archivo y línea o selector) | Hallazgo | Norma que incumple | Evidencia | Severidad |
| :---: | :--- | :--- | :--- | :--- | :--- | :---: |
| 1 | Contraste mínimo de texto | `css/estilos.css`, líneas 8 y 82–84 | En `hover` y `focus`, el texto blanco del menú queda sobre un fondo azul con contraste insuficiente. | WCAG 2.2, criterio 1.4.3: mínimo 4,5:1 para texto normal. | El fondo es `#3b82f6` y el texto es blanco. El contraste calculado es 3,68:1. | Media |
| 2 | Propósito de los campos personales | `index.html`, líneas 151, 154 y 157–164 | Los campos de nombre, correo y teléfono no identifican su propósito con `autocomplete`. | WCAG 2.2, criterio 1.3.5. | Los campos no incluyen `autocomplete="name"`, `autocomplete="email"` ni `autocomplete="tel"`. | Baja |
| 3 | Validación nativa del formulario | `index.html`, líneas 165–170 | La fecha de la cita es obligatoria, pero no tiene un límite `min`; se puede elegir una fecha pasada. | Requisito base 2 de la Parte 1: validación nativa con `required`, `pattern` y límites `min/max`, según el campo. | El campo tiene `type="date"` y `required`, pero no define `min` ni `max`. | Baja |
| 4 | Texto alternativo de imágenes | `index.html`, línea 10 | El texto alternativo del banner solo dice “Banner Taller Mecánico” y no describe la imagen. | WCAG 2.2, criterio 1.1.1: alternativa adecuada para contenido no textual. | La imagen muestra un automóvil, pero el `alt` solo indica que es un banner del taller. Si es decorativa, debería llevar `alt=""`; si informa, debería describir lo que muestra. | Baja |