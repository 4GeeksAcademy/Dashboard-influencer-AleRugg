# Tareas de implementación: Influencer Analytics

El rediseño centrado en la comprensión sustituye los requisitos visuales de la versión anterior: cuatro KPI, exactamente tres drivers y únicamente dos tablas con datos completos. Se conservan los datos de [specs/spec.md](spec.md), la página existente y el CDN de Tailwind CSS v4 de [specs/plan.md](plan.md), sin funcionalidades, dependencias ni archivos adicionales.

## Seguimiento del rediseño vigente

- [x] R1. Modificar [index.html](../index.html) conservando el único CDN, la cabecera, el periodo y los tres bloques semánticos.
- [x] R2. Reducir el bloque superior a cuatro tarjetas: comisiones generadas, ventas generadas, engagement y plataforma destacada.
- [x] R3. Incorporar las cuatro preguntas y explicaciones solicitadas, con 1.830 €, 150 ventas, 6,83 % y TikTok con 70 ventas.
- [x] R4. Aclarar que las comisiones son remuneración bruta y no equivalen al beneficio neto ni a ingresos por ventas.
- [x] R5. Aplicar fondo crema, tarjetas pastel diferenciadas, paneles blancos, colores rosa empolvado, lavanda y salvia, bordes suaves y patrones consistentes.
- [x] R6. Alinear los valores de los KPI en escritorio reservando espacio a las preguntas desde tablet, sin añadir espacio innecesario en móvil.
- [x] R7. Mantener exactamente tres drivers con preguntas naturales, títulos solicitados y explicaciones interpretativas.
- [x] R8. Representar alcance (360.000), clics (4.500) y ventas (150) en un funnel legible con descripciones de cada etapa; identificar sus anchuras como esquemáticas, no proporcionales a los datos.
- [x] R9. Verificar engagement (6,83 %), clics respecto al alcance (1,25 %), ventas respecto a clics (3,33 %) y ventas sobre alcance (aproximadamente 0,042 %); explicar que son ratios agregados, no recorridos individuales demostrados.
- [x] R10. Utilizar una sola visualización de ventas por plataforma; destacar el mayor volumen y alcance de TikTok sin concluir que es más rentable.
- [x] R11. Comparar comisiones con barras proporcionales y destacar el Producto B (900 €), aclarando que el Producto A vende más unidades.
- [x] R12. Mantener únicamente la tabla de productos con precio, ventas, ingresos por ventas y comisiones, y la tabla de plataformas con alcance, interacciones, clics, ventas y coste publicitario.
- [x] R13. Incorporar las frases de utilidad previas a las tablas y filas de totales; verificar 150 ventas por vista, 12.200 € en ventas, 1.830 € en comisiones y 600 € en publicidad.
- [x] R14. Retirar cobertura de categorías, tarjetas redundantes, campañas, alertas, rankings y apartados sin datos de retención, satisfacción, calidad, actividad y desglose de engagement; no mostrar «N/D» ni «Sin datos».
- [x] R15. Mantener la independencia de las simulaciones por producto y plataforma y aclarar que el alcance sumado no representa personas únicas. No inventar atribución, ROI, CTR ni tendencias.
- [x] R16. Comprobar estilos base, `md:` y `lg:`: KPI en una, dos y cuatro columnas; drivers en una, dos y tres columnas, conservando el orden de lectura.
- [x] R17. Verificar a 360, 768 y 1280 de ancho y reflow adicional a 640: sin desbordamiento de página ni texto exterior recortado, con desplazamiento horizontal dentro de las tablas cuando es necesario.
- [x] R18. Validar el HTML, las referencias accesibles y el contraste de texto mínimo de 4,5:1; comprobar el desplazamiento de tablas con teclado.
- [x] R19. Contrastar filas, totales y tasas renderizados, y las seis barras comparativas con sus proporciones; revisar capturas de los tres bloques y la alineación de tarjetas.
- [x] R20. Confirmar que solo se modifican el HTML y este documento: sin CSS separado, JavaScript propio, gráficos SVG o Canvas, frameworks ni dependencias nuevas.
- [ ] R21. Completar la revisión manual con zoom nativo del navegador al 200 %, pendiente desde la versión anterior. El reflow a 640 se comprobó, pero no se considera equivalente a una prueba de zoom nativo.

