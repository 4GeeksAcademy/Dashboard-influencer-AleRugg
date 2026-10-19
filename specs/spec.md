# Especificaciones del dashboard de campañas

## 1. Descripción y objetivo

Definir un dashboard académico, sencillo y estático para que una influencer consulte los resultados de sus campañas de Instagram, TikTok y YouTube durante septiembre de 2026.

El dashboard debe permitir identificar el volumen de ventas, los ingresos por ventas, las comisiones de la influencer y las diferencias de rendimiento entre plataformas y productos. No pretende ser una herramienta profesional ni analizar datos reales.

## 2. Contexto del negocio

- Periodo fijo: del 1 al 30 de septiembre de 2026.
- Plataformas: Instagram, TikTok y YouTube.
- Productos: A, B y C, con precios de 50 €, 120 € y 80 €, respectivamente.
- Comisión de la influencer: 15 % del precio de cada unidad vendida.
- Los precios y el porcentaje de comisión son datos conocidos del negocio según el enunciado.
- Todos los datos de rendimiento proporcionados y los ejemplos de campañas son ficticios y se utilizan exclusivamente para esta propuesta académica.
- Los ingresos por ventas corresponden al valor de los productos vendidos; las comisiones representan la remuneración de la influencer. No son magnitudes equivalentes ni deben sumarse como ingresos de la influencer.

## 3. Alcance y limitaciones

La solución consiste en una única página estática, con tres bloques: indicadores principales, drivers del rendimiento y detalles operacionales. Los valores y los rankings se mostrarán ya calculados.

Se excluyen autenticación, edición de datos, filtros dinámicos, exportaciones, actualización automática, notificaciones y conexiones con las plataformas.

Las métricas sin datos suficientes deben mostrar «Sin datos» o «N/D» (no disponible) y una explicación breve. En este documento, las menciones a «No disponible» designan ese mismo estado. Un valor desconocido no debe representarse como cero. «Pendiente» puede utilizarse para información aún no aportada, sin sugerir que el dashboard la obtendrá automáticamente.

Las distribuciones por producto y por plataforma son vistas agregadas separadas. Aunque ambas suman 150 ventas, no existe una tabla que relacione producto, plataforma y campaña. No se deben deducir esas relaciones ni sumar ambas distribuciones como si fueran ventas distintas.

El alcance agregado no representa personas únicas entre plataformas. No hay datos diarios, comparación con otros periodos, impresiones ni seguimiento individual del recorrido de compra.

## 4. Usuarios y necesidades

La usuaria principal es una influencer que necesita:

- Consultar cuántas ventas se han registrado y qué comisiones generan.
- Comparar plataformas según una métrica claramente identificada.
- Identificar productos con mayor volumen de ventas o comisiones.
- Revisar campañas ilustrativas y reconocer qué resultados faltan.
- Distinguir resultados disponibles, limitaciones y oportunidades de mejora sin conocimientos técnicos.

## 5. Requisitos funcionales

- RF-01. Mostrar el periodo fijo y un aviso visible de que el rendimiento es ficticio y de uso académico.
- RF-02. Organizar el contenido en los tres bloques definidos en la sección 6.
- RF-03. Priorizar los KPI calculables y representar todas las categorías solicitadas, incluso cuando alguna solo tenga métricas no disponibles.
- RF-04. Mostrar un funnel agregado y comparaciones de plataformas y productos, sin inventar atribuciones detalladas.
- RF-05. Incluir los apartados de calidad, actividad y desglose de engagement con sus estados de disponibilidad.
- RF-06. Incluir tablas de productos, plataformas y campañas, con unidades y denominadores identificables.
- RF-07. Mostrar el estado de las alertas y listados de mejores resultados según métricas explícitas.
- RF-08. Diferenciar siempre ingresos por ventas, comisiones y costes publicitarios.
- RF-09. Mantener todos los resultados fijos; no mostrar controles que aparenten funciones inexistentes.

## 6. Estructura de los tres bloques

### 6.1. Bloque superior: indicadores principales

Los KPI destacados serán: 150 ventas, 12.200 € de ingresos por ventas, 1.830 € de comisiones, 81,33 € de precio medio de venta y 24.600 interacciones.

El resto de indicadores se agrupará por categoría con menor prioridad visual:

