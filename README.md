# Cuaderno digital de síntesis — Unidad 1

**Asignatura:** Diseño de Circuitos  
**Unidad:** Análisis de lógica combinacional con diseño clásico  
**Universidad:** Universidad Nacional de Loja  
**Docente:** Ing. Luis Darío Sinche Cueva, Mg.  
**Periodo de la portada de clase:** Septiembre 2026 – marzo 2027

Proyecto educativo estático, elaborado a partir de **nueve PDF originales** aportados para las semanas 1–4. La **semana 5 está pendiente**: no incluye ejercicios, fórmulas ni temas supuestos.

## 1. Estructura exacta del proyecto

```text
cuaderno-sintesis-unidad-1/
├── index.html
├── README.md
├── .nojekyll
├── css/
│   └── estilos.css
├── js/
│   ├── contenido.js
│   └── app.js
└── assets/
    ├── diapositivas/
    │   ├── semana-01.pdf
    │   ├── semana-02.pdf
    │   ├── semana-03.pdf
    │   ├── semana-03-sesion-02.pdf
    │   └── semana-04.pdf
    ├── practicas/
    │   ├── ape-01.pdf
    │   ├── ape-02.pdf
    │   ├── ape-03.pdf
    │   └── ape-04.pdf
    └── circuitos/
        ├── 01-and.svg, 01-or.svg, 01-not.svg, ...
        ├── 02-alarma-canonica.svg, ...
        ├── 03-kmap-4-variables-sop.svg, ...
        └── 04-sumador-restador-4-bits.svg, ...
```

**32 SVG completos** están incluidos en `assets/circuitos/`. Todos pueden ampliarse desde las secciones académicas o desde el catálogo «Técnicas y circuitos resueltos».

El archivo `CODIGO_COMPLETO.md` también está disponible con el código íntegro del HTML, CSS, JS y todos los SVG, identificado por ruta. Los PDF son archivos binarios originales, no código fuente.

## 2. Cómo abrirlo localmente

1. Descomprime el ZIP y conserva toda la estructura de carpetas.
2. Abre `index.html` con Chrome, Edge o Firefox.
3. Comprueba la portada, el índice y los apartados.
4. Los PDF incluidos pueden abrirse con «Abrir» o «Descargar». Algunos navegadores restringen la previsualización integrada de los PDF cuando el protocolo es `file://`; eso **no significa** que el PDF no exista.
5. Para verificar la publicación completa, utiliza GitHub Pages por HTTPS. No hace falta Node.js, npm, React, base de datos ni dependencias.

## 3. Cómo publicarlo en GitHub Pages

1. En GitHub crea un repositorio nuevo, por ejemplo `cuaderno-sintesis-unidad-1`.
2. Sube **el contenido de la carpeta** del proyecto a la raíz del repositorio: `index.html`, `css/`, `js/`, `assets/`, `README.md` y `.nojekyll`. No subas solamente el ZIP.
3. Abre **Settings → Pages**.
4. En **Build and deployment**, elige **Deploy from a branch**.
5. Selecciona `main` y **/(root)**. Guarda.
6. Cuando termine el despliegue, abre **Visit site**. Su URL será aproximadamente `https://TU-USUARIO.github.io/cuaderno-sintesis-unidad-1/`, según el nombre real de tu repositorio.
7. Las rutas del sitio son relativas (`./assets/...`), por lo que funcionan debajo del nombre del repositorio.

Documentación oficial: <https://docs.github.com/es/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site>

### Precaución antes de publicar

Algunas prácticas originales incluyen nombres de estudiantes y otros datos en sus portadas. **GitHub Pages es públicamente accesible.** Revisa si dispones de autorización para publicar esos PDF. Si no, prepara versiones anonimizadas para un repositorio público antes de subirlos. No incluyas documentos con datos personales privados sin permiso.

## 4. Cómo añadir o reemplazar diapositivas

- Semana 1: `assets/diapositivas/semana-01.pdf`
- Semana 2: `assets/diapositivas/semana-02.pdf`
- Semana 3, sesión 1: `assets/diapositivas/semana-03.pdf`
- Semana 3, sesión 2: `assets/diapositivas/semana-03-sesion-02.pdf`
- Semana 4: `assets/diapositivas/semana-04.pdf`
- Las prácticas están en `assets/practicas/ape-01.pdf` hasta `ape-04.pdf`.

Si reemplazas uno de esos archivos y mantienes su nombre y ruta, los enlaces actuales se conservarán. Si agregas otro PDF, inserta un objeto en el arreglo `pdfs` de `js/contenido.js`, indicando `id`, `semana`, `nombre`, `ruta`, `paginas` y `clase`.

**Semana 5:** coloca el futuro PDF original en `assets/diapositivas/semana-05.pdf` y, solo cuando hayas revisado sus páginas, agrega su registro al manifiesto y sustituye el texto pendiente en el apartado `s5-pendiente` de `js/contenido.js`. No enlaces a un PDF inexistente.