## Evidencia del rediseño

- HTML validado sin errores con html-validate; un solo script CDN, tres secciones principales, cuatro KPI, tres figuras y dos tablas.
- Chromium cargó el CDN real desde el HTML abierto mediante `file://`, sin errores de página ni solicitudes fallidas. No se requiere servidor; los estilos requieren conexión al CDN.
- Verificados los valores de ambas tablas y sus totales, las cuatro tasas, las seis barras proporcionales de ventas y comisiones, y las advertencias de atribución. El funnel es esquemático para mantener legibles sus tres etapas.
- Revisadas capturas de móvil y escritorio y mediciones de 360, 768, 1280 y reflow 640. Los cuatro valores KPI quedan alineados en escritorio y las tablas no provocan desbordamiento de la página.
- Contraste de texto de al menos 4,5:1, identificadores únicos, referencias accesibles válidas y tabla desplazable con teclado. Las herramientas y capturas de prueba permanecen fuera del proyecto.

## Histórico de la versión anterior

Las tareas y evidencias siguientes documentan la implementación previa, no el contenido actual. Las categorías completas, nueve KPI, siete tablas, campañas, alertas y estados sin datos fueron retirados por petición expresa en el rediseño. Sus casillas conservan el registro de lo realizado entonces y no deben interpretarse como requisitos vigentes.

### Fase 1: preparación

- [x] F1.1. Revisar los requisitos funcionales y los trece criterios de aceptación de [specs/spec.md](spec.md); confirmar qué contenido y estados debe incluir cada bloque.
- [x] F1.2. Contrastar [specs/plan.md](plan.md) con las especificaciones; confirmar la página única, los patrones estáticos y la entrega mínima sin ampliar el alcance.
- [x] F1.3. Preparar [index.html](../index.html) con documento HTML válido, idioma español, UTF-8, viewport y título «Influencer Analytics»; comprobar que se abre directamente en el navegador.
- [x] F1.4. Incluir una única vez el script CDN autorizado de Tailwind CSS v4 en `head`, después de las etiquetas `meta`, con el comentario en español; no añadir JavaScript propio.
- [x] F1.5. Comprobar que el CDN genera las utilidades escritas directamente en el HTML, sin archivos CSS, enlaces a hojas de estilo ni dependencias adicionales; eliminar la hoja generada obsoleta.
- [x] F1.6. Crear la estructura semántica de cabecera y contenido principal con tres secciones, encabezados jerárquicos e identificadores únicos; comprobar el orden KPI, drivers y detalles operacionales.

### Fase 2: datos y cálculos

