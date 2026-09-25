# Marca · CÓDIGO GLP-1

Documento de referencia. Estos valores no se cambian entre números: el reconocimiento de la
revista depende de que el lector vea siempre lo mismo.

## Paleta (congelada a partir del Núm. 03)

| Uso | Hex |
|---|---|
| Azul de marca (fondos oscuros, texto principal) | `#0E2036` |
| Azul intermedio (bandas, separadores sobre azul) | `#1B3149` |
| Línea sobre azul | `#27405A` |
| Dorado claro (acentos y cifras sobre azul) | `#C9A45E` |
| Dorado oscuro (texto y etiquetas sobre crema o blanco) | `#8A5F27` |
| Dorado oscuro para texto grande (24 px o más, sobre claro) | `#A87B33` |
| Crema (fondo de página) | `#F7F4ED` |
| Crema profunda (bandas, aviso legal) | `#EFEBE1` |
| Papel (fondo de tarjetas) | `#FFFFFF` |
| Texto sobre crema | `#24384D` |
| Texto secundario sobre crema | `#5C6B7C` |
| Texto secundario sobre azul | `#93A3B5` |
| Verde de señal (semáforos) | `#1E6E62` |
| Ámbar de señal (semáforos) | `#9A6A12` |
| Rojo de señal (semáforos) | `#B4432C` |

Nota de accesibilidad: sobre fondos claros no se usa `#C9A45E` para texto (contraste 1.9:1
sobre blanco, 2.1:1 sobre crema). Para texto pequeño sobre crema o blanco el dorado es
`#8A5F27` (5.1:1); para texto de 24 px o más, `#A87B33` (3.5:1). Los números 02 y 03, la
guía, la portada del sitio y la página de erratas pasan AA en texto y en texto grande, medido
recorriendo cada nodo de texto del DOM contra su fondo efectivo. Si se agrega un color nuevo,
se mide antes de publicarlo.

## Tipografía

- Display y texto de interfaz: **Archivo** (400–800, e itálica 400–600).
- Texto de lectura y citas: **Source Serif 4** (400 y 600, itálica 400).
- Los archivos woff2 viajan incrustados en el HTML, **solo con el subconjunto `latin`**
  (U+0000–00FF y signos de puntuación). El subconjunto `latin-ext` se retiró porque ningún
  número lo usa: son 285 KB por archivo. Si algún número futuro necesita caracteres
  centroeuropeos o vietnamitas (por ejemplo el apellido de un autor), hay que volver a
  incrustar la variante `latin-ext` de esa familia o el glifo caerá a una fuente del sistema.
- No se cargan tipografías desde servidores de terceros, ni de Google ni de ningún CDN.

## Reglas técnicas de cada número

1. Sin dependencias de terceros: sin CDN, sin analítica, sin cookies, sin fuentes remotas,
   sin píxeles. Todo lo que carga la página se sirve desde este mismo dominio, y se verifica
   con el inspector de red antes de publicar: el número correcto de peticiones externas es cero.
2. El contenido va en el HTML, no se inyecta con JavaScript. La revista se lee completa con
   JS desactivado; JavaScript solo mueve el menú del índice y la barra de progreso. Cada
   archivo con JS lleva un `<noscript>` con el índice en enlaces directos y el correo.
3. `<html lang="es-MX">`, `meta description`, `link canonical`, Open Graph y Twitter Card
   completos, con una imagen de 1200×630 alojada en este mismo repositorio (nunca en un banco
   de imágenes remoto: Facebook no lee base64 y un tercero puede borrar el archivo).
4. Datos estructurados JSON-LD: `MedicalWebPage` en cada número, `isPartOf: Periodical` con
   su `issueNumber`, y `CollectionPage` con `hasPart` en la portada del sitio.
5. Tablas con `<table>`, `<thead>`, `<th scope>` y `<caption>`. Nunca cuadrículas de `<div>`.
6. Tamaño de letra mínimo: 13 px en la revista y en la portada del sitio.
7. Barra de progreso de lectura y menú de índice con `aria-expanded` / `aria-controls`.
8. Cada capítulo cierra con "Qué no dice esta evidencia" y con su fecha de revisión.
9. Fotografías: archivos `.webp` externos, con `loading="lazy"` (salvo la primera, que va
   `eager` con `fetchpriority="high"`), `decoding="async"` y `width`/`height` declarados.
   La primera foto de cada número no pasa de 1440 px de ancho; las demás, de 1500 px.
10. Ninguna cifra se sostiene en una imagen. Las fotos son de apertura y su función es
    editorial; la información la llevan las gráficas, de elaboración propia.
11. A partir del Núm. 04 (septiembre de 2026) las aperturas de capítulo y la portada son
    ilustraciones vectoriales SVG incrustadas en el HTML, dibujadas a partir del dato central
    de cada reportaje, en lugar de fotografía. La tarjeta `portada-num04.jpg` reproduce esa
    misma ilustración. Si un número vuelve a usar fotografía, aplican las reglas 9 y 10.