En la biblioteca, la aplicación usa peticiones HTTP `HEAD` para verificar las rutas disponibles en GitHub Pages. Si falta un archivo, muestra un aviso y deshabilita el botón del PDF. No crea nombres inventados ni enlaces simulados.

## 5. Cómo añadir, corregir o quitar diagramas

Todos los SVG están guardados en `assets/circuitos/` con nombres descriptivos. Se diseñaron con fondo cuadriculado y símbolos de compuertas o bloques de subcircuito. Algunos diagramas usan rótulos para identificar señales repetidas y compuertas NOT donde hacen falta inversiones.

Para cambiar un circuito, reemplaza el SVG correspondiente sin alterar su nombre. Para agregar otro, crea el SVG y registra su descripción en el arreglo `circuitos` de `js/contenido.js`. Después agrega su explicación en el apartado semanal. **Verifica la tabla de verdad antes de publicar.**

Los SVG **no** son archivos `.circ` de Logisim Evolution. En esta entrega no se incluyen archivos `.circ`, ya que no se ha validado su compatibilidad mediante una instalación y una simulación del programa. Las capturas y resultados de los reportes de prácticas son fuentes, no pruebas de ejecución de estos SVG.

## 6. Qué hace cada archivo de código

| Archivo | Responsabilidad |
|---|---|
| `index.html` | Estructura semántica, menús, botones, búsqueda y contenedores accesibles. |
| `css/estilos.css` | Interfaz académica, responsive y estilos de impresión A4. |
| `js/contenido.js` | Temario, contenido académico, diagramas, tabla y manifiestos PDF. |
| `js/app.js` | Navegación, progreso, buscador, comprobación PDF, formulario de dudas, simulador de compuertas y almacenamiento local. |
| `assets/circuitos/*.svg` | Diagramas independientes de lógica digital. |

Para adaptar el texto modifica únicamente `js/contenido.js`. Las secciones se muestran de forma automática en el índice y en la navegación lateral. No es necesario editar HTML para introducir un nuevo tema.

## 7. Comprobación de funcionamiento

- [ ] La portada se muestra y el campo de estudiante permite escribir y conservar el valor.
- [ ] El índice enlaza directamente con cada tema y el menú lateral permite saltar libremente.
- [ ] «Inicio», «Anterior», «Siguiente» y «Volver al índice» funcionan; «Anterior» se desactiva en portada y «Siguiente» al final.
- [ ] El indicador de sección actual y el progreso se actualizan al desplazarse.
- [ ] Ctrl + K abre el buscador y permite saltar a un tema.
- [ ] La tabla de compuertas de dos entradas coincide con la demostración interactiva.
- [ ] Los 32 SVG están visibles y se amplían sin pixelación.
- [ ] Los nueve PDF muestran «Archivo disponible» en Pages, se pueden abrir y descargar.
- [ ] El visor integrado abre y cierra sin dejar botones inactivos.
- [ ] La semana 5 muestra «Pendiente» y no ofrece un archivo inexistente.
- [ ] Se pueden agregar, editar, resolver, volver a marcar pendientes y eliminar dudas.
- [ ] Las dudas pueden exportarse e importarse mediante JSON.
- [ ] En móvil el menú se abre y cierra; no existe desplazamiento horizontal.
- [ ] Al imprimir se ocultan menús, botones y visores, manteniendo el texto y los diagramas.

**Guardado de dudas:** se utiliza `localStorage` del navegador, no un servidor. Si limpias los datos del navegador o abres el sitio en otro dispositivo, las notas no aparecen automáticamente allí. Exporta un JSON para hacer una copia de seguridad. Tampoco se mezclan las dudas con el código fuente público.

## 8. Notas de exactitud académica

Los ejemplos proceden de las diapositivas y prácticas adjuntas, con referencias de documento y página incluidas en cada apartado. Las expresiones se verificaron con tablas de verdad enumeradas, incluidos:

- Alarma de tres sensores: `F=AB+AC+BC`, activa en 3,5,6,7.
- Comparación práctica 002: `F=A+BC'` para AB (dos bits) mayor que C (un bit).
- Karnaugh de cuatro variables: equivalencia SOP/POS de `Σm(0,1,2,5,8,9,10)`.
- BCD primo: `F=B'C+BD` para los diez dígitos BCD válidos; 10–15 son indiferentes.
- Sumador completo: `S=A⊕B⊕Cin` y `Cout=AB+A·Cin+B·Cin`.
- Sumador/restador: `Bᵢ⊕M`, `Cin₀=M`, `V=C3⊕C4`.

Hay diagramas que muestran un subcircuito HA o FA como un bloque; su lógica interna está representada en otro SVG. En el comparador de magnitud de dos bits, la expresión algebraica es una derivación explícita de la regla verbal enseñada en la diapositiva, no una fórmula que se atribuya textualmente a ella.

**No se añaden referencias bibliográficas ajenas a los nueve PDF recibidos.**
