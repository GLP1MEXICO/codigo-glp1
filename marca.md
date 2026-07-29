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
| Dorado oscuro (acentos y etiquetas sobre crema) | `#8A5F27` |
| Crema (fondo de página) | `#F7F4ED` |
| Papel (fondo de tarjetas) | `#FFFFFF` |
| Texto sobre crema | `#24384D` |
| Texto secundario sobre crema | `#5C6B7C` |
| Texto secundario sobre azul | `#93A3B5` |

Nota de accesibilidad: sobre fondos claros no se usa `#C9A45E` para texto (contraste 1.9:1).
Para texto pequeño sobre crema o blanco, el dorado es `#8A5F27` (5.1:1). Todo el número 03
pasa AA en texto y en texto grande; si se agrega un color nuevo, se verifica antes.

## Tipografía

- Display y texto de interfaz: **Archivo** (400–800, e itálica 400–600).
- Texto de lectura y citas: **Source Serif 4** (400 y 600, itálica 400).
- Los archivos woff2 viajan incrustados en el HTML (subconjuntos latin y latin-ext).
  No se cargan tipografías desde servidores de terceros.

## Reglas técnicas de cada número

1. Un solo archivo HTML por edición, sin dependencias externas: sin CDN, sin analítica,
   sin cookies, sin fuentes remotas.
2. El contenido va en el HTML, no se inyecta con JavaScript. La revista se lee con JS desactivado.
3. `<html lang="es-MX">`, `meta description`, `link canonical`, Open Graph y Twitter Card
   completos, con una imagen de 1200×630 alojada en este mismo repositorio.
4. Tablas con `<table>`, `<thead>`, `<th scope>` y `<caption>`. Nunca cuadrículas de `<div>`.
5. Tamaño de letra mínimo: 13 px.
6. Barra de progreso de lectura y menú de índice con `aria-expanded` / `aria-controls`.
7. Cada capítulo cierra con "Qué no dice esta evidencia" y con su fecha de revisión.

## Archivos del sitio

- `index.html` — Núm. 02 · Julio 2026
- `CODIGO-GLP1-Agosto-2026.html` — Núm. 03 · Agosto 2026
- `agosto-2026.html` — enlace corto que redirige al Núm. 03
- `Guia-Agosto-2026.html` — cuadernillo imprimible del Núm. 03
- `Manual-Nutricional-GLP1.pdf` — descargable del Núm. 02
- `portada-num02.jpg`, `portada-num03.jpg` — tarjetas sociales 1200×630
