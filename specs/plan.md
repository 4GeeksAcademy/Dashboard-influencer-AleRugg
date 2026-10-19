# Plan técnico: Influencer Analytics

## 1. Resumen técnico

Implementar el dashboard definido en [specs/spec.md](spec.md) como una única página estática, en español, con HTML semántico y utilidades de Tailwind CSS. Los datos, resultados y rankings estarán escritos directamente en el HTML y calculados antes de incorporarlos.

La documentación se mantiene exclusivamente en `specs/`: [specs/spec.md](spec.md), [specs/plan.md](plan.md) y [specs/task.md](task.md). La implementación permanece en [index.html](../index.html), en la raíz del proyecto.

La entrega es un único HTML con las utilidades de Tailwind escritas directamente en sus elementos, sin aplicación, arquitectura de componentes ni archivos CSS adicionales.

No se utilizarán JavaScript propio, frameworks, Chart.js, otras librerías, backend, API, bases de datos ni fuentes de datos externas. El único script permitido será Tailwind CSS v4 mediante el CDN autorizado. No habrá animaciones, filtros, botones sin función, actualizaciones automáticas ni cálculos de datos en el navegador. El servidor existente no será un requisito para consultar la página.

La petición posterior de implementación sustituye el método de CSS local por CDN y requiere un funnel proporcional, estados «Sin datos» o «N/D» y breakpoints base, `md:` y `lg:`. El plan recoge esos ajustes sin ampliar el alcance funcional.

## 2. Arquitectura de la página

- Documento con idioma español, codificación UTF-8, configuración de viewport y título «Influencer Analytics».
- Un `header` con el único `h1`, «Influencer Analytics», el periodo «Septiembre de 2026» y la nota visible «Datos simulados con fines académicos».
- Un `main` con tres elementos `section`, en orden vertical: KPI principales, drivers del rendimiento y detalles operacionales.
- Cada bloque tendrá un `h2`; sus agrupaciones y comparaciones usarán `h3`. Los identificadores serán únicos y los encabezados describirán el contenido asociado.
- Las secciones ocuparán el ancho disponible dentro de un contenedor centrado de anchura máxima. No se añadirá barra lateral, navegación compleja ni secciones ajenas al dashboard.
- Las comparaciones gráficas se organizarán con `figure` y `figcaption`; las métricas con listas descriptivas; los rankings con listas ordenadas; los datos tabulares con `table`.

La estructura del documento y el orden de lectura serán iguales en móvil y escritorio. Las limitaciones de cada dato se colocarán junto al componente correspondiente, sin depender de tooltips.

## 3. Distribución de los tres bloques

### 3.1. Bloque 1: KPI principales

Después de la cabecera, disponer una cuadrícula de tarjetas individuales con etiquetas, valor y unidad:

| KPI | Valor previsto | Presentación |
| --- | --- | --- |
| Ventas totales | 150 | Indicador prioritario; una conversión equivale a una venta |
| Comisiones generadas | 1.830 € | Indicador prioritario; remuneración de la influencer |
| Ingresos por ventas | 12.200 € | Indicador prioritario; importe de productos vendidos |
| Precio medio de venta | 81,33 € | Destacado exigido por las especificaciones |
| Interacciones totales | 24.600 | Destacado exigido por las especificaciones |
| Tasa de engagement sobre alcance | 6,83 % | Indicador agregado, con denominador no deduplicado |
| Tasa de conversión sobre alcance | 0,0417 % | Indicador agregado; no conversión sobre clics |
| CTR | No disponible | Faltan impresiones; menor énfasis visual |
| Coste publicitario | 600 € | Inversión agregada de las plataformas, no coste total de actividad |

Mantener los cinco destacados de [specs/spec.md](spec.md) en primer lugar y con mayor énfasis. Las tasas y el coste publicitario completarán la cuadrícula; el CTR tendrá el patrón visual de dato no disponible.

Debajo de las tarjetas, incorporar una tabla compacta de cobertura por categoría, sin tarjetas anidadas:

