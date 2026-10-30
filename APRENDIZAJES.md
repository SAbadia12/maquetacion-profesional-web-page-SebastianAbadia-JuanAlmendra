# **Integrantes:** Sebastián Abadía y Juan Sebastian Almendra

# Aprendizajes e inconvenientes del desarrollo



Este documento resume los principales aprendizajes al construir la página de Disney con HTML y CSS, los problemas que aparecieron y el apoyo recibido mediante la interacción con una inteligencia artificial.

## Aprendizajes

- **Revisar el recurso original antes de cambiar muchos estilos.** La imagen del banner parecía dejar márgenes blancos y al principio se revisaron el margen del `body`, el ancho de `.banner` y el padding. Al final se identificó que los bordes blancos ya venían incluidos en la propia imagen. Por eso, aunque el contenedor ocupe todo el ancho, esos bordes siguen apareciendo: forman parte de los píxeles del archivo, no son un margen creado por CSS.
- **Distinguir el tamaño del contenedor del contenido de una imagen.** `width: 100%` y `background-size: cover` controlan cómo se adapta la imagen al contenedor, pero no eliminan automáticamente un borde incorporado al archivo. Para corregirlo hay que recortar o editar el recurso, o ajustar su encuadre con CSS si el diseño lo permite.
- **Comprobar que los nombres de clases coincidan.** Se encontró una diferencia entre `banner-Logo` en el HTML y `.banner-logo` en CSS. Como las mayúsculas importan en los nombres de clase, el estilo no se aplicaba al logo hasta unificar el nombre.
- **Usar Grid para organizar tarjetas.** Las secciones de tienda, Disney+ y parques se organizaron con CSS Grid para controlar columnas y separación entre imágenes.
- **Diseñar también para pantallas pequeñas.** Las media queries permiten pasar de varias columnas a una o dos cuando el espacio disponible es menor.
- **Comparar los bordes entre secciones.** Para alinear las imágenes de Disney+ con la sección superior, se igualaron los márgenes laterales de las cuadrículas y se verificó la posición de sus extremos en el navegador.
- **Usar HTML semántico y descripciones alternativas.** Las secciones, artículos, títulos y textos `alt` hacen que el contenido sea más claro y accesible.

## Inconveniente principal: los bordes blancos del banner

El objetivo era que el banner se viera de extremo a extremo, como en la referencia. Se hicieron ajustes al ancho y al espaciado de la página, pero esos cambios no quitaban el borde visible. La revisión de la imagen permitió encontrar la causa: el archivo del banner ya tenía bordes blancos incorporados.

La lección fue no asumir que todo espacio visible proviene del layout. Conviene inspeccionar el recurso original y separar estas dos posibilidades:

1. **Espacio generado por la página:** margen del navegador, padding, ancho del contenedor o desbordamiento.
2. **Espacio incluido en el archivo:** borde o fondo que forma parte de la imagen.

En este caso, el origen final identificado fue el segundo. Para obtener un banner sin esos bordes, habría que usar una versión recortada de la imagen o ajustar el encuadre sin perder elementos importantes.

## Otros inconvenientes y soluciones

- **Estilos que no se reflejaban:** se comprobó la correspondencia exacta entre selectores CSS y clases HTML.
- **Sección Disney+ incompleta:** se agregó el título que faltaba y se estructuraron las tres tarjetas con imagen, descripción y enlace.
- **Alineación de las imágenes Disney+:** se ajustó el ancho de la cuadrícula para que sus imágenes exteriores coincidieran con los bordes de la fila de tarjetas superior.
- **Sección de parques vacía:** se incorporaron dos tarjetas con las imágenes disponibles, texto y enlaces, y se agregó un diseño adaptable.
- **Verificación del resultado:** se abrió la página en el navegador para comprobar que las imágenes cargaran, que las secciones aparecieran y que las columnas tuvieran la distribución esperada. También se usó `git diff --check` para revisar errores de espacios en los cambios.

## Interacción y apoyo de la inteligencia artificial

El trabajo se realizó de forma iterativa: se compartieron capturas de referencia y se describió qué debía cambiar en cada paso. La IA apoyó en:

1. Revisar el HTML, CSS y los nombres de las imágenes existentes antes de proponer cambios.
2. Identificar posibles causas de los márgenes y problemas visuales del banner, y considerar que el borde podía formar parte del archivo de imagen.
3. Implementar los estilos y el marcado para las secciones de Disney+, películas y Disney Parks según las referencias compartidas.
4. Ajustar la alineación de las cuadrículas y añadir reglas responsivas para tamaños de pantalla menores.
5. Validar visualmente en el navegador elementos como el ancho de las secciones, la carga de imágenes y el número de tarjetas.

Las capturas y las indicaciones del usuario guiaron cada ajuste. La IA propuso y verificó cambios, mientras que la decisión sobre el aspecto deseado se mantuvo basada en las referencias proporcionadas.

## Recomendaciones para futuros cambios

- Inspeccionar primero los archivos de imagen, incluyendo sus dimensiones y bordes, antes de intentar corregirlos únicamente con CSS.
- Mantener nombres de clase consistentes y en minúsculas.
- Reutilizar patrones de tarjetas cuando el contenido tenga una estructura similar.
- Probar cada sección en escritorio y móvil después de modificar el layout.
- Comparar la página con la captura usando referencias concretas: alineación, proporción de las imágenes, separación y color de fondo.