| Categoría | Métricas disponibles | Métricas no disponibles y motivo |
| --- | --- | --- |
| Volumen | 150 ventas | Inscripciones, usuarios activos e impresiones: sin registros |
| Ingresos | 1.830 € de comisiones; 12.200 € de ingresos por ventas; precio medio de venta de 81,33 € | MRR: no hay suscripciones ni ingresos recurrentes definidos |
| Engagement | 24.600 interacciones; engagement agregado sobre alcance de 6,83 %; conversión sobre alcance de 0,0417 % | Sin desglose por tipo de interacción |
| Retención | Ninguna | Churn, permanencia y compleción del proceso de venta o suscripción: sin cohortes, duraciones ni procesos iniciados y completados |
| Rendimiento | 150 conversiones de venta; conversión sobre alcance de 0,0417 % | CTR: faltan impresiones |
| Satisfacción | Ninguna | NPS y CSAT: sin encuestas |
| Eficiencia | Coste publicitario por venta atribuida de 4,00 € en el agregado de plataformas | Margen y tiempos: faltan costes completos, beneficio y registros temporales |

Una conversión significa una venta en este escenario. Su aparición en varias categorías no representa eventos adicionales. Las tasas agregadas utilizan sumas de numeradores y denominadores, no medias simples de porcentajes.

### 6.2. Bloque intermedio: drivers del rendimiento

**Funnel de conversión por etapas**

Mostrar la secuencia ilustrativa: alcance agregado no deduplicado de 360.000 → 4.500 clics → 150 ventas atribuidas por plataforma. Las etapas deben tener etiquetas y cantidades visibles.

El funnel compara magnitudes agregadas: no demuestra que las mismas personas hayan pasado por cada etapa. No añadir etapas de leads, carrito o suscripción sin datos. No utilizar el alcance como sustituto de impresiones.

**Rendimiento por plataforma**

Comparar alcance, interacciones, clics, ventas, tasa de engagement, conversión sobre alcance y coste publicitario por venta atribuida. Cada indicador debe conservar su unidad y denominador. No atribuir ingresos ni comisiones a plataformas.

**Calidad**

Incluir ratio de leads cualificados, attendance rate y pass rate como «No disponible». Faltan los recuentos y la definición de los eventos de cualificación, asistencia y aprobación; no deben equipararse a clics o ventas.

**Rendimiento por producto**

Comparar las ventas y comisiones totales de A, B y C con los valores de la sección 7. Identificar las conversiones como unidades vendidas para este escenario.

**Actividad**

Mostrar una tabla por plataforma con publicaciones, stories, reels y vídeos. Los recuentos deben figurar como «No disponible» porque no se han proporcionado. Utilizar «No aplica» únicamente para formatos que no correspondan a la plataforma; no confundirlo con ausencia de datos ni sumar formatos potencialmente solapados.

**Engagement**

Mostrar por plataforma me gusta, comentarios, compartidos y guardados como «No disponible». Las interacciones totales sí están disponibles, pero no permiten deducir su reparto entre estas categorías.

### 6.3. Bloque inferior: detalles operacionales

**Tabla de productos**

Incluir producto, precio unitario, comisión unitaria, conversiones, ingresos por ventas, comisiones generadas y ROI. El ROI de todos los productos debe figurar como «No disponible: faltan costes y beneficio atribuible por producto».

**Tabla de plataformas**

Incluir plataforma, alcance, interacciones, tasa de engagement, clics, conversiones, conversión sobre alcance, coste publicitario y coste por venta atribuida. Identificar la mejor plataforma en cada métrica relevante:

- TikTok: mayor alcance, interacciones totales, clics y ventas.
- Instagram: mayor tasa de engagement sobre alcance.
- YouTube: mayor conversión sobre alcance y menor coste publicitario por venta atribuida.

No declarar una plataforma ganadora universal. El coste publicitario es contexto de inversión, no una clasificación de éxito por sí mismo.

**Tabla de campañas**

Mostrar los siguientes ejemplos ficticios, sin conectarlos con los totales de ventas existentes:

| Campaña ilustrativa | Fechas de septiembre de 2026 | Productos promocionados | Resultados | Rendimiento |
| --- | --- | --- | --- | --- |
| Campaña A | 01/09/2026 a 10/09/2026 | Producto A | No disponible | No evaluable: faltan resultados atribuidos |
| Campaña B | 11/09/2026 a 20/09/2026 | Producto B | No disponible | No evaluable: faltan resultados atribuidos |
| Campaña C | 21/09/2026 a 30/09/2026 | Producto C | No disponible | No evaluable: faltan resultados atribuidos |

Los nombres, fechas y asociaciones de productos de esta tabla son ejemplos académicos añadidos, no datos conocidos del negocio. No repartir las 150 ventas entre estas campañas sin una tabla de atribución coherente.