- Volumen: ventas disponibles; inscripciones, usuarios activos e impresiones no disponibles.
- Ingresos: ventas, comisiones y precio medio disponibles; MRR no disponible por ausencia de suscripciones.
- Engagement: interacciones y tasas indicadas; sin desglose de interacciones.
- Retención: churn, permanencia y compleción del proceso de venta o suscripción no disponibles.
- Rendimiento: 150 conversiones y conversión sobre alcance; CTR no disponible.
- Satisfacción: NPS y CSAT no disponibles por ausencia de encuestas.
- Eficiencia: coste publicitario por venta atribuida de 4,00 €; margen y tiempos no disponibles.

Los indicadores repetidos en esta cobertura no se sumarán ni se interpretarán como resultados adicionales. Cada dato ausente llevará el motivo previsto en las especificaciones.

### 3.2. Bloque 2: drivers del rendimiento

**Funnel estático.** Representar tres etapas mediante una lista ordenada de bandas horizontales: alcance agregado no deduplicado (360.000), clics (4.500) y ventas atribuidas por plataforma (150). Utilizar anchuras proporcionales al alcance: 100 %, 1,25 % y aproximadamente 0,041667 %, mediante utilidades de Tailwind. Mantener las cantidades fuera del relleno para que las etapas pequeñas sigan siendo legibles. No mostrar porcentajes de abandono ni aparentar un seguimiento individual. Incluir la advertencia sobre magnitudes agregadas de [specs/spec.md](spec.md).

**Comparación por plataforma.** Utilizar grupos de barras horizontales separados para alcance, interacciones, clics y ventas. Cada grupo tendrá su propia escala lineal, desde cero hasta el máximo de esa métrica entre las tres plataformas. La anchura de cada barra se fijará previamente como valor dividido por ese máximo. Mostrar siempre plataforma y cantidad fuera del relleno. Las tasas de engagement, conversión y coste por venta se mostrarán en una tabla compacta junto a la comparación, sin mezclar sus unidades en una escala común.

**Comparación por producto.** Mostrar barras de comisiones: A, 450 €; B, 900 €; C, 480 €, normalizadas respecto de 900 €. Acompañarlas con sus ventas: 60, 50 y 40. No relacionar estos importes con plataformas o campañas.

**Engagement por plataforma.** Tabla con plataforma, interacciones totales, tasa sobre alcance, me gusta, comentarios, compartidos y guardados. Los cuatro desgloses permanecerán como «No disponible», sin repartir las interacciones totales.

**Calidad.** Lista descriptiva con ratio de leads cualificados, attendance rate y pass rate. Los tres valores serán «No disponible» por falta de recuentos y definición de eventos.

**Actividad.** Tabla con plataforma, publicaciones, stories, reels y vídeos. Mostrar los recuentos como «No disponible» y reservar «No aplica» para formatos inequívocamente ajenos a una plataforma. No deducir actividad a partir de alcance ni sumar formatos solapados.

### 3.3. Bloque 3: detalles operacionales

**Productos.** Tabla con producto, precio unitario, comisión unitaria, conversiones, ingresos por ventas, comisiones generadas y ROI. Añadir fila de totales donde proceda. El ROI permanecerá como «No disponible: faltan costes y beneficio atribuible por producto».

**Plataformas.** Tabla con plataforma, alcance, interacciones, tasa de engagement, clics, conversiones, conversión sobre alcance, coste publicitario y coste por venta atribuida. Identificar los líderes mediante texto junto a las cifras o en una leyenda inmediata: TikTok en alcance, interacciones, clics y ventas; Instagram en engagement; YouTube en conversión sobre alcance y menor coste por venta. No proclamar una ganadora universal.

**Campañas.** Reproducir los ejemplos de [specs/spec.md](spec.md): campaña A del 01/09 al 10/09 con producto A; B del 11/09 al 20/09 con producto B; C del 21/09 al 30/09 con producto C, todas en 2026. Mantener columnas de resultados y rendimiento como «No disponible» y «No evaluable: faltan resultados atribuidos». Indicar que nombres, fechas y asociaciones son ilustrativos e independientes de los totales.