- [x] F2.1. Revisar las filas de productos que se incorporarán al HTML: A a 50 €, B a 120 € y C a 80 €, con 60, 50 y 40 ventas; confirmar que coinciden con la fuente.
- [x] F2.2. Calcular las comisiones unitarias del 15 % antes de escribirlas en el HTML; comprobar los resultados de 7,50 €, 18,00 € y 12,00 €.
- [x] F2.3. Verificar las ventas de ambas vistas por separado: 60 + 50 + 40 y 45 + 70 + 35 deben dar 150; no sumar las vistas entre sí.
- [x] F2.4. Calcular los ingresos por producto como precio por unidades; verificar 3.000 €, 6.000 € y 3.200 €, con un total de 12.200 €.
- [x] F2.5. Calcular las comisiones por producto; verificar 450 €, 900 € y 480 €, con un total de 1.830 € distinto de los ingresos por ventas.
- [x] F2.6. Contrastar los datos de Instagram, TikTok y YouTube que se incorporarán directamente al HTML con la sección 7 de las especificaciones; verificar agregados de 360.000 de alcance, 24.600 interacciones, 4.500 clics y 600 € de coste publicitario.
- [x] F2.7. Revisar engagement = interacciones / alcance × 100 y conversión sobre alcance = ventas atribuidas / alcance × 100; verificar cada plataforma y los agregados de 6,83 % y 0,0417 %, sin promediar porcentajes.
- [x] F2.8. Verificar el precio medio de venta de 81,33 € y el coste publicitario agregado por venta atribuida de 4,00 €; comprobar también los costes por venta de cada plataforma.
- [x] F2.9. Revisar CTR = clics / impresiones × 100 y ROAS = ingresos atribuidos / coste publicitario; confirmar que ambos permanecen no disponibles por falta de los datos exigidos, sin sustituir impresiones por alcance ni inventar atribución de ingresos.
- [x] F2.10. Revisar la fórmula de ROI de las especificaciones; confirmar que no se calculará por producto sin costes de inversión y beneficio atribuible, ni se sustituirá beneficio por comisiones brutas.
- [x] F2.11. Identificar las métricas sin datos en las secciones 6 y 7 de las especificaciones; preparar para cada una el estado y el motivo que se escribirá junto a ella, sin inventar ceros.
- [x] F2.12. Preparar los textos de separación entre vistas por producto, plataforma y campaña, y la nota de alcance no deduplicado; comprobar que no afirman una atribución detallada ni usuarios únicos.
- [x] F2.13. Aplicar el criterio de redondeo a los valores que se mostrarán: engagement con dos decimales, conversión sobre alcance con cuatro e importes según las especificaciones; usar «Sin datos» o «N/D» ante denominadores desconocidos o cero.

### Fase 3: bloque superior

- [x] F3.1. Construir la cabecera con «Influencer Analytics» y «Septiembre de 2026»; comprobar que ambos textos aparecen al inicio y solo existe un título principal.
- [x] F3.2. Añadir la nota visible «Datos simulados con fines académicos»; comprobar que no se oculta en pantallas pequeñas.
- [x] F3.3. Implementar el patrón de tarjeta KPI y las tarjetas de ventas, comisiones e ingresos por ventas; verificar etiquetas, unidades y valores de la fase 2, sin confundir las magnitudes económicas.
- [x] F3.4. Añadir tarjetas de precio medio de venta e interacciones totales; mantener estos dos indicadores entre los cinco destacados exigidos por las especificaciones.
- [x] F3.5. Incorporar las tarjetas de engagement sobre alcance, conversión sobre alcance y coste publicitario; mostrar el denominador de las tasas y la limitación del alcance agregado.
- [x] F3.6. Añadir la tarjeta CTR con «Sin datos» y el motivo «Faltan impresiones» con menor énfasis visual; comprobar que no muestra un porcentaje ficticio.
- [x] F3.7. Crear la tabla compacta de cobertura de volumen, ingresos, engagement, retención, rendimiento, satisfacción y eficiencia; verificar que ninguna categoría queda omitida.
- [x] F3.8. Completar las métricas sin datos, incluidas inscripciones, usuarios activos, impresiones, MRR, churn, permanencia, compleción, NPS, CSAT, margen y tiempos; mostrar un motivo y distinguir sus estados de un valor cero.
- [x] F3.9. Incorporar el coste publicitario por venta atribuida de 4,00 € en eficiencia; aclarar que las conversiones son ventas y que los indicadores repetidos no se suman.

### Fase 4: bloque intermedio

- [x] F4.1. Construir el funnel con alcance agregado de 360.000, 4.500 clics y 150 ventas; conservar las tres etapas en secuencia vertical con etiquetas y valores visibles.
- [x] F4.2. Añadir al funnel las notas de escala proporcional al alcance, alcance no deduplicado y ausencia de seguimiento individual; mantener los valores fuera del relleno y no mostrar abandonos ni etapas sin datos.
- [x] F4.3. Crear las comparaciones con barras HTML de alcance, interacciones, clics y ventas para las tres plataformas; usar una escala independiente por métrica y anchuras precalculadas respecto de su máximo.
- [x] F4.4. Incorporar la tabla compacta de engagement, conversión sobre alcance y coste por venta de cada plataforma; verificar valores, unidades y denominadores contra la fase 2.
- [x] F4.5. Representar las comisiones de A, B y C con barras normalizadas respecto de 900 €; acompañar los importes de las ventas por producto, sin asignarlas a plataformas.
- [x] F4.6. Crear la tabla de engagement por plataforma con interacciones totales y tasa sobre alcance; incluir me gusta, comentarios, compartidos y guardados como «Sin datos», sin repartir los totales.
- [x] F4.7. Incorporar ratio de leads cualificados, attendance rate y pass rate; mostrar su indisponibilidad por falta de recuentos y definición de eventos.
- [x] F4.8. Construir la tabla de actividad por plataforma con publicaciones, stories, reels y vídeos; mostrar los datos ausentes y reservar «No aplica» para formatos que realmente no correspondan, sin sumar formatos solapados.

