<div align="center">

# SEEKING.LOC

**Portal inmobiliario para Córdoba, Argentina: buscá, compará y entendé el precio real de cualquier propiedad, sin salir de una sola página.**

![Estado](https://img.shields.io/badge/estado-prototipo%20funcional%20v44-1E6B3C)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?logo=javascript&logoColor=black)
![MapLibre](https://img.shields.io/badge/MapLibre%20GL-4.7.1-396CB2)
![deck.gl](https://img.shields.io/badge/deck.gl-9.2.11-0B2545)
![Accesibilidad](https://img.shields.io/badge/axe--core-0%20problemas%20graves-1E6B3C)

**Demo en vivo disponible a pedido** · [Capturas](#capturas) · [Cómo verlo](#cómo-verlo) · [Desafíos técnicos](#desafíos-técnicos-resueltos)

![Portada de SeekingLoc](docs/capturas/portada.png)

</div>

---

## Resumen

SeekingLoc es un portal para **alquilar, comprar y vender cualquier tipo de propiedad en la provincia de Córdoba**: deptos, casas, dúplex/PH, terrenos, cocheras, locales, oficinas, galpones y depósitos.

Nació de una frustración concreta: en los portales actuales cada aviso abre una pestaña nueva, el mapa depende de Google, los datos vienen incompletos y nadie te dice si el precio es razonable. SeekingLoc propone otra cosa:

- **Todo pasa en una sola página.** Listado, mapa, ficha, comparador y calculadora conviven sin abrir ventanas.
- **Un buscador que entiende lenguaje natural**, incluso con errores de tipeo: *"depto 2 ambientes con balcón y mascotas en Nueva Córdoba hasta 700 mil"*.
- **Un mapa propio de toda la provincia**, con calles, barrios, relieve, paradas de colectivo y comercios cercanos, sin depender de Google Maps.
- **Fichas estandarizadas**: plano, servicios con su detalle (por ejemplo, si el agua es potable) y la comparación del precio por m² con avisos parecidos.
- **Sin registro obligatorio.** Se explora libremente; el registro aparece solo si la persona lo pide.

> **Estado:** prototipo funcional (versión 44) con 1.500 avisos de prueba ubicados en **direcciones reales**. Los avisos, los anunciantes y los precios son de ejemplo hasta el lanzamiento.

---

## Capturas

| Listado (escritorio) | Mapa propio de Córdoba |
|---|---|
| ![Listado con filtros](docs/capturas/listado.png) | ![Mapa con barrios, rutas y calculadora](docs/capturas/mapa.png) |

| Ficha: "¿Está bien de precio?" | Celular |
|---|---|
| ![Ficha con precio por m², servicios y plano](docs/capturas/ficha-precio-m2.png) | <img src="docs/capturas/celular.png" alt="Versión para celular" width="300"> |

---

## Funcionalidades principales

| Área | Qué hace |
|---|---|
| **Búsqueda** | Intérprete propio de lenguaje natural: tipo, ambientes, barrio, calle y altura, puntos de referencia ("cerca de la UNC"), presupuesto y requisitos (balcón, mascotas, cochera, seguridad 24 h…). Tolera errores de tipeo. Cuando no hay resultados, explica por qué y ofrece qué filtro quitar, con cuántos avisos aparecerían. |
| **Mapa** | Provincia completa con MapLibre GL: calles, manzanas, barrios, rutas, ríos, relieve, espacios verdes, paradas y recorridos de colectivo. Capas que se prenden y apagan, y dibujo de zona a mano alzada (también con teclado). |
| **Listado y filtros** | Diseño inspirado en Booking: filtros fijos a la izquierda, contadores en vivo, histograma de precios, 12 avisos por página y orden por destacados, precio o novedad. |
| **Ficha** | Galería por ambiente, precio y expensas, características, servicios con tilde o cruz, plano a escala, comercios y servicios cercanos en un radio, y comparación del precio por m² con la mediana de la zona. |
| **Herramientas para quien busca** | Calculadora de costo real de un alquiler (ingreso, ajustes por IPC y total del contrato), comparador de guardados, búsquedas guardadas que marcan los avisos nuevos y "Seguí donde quedaste". |
| **Publicación** | Formulario guiado por tipo de propiedad, con fotos mínimas por ambiente, servicios específicos y plano dibujable en hoja cuadriculada. No se puede guardar con campos vacíos, para que todos los avisos lleguen completos. |
| **Panel de administración** | Métricas en tiempo real e históricas por aviso, por anunciante y por botón; embudo de interacción, búsquedas sin resultado y edición del sitio (pausar avisos, banners, destacados). Solo se habilita para el dueño del sitio. |

---

## Stack tecnológico

**Frontend (todo en un único `index.html`, sin frameworks ni paso de compilación)**
- **HTML5, CSS3 y JavaScript vanilla**: unas 8.400 líneas y cerca de 490 funciones, encapsuladas en un módulo autoejecutable (IIFE).
- **[MapLibre GL JS 4.7.1](https://maplibre.org/)**: motor de mapas vectoriales de código abierto, alternativa a Google Maps.
- **[deck.gl 9.2.11](https://deck.gl/)**: capas de visualización de datos sobre el mapa.
- **Tipografías**: Outfit (títulos) y Manrope (texto), desde Google Fonts.
- **Datos geográficos en GeoJSON**, partidos por departamento y por celdas para que se descarguen solo cuando se necesitan.

**Datos y herramientas de desarrollo**
- **Python**: procesamiento de datos geográficos (calles, manzanas, comercios, puntos de referencia), geocodificación de direcciones reales y generación de los 1.500 avisos de prueba.
- **Node.js, Playwright y axe-core**: batería de pruebas automatizadas de interfaz, rendimiento y accesibilidad, en escritorio y celular.
- **Claude (Anthropic)**: asistente de IA para desarrollo, con quien se programó el proyecto bajo mi dirección de producto y diseño.
- **claude.ai Artifacts**: hosting del prototipo, que además aporta base de datos, presencia en tiempo real e identificación del usuario para el panel de administración.

**Fuentes de datos**
- IDECOR (Infraestructura de Datos Espaciales de la Provincia de Córdoba) y Municipalidad de Córdoba.
- © Colaboradores de [OpenStreetMap](https://www.openstreetmap.org/copyright), bajo licencia ODbL.
- Relieve: AWS Terrain Tiles.

---

## Cómo verlo

Cómo verlo

👉 Abrir SeekingLoc

La página se abre directo en el navegador, en computadora o celular, sin instalar nada ni registrarse. Es la versión completa, con el buscador en lenguaje natural incluido.

> Fuera de claude.ai, el sitio funciona completo como portal de búsqueda. Las funciones que dependen de esa plataforma (panel de administración, métricas en tiempo real y la interpretación de búsquedas con IA generativa) se desactivan solas, sin errores: el buscador sigue funcionando con su intérprete propio.

### Estructura del repositorio

```
seekingloc/
├── index.html            # la aplicación completa (HTML + CSS + JS)
├── data/                 # datos geográficos y avisos de prueba
│   ├── avisos.json       # 1.500 avisos de prueba (formato compacto)
│   ├── avisos_det/       # descripción y plano, en 8 tandas que se piden al abrir una ficha
│   ├── cp/  mz/          # calles y manzanas de la provincia, partidas por departamento
│   ├── cerca/            # comercios y servicios, en celdas para búsquedas por radio
│   └── *.geojson         # barrios, localidades, rutas, ríos, colectivos, espacios verdes…
├── dem/                  # teselas de relieve (formato terrarium)
├── img/ej/               # 60 ilustraciones de ambientes para los avisos de ejemplo
├── tutorial.mp4          # video tutorial de carga de una propiedad
└── docs/capturas/        # capturas de este README
```

---

## Desafíos técnicos resueltos

### 1. Un mapa de toda la provincia sin Google Maps
**Problema:** mostrar calles, manzanas y barrios de toda Córdoba con una fluidez parecida a Google Maps, sin pagar una API y sin servidor de teselas.
**Solución:** MapLibre GL con datos GeoJSON propios, partidos en 60 bloques de calles y 52 de manzanas que se descargan según la zona visible; relieve con teselas DEM y un índice propio de más de 11.000 calles para ubicar direcciones reales en el navegador.

### 2. Un buscador en lenguaje natural que corre en el navegador
**Problema:** entender pedidos como *"oficina con seguridad 24 hs en el centro"* o *"casa con patio cerca del kempes"*, con errores de tipeo, sin depender de un servidor.
**Solución:** un intérprete propio que reconoce tipo de propiedad, operación, ambientes, presupuesto, barrios, calles con altura (incluso con iniciales o mal escritas), puntos de referencia y requisitos. Se mide con una batería fija de **2.264 consultas reales**:

| Métrica | v43 | v44 |
|---|---|---|
| Búsquedas que salen bien | 74,2 % | **78,2 %** |
| Bien o sin resultados pero explicadas | 92,9 % | **97,1 %** |
| Malinterpretadas | 89 | **25** |
| Sin resultados y sin explicación | 15 | **0** |

### 3. Rendimiento con miles de avisos en una sola página
**Problema:** filtrar y ordenar más de 30.000 avisos de ejemplo (1.500 de ellos completos) sin trabar la interfaz.
**Solución:**
- Formato compacto con tabla de textos repetidos: el archivo de avisos bajó de 3 MB a 0,9 MB (148 KB comprimido).
- Descripción y plano en tandas que se descargan al abrir cada ficha.
- Datos precalculados y memorización de cálculos costosos, como el comercio más cercano.

| Operación (navegador de prueba, sin placa de video) | Tiempo |
|---|---|
| Pintar el listado | 8 ms |
| Recalcular la barra de filtros | 70 ms |
| Búsqueda con requisitos | 55 ms |
| Carga de los 1.500 avisos (antes 9,6 s) | 3,7 s |

### 4. Accesibilidad medida, no supuesta
Con axe-core, los problemas graves y moderados bajaron de **174 a 0**:
- Tarjetas sin botones anidados y contraste corregido.
- La cantidad de resultados se anuncia a los lectores de pantalla.
- Los gráficos tienen su tabla de datos equivalente.
- La zona del mapa también se puede dibujar con el teclado (flechas, Enter, F).

### 5. "¿Está bien de precio?"
El precio por m² de cada aviso se compara con la **mediana** de avisos parecidos (mismo tipo y ambientes), buscando primero en el barrio, después en los alrededores y por último en la ciudad, hasta reunir una muestra suficiente. Se usa la mediana en lugar del promedio para que pocos avisos extremos no distorsionen la referencia.

### 6. Calidad sostenida con una batería de pruebas fija
Antes de cada versión corre una batería automatizada con Playwright de 17 controles:
- Carga de los avisos y tiempos de respuesta.
- Ficha completa en los 9 tipos de propiedad.
- Panel de administración y guardado de cambios.
- Accesibilidad en escritorio y celular.
- Ausencia de errores de JavaScript.
- Las 2.264 búsquedas.

En la v44 pasaron los 17 controles. La única salvedad es que la barra de filtros cumple su límite de 150 ms cuando la batería corre sola, no con otra prueba en paralelo.

---

## Decisiones de diseño UX

- **Una sola página.** Al abrir un aviso no se abre otra pestaña; el desafío fue ofrecer todas las herramientas sin abrumar a quien solo quiere ver fotos.
- **Menos es más.** Portada tipo "telón" con un buscador y los filtros esenciales; el resto aparece cuando hace falta.
- **Sin muros de registro.** La ventana de registro nunca aparece sola.
- **IA implícita.** El buscador entiende pedidos complejos sin etiquetarse como "con IA"; sugerencias tenues muestran que se puede pedir cualquier cosa.
- **Información verificable.** Los precios y las estadísticas salen solo de los avisos y del uso del sitio, no de fuentes externas sin control.
- **Identidad visual propia.** Paleta verde azulada y violeta de alto contraste, sin naranja, para diferenciarse de la competencia local.
- **Sin puntajes ni reseñas.** Las propiedades se miden por lo que ofrecen, no por opiniones.

---

## Mi rol

Proyecto **independiente**, de punta a punta: idea, producto y diseño de la experiencia.

- **Producto:** definí el problema, el público (quien busca y quien publica), el alcance (todos los tipos de propiedad, alquiler y compra, toda la provincia) y el modelo de negocio con planes de suscripción.
- **Diseño UX/UI:** definí la arquitectura de la información, el recorrido de búsqueda en una sola página, la ficha estandarizada y la identidad visual. Iteré el diseño en **44 versiones** a partir de pruebas y auditorías.
- **Dirección técnica y calidad:** el código se escribió con un asistente de IA (Claude). Yo marqué los requisitos, revisé cada versión, definí los criterios de evaluación (rúbricas, batería de búsquedas, metas de rendimiento y accesibilidad) y decidí qué entraba en cada iteración.
- **Datos:** elegí las fuentes oficiales y abiertas (IDECOR, Municipalidad de Córdoba, OpenStreetMap) y los criterios para que los avisos de prueba sean realistas.

---

## Próximos pasos

- [ ] Servidor y base de datos para publicaciones reales, con guardados y búsquedas sincronizados entre dispositivos.
- [ ] Panel para anunciantes con métricas de cada aviso y reporte mensual en PDF.
- [ ] Mejorar el reconocimiento de barrios mal escritos.
- [ ] Lanzamiento con inmobiliarias de Córdoba.

---

## Contacto

**Nicolás Barrera** · Unquillo, Córdoba, Argentina
[LinkedIn](https://www.linkedin.com/in/nicolas-barrera-216524241) · [GitHub](https://github.com/nico-barrera-01))

<sub>© 2026 Nicolás Barrera. Todos los derechos reservados. Datos geográficos: IDECOR, Municipalidad de Córdoba y © colaboradores de OpenStreetMap (ODbL). Los avisos son de ejemplo: las direcciones son reales, los avisos no.</sub>