**Alertas.** Lista visual de caídas importantes de conversión, picos de conversión y anomalías de rendimiento. Las tres entradas indicarán «No evaluable: faltan datos temporales y una referencia de comparación». No usar estados de éxito, umbrales inventados ni mensajes de detección automática.

**Rankings y oportunidades.** Listas ordenadas de productos por ventas (A, B, C), productos por comisiones (B, C, A) y plataformas por ventas (TikTok, Instagram, YouTube), con sus cifras. El top campañas mostrará el estado pendiente especificado. Las oportunidades se limitarán a revisar descriptivamente el recorrido de conversión y completar impresiones, costes por producto y atribución de campañas; no prometer causalidad ni resultados futuros.

## 4. Componentes HTML y patrones visuales

- Tarjeta KPI: etiqueta, cifra, unidad y explicación breve cuando sea necesaria. Misma estructura y espaciado para todas; ningún componente interactivo.
- Grupo de métricas: lista descriptiva o tabla abierta dentro de la sección; no encerrar tarjetas dentro de otras tarjetas ni convertir bloques completos en tarjetas flotantes.
- Barra comparativa: etiqueta y valor legibles, pista neutra y relleno de longitud fija precalculada. La información textual será suficiente sin percibir el color o la longitud.
- Funnel: bandas estáticas proporcionales al alcance con cantidades y escala visibles.
- Tabla: título mediante `caption`, `thead`, `tbody`, cabeceras `th` con `scope` y `tfoot` solo cuando los totales tengan sentido. Las cifras se alinearán a la derecha y los nombres a la izquierda.
- Estado: texto «Sin datos», «N/D» (no disponible), «Pendiente», «No aplica» o «No evaluable» acompañado del motivo, sin reemplazarlo por guiones o ceros. Las menciones a «No disponible» en este plan representan el mismo estado.
- Alertas: lista con borde lateral y etiqueta textual de estado; no utilizar roles de aviso urgente para información estática.

La reutilización será manual: repetir el mismo marcado y las mismas clases para tarjetas, tablas y estados. No crear componentes programáticos, plantillas dinámicas ni nuevas abstracciones. Las etiquetas visibles nombrarán métricas y limitaciones, no explicarán cómo utilizar la interfaz.

## 5. Estrategia de estilos con Tailwind

### Método de incorporación

Incluir una única vez en `head`, después de las etiquetas `meta`, el script `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`, precedido del comentario «Tailwind CSS v4: utilidades de estilo para el prototipo académico».

Escribir las clases directamente en el HTML. No crear entradas CSS, hojas precompiladas, configuración de Tailwind ni paquetes de aplicación. No incluir estilos propios ni enlaces a hojas externas.

Tailwind genera los estilos en el navegador. La página necesita conexión al CDN para su presentación, pero no depende de datos externos ni de un servidor de aplicación. No añadir ningún otro script. Las anchuras de barras se expresarán con utilidades fraccionarias o porcentajes arbitrarios completos, nunca con tamaños manuales en píxeles.

### Paleta y tipografía

| Uso | Utilidades previstas |
| --- | --- |
| Fondo general | `bg-zinc-50` |
| Superficie de tarjetas KPI | `bg-white` |
| Texto principal y secundario | `text-zinc-900`, `text-zinc-600` |
| Bordes y separadores | `border-zinc-200` |
| Comisiones y datos económicos destacados | `text-emerald-800`, rellenos `bg-emerald-600` |
| Barras de plataformas | `bg-sky-600`, `bg-emerald-600`, `bg-rose-600`, manteniendo una asignación consistente |
| Estados pendientes o no evaluables | `bg-amber-50`, `text-amber-900`, `border-amber-300` |