12. El Núm. 05 (octubre de 2026) vuelve a la fotografía, con las reglas 9 y 10. Las aperturas
    de capítulo son a doble página: el texto va sobre azul y la foto a sangre en la otra mitad,
    alternando el lado de un capítulo a otro. Nunca hay texto ni cifras encima de una foto. Las
    fotos salen de Pexels (licencia libre, sin atribución obligatoria), se acredita igual al
    fotógrafo y se marcan como «Imagen ilustrativa». La tarjeta `portada-num05.jpg` sigue la
    misma regla: texto sobre azul a la izquierda, foto a la derecha.
13. Las gráficas del Núm. 05 son HTML y CSS (barras, gráfica de bosque y barras apiladas), sin
    SVG ni imágenes. Colores nuevos, solo para elementos gráficos y no para texto: `#B7C2CE`
    (barra del comparador) y `#EFEBE1` (riel de las barras). Cada valor va escrito junto a su
    barra, así que la gráfica nunca es la única forma de leer el dato. Para texto pequeño en
    ámbar (las etiquetas «comunicado» y «congreso», y los avisos de corrección) se usa `#8C600F`,
    que pasa AA sobre blanco (5.5:1), crema (5.0:1) y crema profunda (4.6:1); el ámbar de señal
    `#9A6A12` queda para semáforos y elementos gráficos.
14. Desde el Núm. 05, las tablas y las referencias llevan etiqueta de evidencia (estudio
    publicado, guía o consenso, documento oficial, comunicado, congreso, prensa o fuente
    secundaria), y cada capítulo abre con un recuadro «En 60 segundos».
15. Nitidez en cualquier pantalla. Las fotos se preparan desde el original de mayor resolución
    que ofrezca el banco, nunca desde una copia reducida, y cada una se publica en varios anchos
    con `srcset` y `sizes`, para que el navegador descargue solo lo que su pantalla necesita. El
    archivo de `src` sigue la regla 9 (la primera foto hasta 1440 px; las demás, hasta 1500 px) y
    es el que declara `width` y `height`; las versiones de alta densidad (hasta 2400 px en las
    aperturas) solo las piden las pantallas retina y las tabletas. La portada usa dirección de
    arte con `<picture>`: encuadre vertical 4:5 en pantallas anchas y horizontal 5:4 en tableta
    y celular, para que el título quede a la vista en la primera pantalla. Antes de publicar se
    comprueba en compu, iPad y celular que ninguna foto se muestre con menos píxeles de los que
    pide la pantalla, y la foto de portada se elige nítida en el punto de interés: una foto con
    desenfoque de origen no se corrige con más resolución.

## Erratas

- El registro vive en `erratas.html` y se enlaza desde el pie de **todos** los archivos y
  desde el aviso legal.
- Se anotan errores de dato, de atribución, de alcance y enlaces caídos. No se anotan cambios
  de redacción, tipografía, imágenes ni maquetación que no alteren ningún dato.
- Las correcciones hechas **antes** de publicar no son erratas: son edición, y no se anotan.
  El registro arranca en cero con cada número.
- Compromiso público: corregir en menos de 72 horas desde un aviso verificable, dejando
  escrito lo que decía la versión anterior.

## Nombres de archivo

- `index.html` — portada del sitio. Lista las ediciones y nunca se sobrescribe con un número.
- `CODIGO-GLP1-<Mes>-<Año>.html` — una edición. Nunca vive solo en la raíz.
- `Guia-<Mes>-<Año>.html` — cuadernillo imprimible de la edición.
- `portada-num<NN>.jpg` — tarjeta de 1200×630 para Open Graph.
- `<mes>-<NN>-<tema>.webp` — fotografías de apertura de esa edición.
- `<mes>-<año>.html` — liga corta que redirige a la edición (`agosto-2026.html`, `septiembre-2026.html`).
- `erratas.html`, `robots.txt`, `sitemap.xml`, `marca.md` — permanentes.

## Al publicar un número nuevo

1. Crear `CODIGO-GLP1-<Mes>-<Año>.html` con su `canonical`, su Open Graph y su `portada-num<NN>.jpg`.
2. Actualizar `index.html`: mover el número anterior al archivo y poner el nuevo como actual.
3. Actualizar los pies de página de todos los archivos con la edición nueva.
4. Añadir las URLs nuevas a `sitemap.xml` y actualizar `lastmod`.
5. Abrir `erratas.html` y agregar el bloque del número nuevo en cero.
6. Verificar: peticiones externas = 0, contraste = 0 fallos, sin JS se lee todo, y la tarjeta
   de Open Graph se ve bien en el depurador de Facebook antes de compartir el enlace.

## Nota sobre `robots.txt`

GitHub Pages solo respeta `robots.txt` en la raíz del dominio (`glp1mexico.github.io/robots.txt`),
no dentro de la carpeta de un repositorio. El archivo que está aquí es correcto y sirve de
referencia, pero para que un rastreador lo lea hay que copiarlo al repositorio
`glp1mexico.github.io`. El `sitemap.xml` sí funciona: se envía a mano en Search Console.