### Fase 5: bloque inferior

- [x] F5.1. Construir la tabla de productos con precio, comisión unitaria, conversiones, ingresos por ventas, comisiones generadas y ROI; incorporar los datos revisados y totales solo donde proceda.
- [x] F5.2. Completar la columna ROI con «N/D» y una nota asociada de costes y beneficio atribuible faltantes por producto; comprobar que ningún producto presenta rentabilidad inventada.
- [x] F5.3. Construir la tabla de plataformas con alcance, interacciones, engagement, clics, conversiones, conversión sobre alcance, coste publicitario y coste por venta; verificar todas las filas con la fase 2.
- [x] F5.4. Identificar textualmente los líderes por métrica previstos en el plan; comprobar que no se presenta una plataforma ganadora universal ni el gasto como éxito por sí mismo.
- [x] F5.5. Construir la tabla de campañas A, B y C con las fechas y productos ilustrativos de las especificaciones; mantener resultados no disponibles y rendimiento no evaluable, sin atribuirles las 150 ventas.
- [x] F5.6. Añadir la nota de que nombres, fechas y asociaciones de las campañas son ejemplos ficticios independientes de los totales; comprobar que no se interpretan como atribución real.
- [x] F5.7. Incorporar las alertas de caídas, picos y anomalías con el motivo «No evaluable: faltan datos temporales y una referencia de comparación»; no añadir umbrales ni afirmar que no existen anomalías.
- [x] F5.8. Crear los listados ordenados de productos por ventas (A, B, C) y por comisiones (B, C, A); verificar posiciones y cifras.
- [x] F5.9. Crear el top plataformas por ventas (TikTok, Instagram, YouTube) con sus cifras y el top campañas como pendiente por falta de resultados atribuidos; no inventar una clasificación de campañas.
- [x] F5.10. Añadir las oportunidades de mejora ya definidas: revisión descriptiva de conversión y necesidad de impresiones, costes por producto y atribución de campañas; excluir promesas de causalidad o resultados futuros.

### Fase 6: diseño y revisión