Usar una tipografía sans serif local disponible, sin descargar fuentes. Los valores se distinguirán con `font-semibold` y `tabular-nums`. Prever `text-2xl` para el título y los valores KPI, `text-xl` para títulos de bloque, `text-lg` para subtítulos y `text-sm` o `text-base` para etiquetas y tablas. No escalar las fuentes en función del ancho de la ventana ni utilizar espaciado negativo entre letras.

### Espaciado y superficies

Usar `max-w-7xl`, `mx-auto` y relleno horizontal adaptable con `px-4`, `md:px-6` y `lg:px-8`. Separar bloques mediante `space-y-12`; agrupar contenidos con `gap-4` o `gap-6` y dar a las tarjetas `p-5`, `border` y `rounded-lg`. No añadir sombras decorativas, gradientes, ilustraciones, iconos externos ni animaciones.

Las barras tendrán altura estable, por ejemplo `h-3`, y las etiquetas se situarán fuera del relleno para evitar recortes. Los indicadores desconocidos serán texto, nunca barras de longitud cero ni esqueletos de carga.

## 6. Organización y coherencia de los datos

[specs/spec.md](spec.md) será la fuente de referencia de todos los valores. Se incorporarán directamente a celdas, listas, etiquetas y anchuras estáticas del HTML; no se crearán archivos JSON, generadores de datos ni lecturas externas.

| Producto | Precio | Comisión unitaria (15 %) | Ventas | Ingresos por ventas | Comisiones |
| --- | --- | --- | --- | --- | --- |
| A | 50 € | 7,50 € | 60 | 3.000 € | 450 € |
| B | 120 € | 18,00 € | 50 | 6.000 € | 900 € |
| C | 80 € | 12,00 € | 40 | 3.200 € | 480 € |
| Total | No aplica | No aplica | 150 | 12.200 € | 1.830 € |

| Plataforma | Alcance | Interacciones | Clics | Ventas | Coste publicitario | Engagement | Conversión sobre alcance | Coste por venta |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Instagram | 120.000 | 9.600 | 1.500 | 45 | 200 € | 8,00 % | 0,0375 % | 4,44 € |
| TikTok | 180.000 | 10.800 | 2.400 | 70 | 300 € | 6,00 % | 0,0389 % | 4,29 € |
| YouTube | 60.000 | 4.200 | 600 | 35 | 100 € | 7,00 % | 0,0583 % | 2,86 € |
| Agregado | 360.000 | 24.600 | 4.500 | 150 | 600 € | 6,83 % | 0,0417 % | 4,00 € |

Reglas de incorporación y revisión:

- Comisión unitaria = precio × 15 %; ingresos por producto = precio × ventas; comisiones por producto = comisión unitaria × ventas.
- Precio medio = 12.200 / 150 = 81,33 €; engagement agregado = 24.600 / 360.000 × 100; conversión agregada sobre alcance = 150 / 360.000 × 100; coste publicitario por venta = 600 / 150.
- No promediar directamente los porcentajes de plataformas. Redondear solo la presentación: engagement a dos decimales, conversión sobre alcance a cuatro e importes según [specs/spec.md](spec.md).
- Mantener el formato numérico español y las unidades visibles. Mostrar «No disponible» si falta el denominador o es cero.
- Aclarar que 360.000 es alcance agregado no deduplicado y que las dos distribuciones de 150 ventas no constituyen una atribución cruzada ni 300 ventas.
- No asignar ingresos o comisiones a plataformas ni ventas a campañas. No calcular ROAS sin atribución válida, CTR sin impresiones ni ROI sin costes y beneficio atribuible.
- No equiparar comisiones con beneficio neto ni el coste publicitario con todos los costes. No utilizar alcance como impresiones.
- Repetir un valor en varios componentes exige verificar todas sus apariciones; el navegador no sincronizará los datos.

## 7. Responsive design