**Alertas**

Incluir caídas importantes de conversión, picos de conversión y anomalías de rendimiento. Los tres estados serán «No evaluable: faltan datos temporales y una referencia de comparación». No afirmar que no existen anomalías ni inventar variaciones mensuales, umbrales o detección automática.

**Listados y oportunidades de mejora**

- Top productos por ventas: A (60), B (50), C (40).
- Top productos por comisiones: B (900 €), C (480 €), A (450 €).
- Top plataformas por ventas: TikTok (70), Instagram (45), YouTube (35).
- Top campañas: «Pendiente: faltan resultados atribuidos por campaña».
- Oportunidades: revisar el recorrido de conversión de Instagram y TikTok tomando YouTube como referencia descriptiva, sin asegurar causalidad ni mejoras futuras; completar impresiones, costes por producto y atribución de campañas para ampliar el análisis.

## 7. Datos y fórmulas

### 7.1. Rendimiento ficticio por plataforma

| Plataforma | Alcance | Interacciones | Clics | Ventas atribuidas | Coste publicitario |
| --- | --- | --- | --- | --- | --- |
| Instagram | 120.000 | 9.600 | 1.500 | 45 | 200 € |
| TikTok | 180.000 | 10.800 | 2.400 | 70 | 300 € |
| YouTube | 60.000 | 4.200 | 600 | 35 | 100 € |
| Total agregado | 360.000 | 24.600 | 4.500 | 150 | 600 € |

El alcance total es una suma no deduplicada. Los costes son exclusivamente publicitarios, no costes completos de la actividad.

| Plataforma | Engagement sobre alcance | Conversión sobre alcance | Coste publicitario por venta atribuida |
| --- | --- | --- | --- |
| Instagram | 8,00 % | 0,0375 % | 4,44 € |
| TikTok | 6,00 % | 0,0389 % | 4,29 € |
| YouTube | 7,00 % | 0,0583 % | 2,86 € |
| Agregado | 6,83 % | 0,0417 % | 4,00 € |

### 7.2. Productos y resultados

| Producto | Precio unitario conocido | Comisión por venta | Ventas ficticias | Ingresos por ventas | Comisiones generadas |
| --- | --- | --- | --- | --- | --- |
| A | 50 € | 7,50 € | 60 | 3.000 € | 450 € |
| B | 120 € | 18,00 € | 50 | 6.000 € | 900 € |
| C | 80 € | 12,00 € | 40 | 3.200 € | 480 € |
| Total | No aplica | No aplica | 150 | 12.200 € | 1.830 € |

### 7.3. Definición de fórmulas

- Comisión unitaria por producto = precio × 15 %.
- Comisiones generadas por producto = comisión unitaria × unidades vendidas.
- Comisiones totales = suma de las comisiones generadas por producto = 1.830 €.
- Ingresos por ventas = suma de precio × unidades vendidas = 12.200 €.
- Precio medio de venta = ingresos por ventas / unidades vendidas = 12.200 / 150 = 81,33 €.
- Tasa de engagement = interacciones / alcance × 100.
- Conversión sobre alcance = ventas atribuidas / alcance × 100.
- CTR = clics / impresiones × 100. No disponible porque faltan impresiones; no sustituirlas por alcance.
- Coste publicitario por venta atribuida = coste publicitario / ventas atribuidas. No equivale al coste completo de adquisición de un cliente único.
- ROAS = ingresos por ventas atribuidos / coste publicitario. Se expresa como múltiplo. No disponible por plataforma o campaña: falta atribución de ingresos. No calcular un ROAS global con las dos vistas independientes sin confirmar que los ingresos y el gasto pertenecen al mismo ámbito publicitario.
- ROI = (beneficio atribuible − coste de inversión) / coste de inversión × 100. Para esta fórmula, beneficio atribuible significa el beneficio antes de descontar el coste de inversión que se resta en el numerador; así se evita descontarlo dos veces. Hacen falta costes y beneficios del mismo ámbito, periodo y titular económico. No sustituir beneficio por ingresos por ventas o comisiones brutas.

Las tasas agregadas de engagement y conversión se calculan respectivamente como 24.600 / 360.000 × 100 y 150 / 360.000 × 100. Debe indicarse que sus denominadores no están deduplicados entre plataformas.

Todos los cálculos utilizan los valores originales y se redondean solo al mostrarlos. Mostrar importes con dos decimales cuando sea necesario, engagement con dos decimales y conversión sobre alcance con cuatro decimales. Ante un denominador cero o desconocido, mostrar «No disponible».