- [x] F6.1. Aplicar la paleta, tipografía local y jerarquía de tamaños del plan; verificar consistencia entre etiquetas, cifras, encabezados y estados sin descargar fuentes.
- [x] F6.2. Unificar tarjetas, tablas y barras con los patrones de espaciado, bordes y esquinas de hasta 8 px; evitar tarjetas anidadas, animaciones y decoración innecesaria.
- [x] F6.3. Aplicar una columna en móvil, dos columnas de KPI desde `md:` y tres desde `lg:`; mantener los tres bloques siempre en orden vertical.
- [x] F6.4. Adaptar los drivers a dos columnas amplias solo cuando conserven legibilidad; verificar etiquetas largas, cifras fuera de las barras y alturas estables.
- [x] F6.5. Envolver las tablas anchas en contenedores con desplazamiento horizontal propio; comprobar que no se ocultan columnas, unidades o motivos y que la página no se desborda horizontalmente.
- [ ] F6.6. Completar la revisión con zoom nativo del navegador al 200 %. Ya se comprobaron anchos de 360, 768 y 1280, capturas de móvil y escritorio y reflow a 640 equivalente al espacio disponible con zoom del 200 % en escritorio, sin desbordamientos; el zoom nativo sigue pendiente de revisión manual.
- [x] F6.7. Comprobar contraste de texto normal de al menos 4,5:1 y estados comprensibles sin color; verificar también el acceso por teclado a las tablas desplazables cuando requieran foco.
- [x] F6.8. Validar el HTML y revisar idioma, encabezados, identificadores únicos, títulos de tablas y cabeceras con su alcance; corregir errores de marcado relevantes.
- [x] F6.9. Contrastar todas las apariciones de cifras con las especificaciones y las operaciones de la fase 2; comprobar totales, fórmulas, redondeos, rankings y separación entre ingresos, comisiones y costes.
- [x] F6.10. Verificar las longitudes proporcionales de las barras por grupo y del funnel sobre alcance; confirmar que todas las visualizaciones comunican sus valores mediante texto.
- [x] F6.11. Revisar el HTML y sus recursos para confirmar que solo usa HTML y el script CDN de Tailwind CSS v4; descartar JavaScript propio, archivos CSS, frameworks, librerías de gráficos, SVG, Canvas, API, datos externos y dependencias de backend o base de datos.
- [x] F6.12. Abrir el HTML directamente con conexión y comprobar que el CDN real carga y genera las clases finales, incluidas las anchuras estáticas, sin servidor ni compilación local.
- [x] F6.13. Recorrer uno por uno los trece criterios de aceptación de [specs/spec.md](spec.md); corregir cualquier incumplimiento antes de marcar la definición de terminado.

### Definición de terminado anterior

- [ ] Las tareas anteriores están completadas y sus resultados comprobados; no se confunde la existencia de este listado con una implementación realizada.
- [x] La entrega abre directamente con conexión al CDN, con un único script de Tailwind CSS v4 y sin JavaScript propio, archivos CSS, servidor ni tecnologías no permitidas.
- [x] La cabecera identifica «Influencer Analytics», septiembre de 2026 y el carácter académico de los datos simulados.
- [x] Los tres bloques contienen todos los KPI, drivers, tablas, estados de alertas y listados exigidos, sin funcionalidades añadidas.
- [x] Los totales de 150 ventas, 12.200 € en ingresos por ventas y 1.830 € en comisiones coinciden en todas sus apariciones; las tasas y demás cálculos respetan sus fórmulas y redondeos.
- [x] Las vistas agregadas permanecen separadas, el alcance no se presenta como usuarios únicos y no se inventan atribuciones ni resultados de campañas.
- [x] Las métricas sin datos muestran su estado y motivo; CTR, ROAS y ROI no se calculan sin los datos necesarios, y las alertas no aparentan detección automática.
- [ ] La página conserva legibilidad, jerarquía y tablas accesibles en los tamaños y el zoom revisados, sin solapamientos ni dependencia exclusiva del color.
- [x] Los trece criterios de aceptación de [specs/spec.md](spec.md) se han verificado sobre la página terminada y no quedan incumplimientos pendientes.

### Evidencia de verificación anterior

- HTML validado sin errores con html-validate, ejecutado fuera del proyecto. Un solo script CDN, sin `link`, `style`, estilos en línea, SVG, Canvas ni archivos CSS adicionales en la entrega.
- Chromium abrió el HTML mediante `file://` con conexión y cargó el CDN real de Tailwind v4, sin errores de página ni solicitudes fallidas.
- Comprobados anchos de 360, 768 y 1280: una, dos y tres columnas KPI, sin desbordamientos de página ni texto exterior recortado; tablas desplazables dentro de sus contenedores. Capturas de móvil y escritorio revisadas.
- Comprobado reflow adicional a 640. No sustituye la revisión pendiente con zoom nativo al 200 %.
- Verificados nueve KPI, siete categorías, siete tablas, filas de productos y plataformas, fórmulas y totales; campañas sin atribuciones inventadas y alertas no evaluables.
- Verificadas las proporciones de las 18 barras, referencias accesibles, contraste de texto de al menos 4,5:1 y desplazamiento de tabla con teclado.
- Las herramientas y capturas de prueba permanecen fuera del proyecto. La aplicación solo depende del CDN autorizado para sus estilos, no de datos externos.