- Partir de una columna con `grid-cols-1`. Las tarjetas KPI pasarán a dos columnas con `md:grid-cols-2` y a tres con `lg:grid-cols-3`.
- Mantener siempre los tres bloques uno debajo de otro. Dentro del bloque de drivers, utilizar dos columnas con `lg:grid-cols-2` únicamente para comparaciones que conserven espacio suficiente.
- Mantener las secciones de tablas a todo el ancho. Cada tabla tendrá un contenedor `overflow-x-auto` y una anchura mínima adecuada a sus columnas; el desplazamiento horizontal quedará limitado a ese contenedor.
- Utilizar `min-w-0` en elementos de cuadrículas y permitir el salto de línea en etiquetas largas con `break-words`. Reservar `whitespace-nowrap` para cifras cortas, no para mensajes de ausencia de datos.
- Mantener las etiquetas de barras fuera del relleno y adaptar su disposición sin reducir la legibilidad de los números.
- No ocultar columnas, motivos de indisponibilidad, unidades ni notas de atribución en móvil. El funnel conservará su secuencia vertical en todos los tamaños.

## 8. Validación y pruebas visuales

Las siguientes comprobaciones se realizarán durante la implementación; no constituyen resultados de pruebas ya ejecutadas.

1. Revisar el HTML con un validador de marcado: idioma, estructura de encabezados, identificadores únicos, tablas y elementos semánticos. Comprobar que solo existe el script CDN autorizado, sin JavaScript propio, estilos adicionales o fuentes externas de datos.
2. Abrir el HTML directamente desde el sistema de archivos con conexión y comprobar que el script real de Tailwind v4 genera los estilos sin servidor de aplicación. No exigir funcionamiento con estilos sin conexión.
3. Revisar visualmente a 360, 768 y 1280 píxeles de ancho: orden de bloques, columnas, ausencia de solapamientos, ajuste de etiquetas, barras visibles y desplazamiento limitado a tablas. Revisar también con zoom del 200 %.
4. Comprobar contraste de texto normal de al menos 4,5:1, encabezados comprensibles, cabeceras de tablas y estados identificables sin color. Si un contenedor de tabla requiere foco para desplazarse con teclado, proporcionarle foco nativo y nombre accesible, sin JavaScript.
5. Verificar los totales, el precio medio, las tasas y los costes por venta mediante las fórmulas de [specs/spec.md](spec.md), calculadora u operaciones manuales; contrastar cada aparición repetida en el HTML.
6. Contrastar las anchuras de barras con sus escalas: cada máximo será el 100 % de su grupo y las demás longitudes serán proporcionales. Comprobar que el funnel use el alcance como referencia proporcional y conserve sus cifras legibles.
7. Verificar precios, comisión del 15 %, rankings y líderes por métrica. Confirmar que campañas, ROI, CTR, ROAS, alertas y métricas faltantes conservan sus estados y motivos correctos.
8. Recorrer los trece criterios de aceptación de [specs/spec.md](spec.md) y todos los campos previstos en los tres bloques. Comprobar la nota de datos simulados, el periodo y las advertencias de atribución, sin controles ficticios, decoraciones o interactividad añadida.

No se incorporará un framework de pruebas ni un entorno de automatización como dependencia del dashboard. Si se dispone de captura de pantalla en el navegador, se utilizará como evidencia de la revisión responsive.

## 9. Orden recomendado de implementación

1. Preparar el único script CDN de Tailwind CSS v4 en `head`, conservando `index.html` como única implementación, sin archivos CSS adicionales.
2. Crear la estructura semántica, la cabecera, el periodo y la nota de datos simulados.
3. Incorporar los KPI prioritarios y la cobertura de todas las categorías con sus estados de disponibilidad.
4. Construir el funnel, las comparaciones por plataforma y producto, y las secciones de engagement, calidad y actividad.
5. Completar las tablas operacionales, los estados de alertas, los rankings y las oportunidades de mejora.
6. Unificar los patrones visuales y aplicar la distribución responsive, sin añadir funciones ni elementos decorativos.
7. Comprobar la carga real del CDN y ejecutar las comprobaciones de presentación, accesibilidad, datos y aceptación de la sección 8.

El resultado será una página académica estática terminada, no una base para servicios, componentes dinámicos o integraciones posteriores fuera del alcance.