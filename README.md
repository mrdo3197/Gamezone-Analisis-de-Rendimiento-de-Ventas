# Análisis de Rendimiento de Ventas para GameZone: Monitoreo Mensual de Ingresos por Producto, Plataforma y Canal (2019-2023)

# Contexto del Proyecto
Gamezone, fundada en 2018, es una empresa global de comercio electrónico especializada en la venta de productos de videojuegos nuevos y reacondicionados. Opera principalmente a través de su sitio web y aplicación móvil, atendiendo a clientes en múltiples regiones del mundo. Su modelo de negocio se centra en la venta directa al consumidor, con un portafolio que incluye consolas, accesorios y equipos especializados.

Recientemente, la compañía ha observado una desaceleración en el crecimiento de ventas posterior al auge de 2020. Este proyecto tiene como objetivo analizar los datos históricos de ventas (2019-2023) para proporcionar a los gerentes de ventas y marketing un panel de control que les permita monitorear el rendimiento mensual de ingresos y tomar decisiones informadas para optimizar la estrategia comercial.

El dashboard está diseñado para ayudar a el equipo de ventas a explorar el rendimiento de ventas a través de las siguientes dimensiones clave:

**- Tendencias de Ventas:** Evaluación de la evolución mensual de ingresos totales, permitiendo comparaciones entre mes actual vs. mes anterior dentro del mismo año, así como mes actual vs. mismo mes del año anterior para identificar patrones estacionales y cambios estructurales en el negocio.

**- Rendimiento por Categoría/Producto:** Análisis del portafolio para identificar qué productos son los principales impulsores de ingresos y cómo ha evolucionado su contribución en el tiempo.

**- Segmentación por Plataforma:** Comparación del rendimiento de ingresos entre sitio web y aplicación móvil para determinar patrones de compra y oportunidades por plataforma.

**- Efectividad por Canal de Marketing:** Evaluación del desempeño de los canales de adquisición en términos de ingresos generados, para optimizar la asignación de presupuesto y maximizar el retorno de inversión.

Este dashboard está diseñado para ser revisado mensualmente por el equipo de ventas, permitiendo un seguimiento ágil de los ingresos y la rápida identificación de áreas de oportunidad o riesgo.