## 8. Requisitos visuales y de usabilidad

- Interfaz y etiquetas en español; periodo de análisis siempre visible al inicio.
- Jerarquía clara: KPI principales, drivers y detalles, en ese orden.
- Diseño sencillo y consistente, con tablas legibles y sin gráficos decorativos innecesarios.
- Visualizaciones estáticas con etiquetas y valores; no depender de tooltips para comunicar datos esenciales.
- Mostrar las unidades de cada métrica y diferenciar visualmente ingresos por ventas y comisiones.
- Identificar los datos ficticios de forma visible y explicar cerca de cada métrica las limitaciones necesarias.
- Usar contraste suficiente y no depender únicamente del color para señalar estados o mejores resultados.
- Utilizar encabezados jerárquicos y tablas con cabeceras identificables.
- Adaptar la distribución a móvil y escritorio, sin texto superpuesto. Las tablas anchas pueden tener desplazamiento horizontal dentro de su contenedor.
- Los estados «No disponible», «No aplica» y «No evaluable» deben ser legibles y distinguirse de un valor numérico cero.
- No mostrar botones, selectores o filtros sin funcionalidad real. Si se incluyen enlaces internos, deben permitir navegación nativa entre secciones.

## 9. Restricciones tecnológicas

- Utilizar exclusivamente HTML y Tailwind CSS v4 mediante el CDN indicado en la petición de implementación. Esta decisión sustituye el método previo de CSS local precompilado.
- No utilizar React, Vue, Angular, JavaScript propio, TypeScript ni librerías adicionales. La única excepción de script es el cargador oficial `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`, incluido una sola vez en la cabecera.
- No utilizar backend, API, bases de datos, servicios externos de datos ni almacenamiento de información de usuarios.
- El dashboard debe funcionar al abrir el HTML como página estática, sin ejecutar un servidor de aplicación. Necesita conexión para cargar Tailwind desde el CDN; no se garantiza presentación con estilos sin conexión.
- Escribir todas las utilidades directamente en los elementos HTML. No crear ni enlazar archivos CSS adicionales, hojas externas o estilos propios; Tailwind genera sus estilos en el navegador.
- Todos los datos, cálculos, tablas, rankings y estados estarán definidos previamente en el contenido estático. No habrá cálculos ni actualización de datos en tiempo de ejecución.
- No utilizar librerías de gráficos, SVG ni Canvas. Construir barras y funnel con HTML y clases de Tailwind de anchura proporcional, con cantidades legibles fuera del relleno.

## 10. Criterios de aceptación

1. El dashboard está redactado en español, identifica septiembre de 2026 y avisa de que los datos de rendimiento son ficticios y académicos.
2. Presenta los tres bloques obligatorios en el orden solicitado y contempla todas las categorías de KPI.
3. Destaca 150 ventas, 12.200 € de ingresos por ventas, 1.830 € de comisiones, 81,33 € de precio medio de venta y 24.600 interacciones.
4. Reproduce los datos por plataforma y producto de la sección 7 sin cambios, duplicaciones ni atribuciones cruzadas inventadas.
5. Las tasas y los costes por venta coinciden con las fórmulas y los redondeos documentados; las conversiones sobre alcance no aparecen como conversiones sobre clics.
6. Incluye funnel, rendimiento por plataforma y producto, calidad, actividad y desglose de engagement; representa los datos faltantes sin inventarlos.
7. Incluye las tablas de productos, plataformas y campañas con todos los campos exigidos; el ROI por producto y el rendimiento de campañas permanecen no disponibles o no evaluables.
8. Identifica líderes por métrica y muestra los rankings especificados, sin afirmar que existe una mejor plataforma universal ni clasificar campañas sin resultados.
9. Incluye los tres tipos de alertas y explica por qué no son evaluables con los datos mensuales disponibles.
10. No calcula CTR sin impresiones, ROAS sin atribución válida ni ROI sin costes y beneficio atribuible. No confunde ingresos por ventas con comisiones.
11. Muestra las métricas no disponibles con su motivo; no las presenta como cero, resultados reales o funciones pendientes de ejecución automática.
12. Se puede consultar en móvil y escritorio con texto legible, tablas accesibles y sin solapamientos.
13. Funciona como una única página HTML con Tailwind CSS v4 mediante el CDN autorizado, sin JavaScript propio, CSS adicional, backend, API, bases de datos ni librerías adicionales. Solo incluye una vez el script de Tailwind y requiere conexión para sus estilos.