Las consultas de SQL utilizados para inspeccionar y limpiar los datos para este análisis se pueden encontrar aquí [link](https://github.com/mrdo3197/Gamezone-Analisis-de-Rendimiento-de-Ventas/blob/main/etl_gamezone.sql).

Un dashboard interactivo de Tableau utilizado para reportar y explorar tendencias de ventas se puede encontrar aquí [link](https://public.tableau.com/views/Proyecto_Gamezone_Ingresos_marketing/Dashboard1?:language=es-ES&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

# Estructura de Datos y Chequeos Iniciales

Los datos de pedidos de Gamezone están alojados en una sola tabla (ver imagen), que contiene 54.318 registros, donde cada registro representa un ítem único en el pedido de un cliente. Esta estructura es ideal para analizar el rendimiento de productos desde múltiples dimensiones.

<img width="279" height="294" alt="imagen" src="https://github.com/user-attachments/assets/02c85e83-b3a1-4acb-af6b-8c235fd13597" />


Anterior al comienzo del análisis, una variedad de chequeos fueron llevados a cabo con el fin de asegurar el control de calidad así como la familiarización con el conjunto de datos. Las consultas en SQL utilizadas para la inspección y limpieza de los datos puede ser encontrada aquí [link](https://github.com/mrdo3197/Gamezone-Analisis-de-Rendimiento-de-Ventas/blob/main/etl_gamezone.sql).

# Resumen Ejecutivo

A continuación se desglozan cada una de las dimensiones analizadas. El dashboard interactivo puede ser consultado aquí [link](https://public.tableau.com/views/Proyecto_Gamezone_Ingresos_marketing/Dashboard1?:language=es-ES&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

### Tendencias de Ventas:

El análisis de ingresos de GameZone (2019-2023) revela dos patrones fundamentales que definen la dinámica del negocio:

* **Estacionalidad consistente y predecible:** Los ingresos alcanzan sus niveles más altos entre septiembre y diciembre, impulsados por la temporada navideña y campañas de fin de año. Por el contrario, los meses de inicio de año (enero-febrero) registran sistemáticamente los valores más bajos, reflejando una desaceleración post-temporada alta.

* **Normalización post-pandemia:** Tras los máximos históricos alcanzados a finales de 2021 (impulsados por el augo del gaming durante el confinamiento), los ingresos se han estabilizado en niveles similares a 2020. Esta corrección era esperable a medida que la vida social retomó su curso normal. Aunque febrero 2023 muestra una mejora del +8,6% vs. 2022, la caída del -3% vs. el mes anterior refleja la desaceleración típica de inicio de año, confirmando que el patrón estacional se mantiene.

<img width="362" height="308" alt="imagen" src="https://github.com/user-attachments/assets/5feb028a-576e-45ea-836c-116ca14f0fe9" /> <img width="363" height="340" alt="imagen" src="https://github.com/user-attachments/assets/c0720db0-fa74-4172-aff4-66a7181cca15" />


### Rendimiento por Categoría:

* **Alta concentración en dos categorías:** El portafolio de GameZone está fuertemente concentrado en Consolas y Monitores, que en conjunto representan el 85,8% de los ingresos totales. Esta dependencia estructural implica que cualquier fluctuación en estas categorías (problemas de stock, cambios en demanda, competencia) impacta directamente los resultados globales de la compañía. Categorías como Audífonos y Periféricos tienen una contribución marginal (apenas 2% combinado).

* **Consolas, el motor del negocio:** La categoría lidera con $211.334 en febrero 2023 (60,6% de participación) y un sólido crecimiento anual del +34,5%. Este desempeño indica que la demanda por consolas de nueva generación (especialmente PS5) se mantiene fuerte, incluso en un contexto de desaceleración general.

* **Audífonos, señal emergente:** A pesar de su bajo volumen (1,3%), la categoría registró el mayor crecimiento mensual (+25,4%). Este repunte podría deberse a una promoción reciente, al lanzamiento de un nuevo modelo (JBL Quantum), o a una tendencia estacional atípica.

* **Gaming Laptops, foco de alerta**: Es la categoría con peor desempeño absoluto y relativo, con caídas dramáticas tanto mensuales (-39,1%) como anuales (-32,7%). Las posibles causas incluyen: fin del ciclo de vida de productos actuales, alta competencia en el segmento, problemas de abastecimiento, o un cambio en las preferencias del consumidor hacia consolas portátiles (Steam Deck, ASUS ROG Ally).

<img width="583" height="292" alt="imagen" src="https://github.com/user-attachments/assets/563e7407-7fb3-4fd5-8dc2-e5022115f39f" />


### Rendimiento por Producto:

* **Alta concentración en 3 productos:** El 86% de las ventas depende de solo tres productos: Sony PlayStation 5 Bundle (40%), 27in 4K gaming monitor (25,2%) y Nintendo Switch (20,7%). Esta concentración extrema representa un riesgo significativo: una caída en la demanda, problemas de stock o la aparición de competidores fuertes en cualquiera de estos productos afectaría desproporcionadamente los resultados de la compañía.

* **PS5 Bundle, el producto estrella:** Con $139.269 en ingresos (40% del total) y un crecimiento anual explosivo del +84,8%, el PS5 Bundle es el principal impulsor del negocio. Este crecimiento refleja tanto la demanda acumulada por posibles problemas de stock en años anteriores como la fortaleza de la marca PlayStation.

* **27in 4K Monitor, sólido y estable:** Segundo producto en ventas, con crecimiento mensual del +11,9% y una leve caída anual (-4,9%) atribuible a la normalización post-pandemia. Es un producto confiable que sostiene la categoría Monitores.

* **Nintendo Switch, madurez y declive:** Aunque aún aporta el 20,7% de los ingresos, la caída anual del -11,9% sugiere que el producto está llegando al final de su ciclo de vida (lanzado en 2017), anticipando el lanzamiento de una posible nueva consola por parte de Nintendo.

* **Gaming Laptops (Lenovo IdeaPad y Acer Nitro), crisis profunda:** Ambos productos muestran caídas severas:

    * Lenovo IdeaPad: -37,5% mensual y -32,6% anual
    * Acer Nitro V: -54,9% mensual y -33,9% anual

    lo que se traduce en una pérdida combinada de $27.000 en un solo mes. posiblemente por el fin de ciclo de vida, competencia agresiva de otras marcas, problemas de stock, o desplazamiento de demanda hacia consolas portátiles.

* **JBL Quantum Headset, oportunidad emergente:** A pesar del bajo volumen (1,3%), tiene el mayor crecimiento mensual (+23,3%). La causa podría ser una campaña de marketing específica, buena recepción del producto, o estacionalidad.

* **Razer Pro Headset:** Con $81 (0,02% de ingresos) y ventas intermitentes (periodos de $0), el costo de mantener este producto en inventario probablemente supera su contribución.

* **Dell Gaming Mouse, marginal y estable:** Aporta solo 0,7% de ingresos con variaciones mínimas.

<img width="582" height="362" alt="imagen" src="https://github.com/user-attachments/assets/288976b6-c376-40c4-98b4-bd0fb0deb5b5" />



### Segmentación por Plataforma:

* **Web, plataforma dominante y estable:** Representa entre el 75% y 97% de los ingresos según el año. Es el canal de compra principal, con una temporada alta extendida de agosto a diciembre (pico en diciembre). En febrero 2023 alcanzó $268.415, con un sólido crecimiento anual del +12% y una leve mejora mensual (+0,8%), sugiriendo una posible recuperación tras dos años de normalización a la baja.

* **App, secundaria pero con potencial:** Pasó de ser irrelevante (<3% antes de 2021) a representar ~25% de los ingresos en 2021-2023, consolidándose como un canal complementario importante. Su estacionalidad es más concentrada (septiembre-diciembre). Sin embargo, después de un buen enero (+18% anual), frenó en febrero con una caída mensual del -14,1% y la primera contracción anual (-1,3%). Posiblemenrte por problemas de UX en la última actualización, menor promoción de la App, o cambios en el comportamiento del usuario post-pandemia.

* **Evolución histórica:**

    * Web: Crecimiento explosivo en 2020 (+163%), pico en 2021, y dos años de normalización. Febrero 2023 sugiere un punto de inflexión positivo.
    * App: Explosión en 2021 (+1.455%), seguida de dos años de declive, aunque manteniendo participación (~25%). La caída reciente podría indicar que el crecimiento post-pandemia se ha estabilizado a la baja.
  
<img width="475" height="349" alt="imagen" src="https://github.com/user-attachments/assets/f60f5188-de92-429a-beab-4caace94b825" />



### Efectividad por Canal de Marketing:

* **Directo, el pilar del negocio:** Representa 63% de los ingresos, con crecimiento anual sólido (+13,0%) y estabilidad mensual (+0,5%). Este canal refleja la fortaleza de la marca y la recurrencia de clientes existentes.

* **Email, secundario y en crecimiento:** Aporta 23% de ingresos con un crecimiento anual muy fuerte (+33,3%), aunque con una leve caída mensual (-3,8%) que podría deberse a variaciones estacionales en las campañas. Es el canal con mejor retorno después de Directo.

* **Búsqueda de Pago, oportunidad emergente:** Con solo 3,3% de participación, registró un crecimiento mensual explosivo (+132,5%) y anual positivo (+10,7%). Probablemente debido a campañas recientes bien segmentadas o estacionalidad atípica.

* **Afiliados y Redes Sociales: en crisis:** Ambos canales muestran caídas severas:

    * Afiliados: -34,9% mensual, -22,9% anual
    * Redes Sociales: -19,6% mensual, -42,5% anual

    Asociadas a cambios en algoritmos, menor inversión, contenido inefectivo o programas de afiliados poco atractivos. Se requiere una revisión crítica.

<img width="495" height="245" alt="imagen" src="https://github.com/user-attachments/assets/132ae2b3-4b9b-4d72-bcb0-076456609dd9" />



# Recomendaciones:

De acuerdo con los hallazgos anteriormente mencionados, se recomienda considerar lo siguiente:

* Con $139.269 (40% de ingresos), el PS5 Bundle es el producto más importante de GameZone. **Se recomienda garantizar stock constante, priorizar su visibilidad en campañas y optimizar la experiencia de compra en Web y App.**
* Con $87.868 (25,2% de ingresos), el monitor 4K es un pilar estable de la categoría Monitores. **Mantener la estrategia actual y monitorear su evolución anual.**
* Con una pérdida combinada de $27.000 en un solo mes, la categoría Gaming Laptops enfrenta una crisis profunda. **Se requiere investigar causas (stock, obsolescencia, competencia) y, si la tendencia no se revierte, evaluar descontinuación o reemplazo.**
* A pesar de aportar el 20,7% de ingresos ($72.065), la caída anual del -11,9% anticipa el fin de su ciclo de vida ante la confirmación de una nueva consola por parte de Nintendo. **Se recomienda una estrategia de transición que incluya liquidar inventario mediante bundles y asegurar disponibilidad de la nueva consola para capturar la demanda emergente.**
* Con $4.598 (1,3% de ingresos) y el mayor crecimiento mensual (+23,3%), JBL Quantum Headset representa una oportunidad para diversificar un portafolio concentrado en 3 productos (86% de ventas). **Asignar presupuesto de marketing por 90 días para evaluar si el crecimiento se sostiene.**
* Razer Pro Headset con $81 mensuales (0,02% de ingresos) y ventas intermitentes, su costo de inventario supera su contribución. **Evaluar discontinuación y liquidar stock restante.**
* Dell Gaming Mouse Con $2.579 (0,7% de ingresos) y estabilidad, **mantener sin inversión activa y monitorear trimestralmente.**
* Web es la plataforma dominante (75-97% de ingresos) con $268.415 en febrero y temporada alta de agosto a diciembre. **Mantener estrategia, aprovechar ventana para campañas y optimizar UX.**
* App representa ~25% de ingresos pero cayó -14,1% M/M y -1,3% A/A en febrero. **Investigar causas (UX, bugs, promoción) e implementar incentivos exclusivos (descuentos, envío gratis) para reactivar su uso.**
* Con temporada alta de agosto a diciembre (pico en diciembre) y valles en enero-febrero en ambas plataformas, se recomienda **incorporar estos patrones en la planificación anual de inventario, marketing, caja y contrataciones para una operación más eficiente.**
* Directo: $218.861 (63% de ingresos). **Proteger con experiencia de usuario fluida y fidelización.**
* Email: $80.437 (23,2% de ingresos). **Mantener estrategia e investigar leve caída mensual (-3,8%).**
* Búsqueda de Pago: +132,5% M/M con solo 3,3% de participación. **Asignar presupuesto de prueba para evaluar escalabilidad.**
* Afiliados: -34,9% M/M y -22,9% A/A con 5,9% de ingresos. **Revisar programa y reasignar presupuesto si no hay mejora.**
* Redes Sociales: -42,5% A/A con 4,9% de ingresos. **Auditar estrategia y pausar inversión si no hay reactivación clara.**


# Supuestos y Consideraciones:

A lo largo del análisis, se realizaron varios supuestos para abordar los desafíos presentados con los datos. Estos supuestos y limitaciones se detallan a continuación:

* **Valores nulos en fechas de compra y precio:** Las filas con fechas de compra ausentes (1 registro, 0,001%) y precios en blanco (5 registros, 0,009%) se mantuvieron como valores nulos en lugar de eliminarlas o imputarlas, dado su impacto marginal en los resultados agregados. Esta decisión evita introducir sesgos sin comprometer la integridad del análisis.
* **Transacciones con precio cero:** Se identificaron 34 transacciones (0,062%) con precio cero. Ante la falta de contexto sobre si corresponden a promociones, errores o productos de prueba, se optó por mantener estos registros sin modificar para no distorsionar los cálculos de ingresos totales.
* **Duplicados parciales:** Se identificaron dos tipos de duplicados parciales:

    * 108 registros (0,198%) donde solo difiere la columna cliente_id.
    * 2 registros (0,003%) donde solo difiere la columna metodo_registro.

Ante la falta de contexto para determinar cuál es el registro correcto, se conservaron ambas versiones, asumiendo que podrían corresponder a casos legítimos (múltiples usuarios en un mismo pedido, o actualizaciones en el método de registro). Estos duplicados tienen un impacto insignificante en los resultados agregados.

* **Columnas no incluidas en el alcance del análisis:** El presente análisis se centró exclusivamente en las dimensiones definidas en los objetivos del proyecto: tendencias de ventas, rendimiento por categoría/producto, segmentación por plataforma y efectividad por canal de marketing. En consecuencia, las columnas cliente_id, pedido_id, producto_id, fecha_envio y metodo_registro no fueron utilizadas, al no ser relevantes para responder las preguntas de negocio planteadas por el equipo de ventas y marketing. Estas variables podrían ser valiosas para análisis futuros, como estudios de retención de clientes, seguimiento de pedidos individuales o evaluaciones de métodos de registro.
