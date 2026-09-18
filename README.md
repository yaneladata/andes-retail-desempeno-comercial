# 📈 Dashboard Comercial y Análisis de Desempeño (2024–2025) | Andes Retail Group

> 👤 **Rol:** Analista de Datos (Proyecto Individual)  
> 🏢 **Contexto:** Caso de Negocio / Proyecto de Portafolio (Bootcamp Analytics)  
> 🎯 **Alcance:** Proceso End-to-End (Exploración y preparación de datos en Python, diseño de Dashboard en Tableau y narrativa ejecutiva SCQA).  
> 🛠️ **Stack Técnico:** Tableau Desktop, Python (Pandas/Jupyter), Modelado Dimensional, Campos Calculados, Framework SCQA.

---

## 🎯 Contexto y Desafío de Negocio

**Andes Retail Group** es una empresa de retail con operaciones transaccionales en **Perú, Chile y Colombia**, comercializando productos a través de cuatro categorías principales: **Electrónica, Ropa, Deportes y Hogar** en tres segmentos de clientes (**Económico, Estándar y Premium**).

El dataset contiene **5,000 registros transaccionales (12 campos)** del período 2024–2025. La dirección ejecutiva requería una visión analítica unificada mediante dos dashboards integrados (Vista General + Vista Detallada) para responder a 6 preguntas clave de negocio:

1. **Evolución Temporal (YoY):** ¿Cómo evolucionan los ingresos entre 2024 y 2025 e identificando meses críticos?
2. **Segmentación de Clientes:** ¿Qué segmentos aportan mayor ingreso y rentabilidad?
3. **Impacto por Categorías:** ¿Qué categorías tienen mayor impacto en el negocio?
4. **Desempeño Geográfico:** ¿Cuáles son las diferencias de rentabilidad entre países y regiones?
5. **Estacionalidad Climática:** ¿Existen patrones temporales/estacionales a lo largo del año?
6. **Oportunidades Comerciales:** ¿Dónde están los focos de mejora (¿Problema de volumen o de eficiencia de margen?)?

---

## 🛠️ Conexión, Exploración y Preparación de Datos

Durante la fase de auditoría e ingeniería de datos en el Notebook/Power Query, se realizaron las siguientes validaciones y transformaciones:

* **Calidad de Datos:** Evaluación de 5,000 filas y 12 columnas. No se encontraron registros nulos ni errores de consistencia.
* **Ajuste de Tipos de Datos:**
  * `Ingresos` y `Precio Unitario`: Convertidos de entero a decimal para precisión financiera.
  * `Costo`: Mantenido como decimal.
  * `Unidades Vendidas`: Mantenido como entero.
  * `Fecha_Pedido`: Estandarizado a formato fecha regional en español (Latinoamérica).
* **Campos Calculados & Variables Condicionales:**
  * `Ganancia` $= \text{Ingresos} - \text{Costo}$
  * `Margen_Ganancia (%)` $= (\text{Ganancia} / \text{Ingresos}) \times 100$
  * `Nivel_Venta`: Columna condicional creada donde $\text{Ingresos} \ge 1000 \rightarrow \text{"Venta Alta"}$, de lo contrario $\text{"Venta Baja"}$.
  * `País-Región`: Concatenación para análisis geográfico granular.

---

## 🖼️ Estructura del Dashboard y Visualizaciones

El proyecto se estructuró bajo una jerarquía visual estratégica: **KPIs en la zona superior**, **gráficos principales en la zona media** y **desgloses detallados/tablas en la zona inferior**.

### 🖥️ Vista 1: Overview Ejecutivo (Vista General)
*Diseñada para que directivos entiendan el estado global del negocio en 30 segundos.*

* **KPIs Principales:** Ingresos Totales ($5.532K), Unidades Vendidas (57,601), Ganancia Total ($1,942K) y % Margen de Ganancia (35.1%).
* **Evolución de Ingresos (Líneas):** Compara mes a mes 2024 vs 2025 para detectar la caída interanual.
* **Rentabilidad Geográfica (Barras Horizontales):** Muestra el margen por País-Región (resaltando Colombia-Sur con 34.9%).
* **Ingresos y Ganancia por Segmento (Columnas Agrupadas):** Compara el aporte de los segmentos Económico, Premium y Estándar.
* **Impacto por Categoría de Producto(Barras Horizontales):** Muestra la contribución de Deportes, Electrónica, Hogar y Ropa.

![Visión General](visualizaciones/vision_general.png)

---

### 🔎 Vista 2: Análisis Detallado (Deep-Dive Estacional)
*Diseñada para que analistas exploren causas de fondo y patrones de comportamiento.*

* **Ingresos Mensuales por Estación (Líneas por Clima):** Identifica el comportamiento de ventas a lo largo del año según la estación.
* **Rentabilidad por Estación y Categoría de Producto (Barras Apiladas):** Evalúa qué categorías sostienen la ganancia en Verano, Otoño, Invierno y Primavera.
* **Rentabilidad por País-Región y Categoría de Producto (Barras Apiladas):** Compara la mezcla de producto por zona geográfica.
* **Scatter Diagnóstico (Dispersión Ingresos vs % Margen):** Cruza volumen de ventas contra eficiencia de margen con líneas de referencia promedio para aislar el problema real de negocio.
* **Tabla Comparativa Final:** Presenta el desglose con conteo de pedidos, clientes únicos, ganancia y % de margen.

![Visión Detallada](visulizaciones/vision_detallada.png)

---

## 💡 Informe Ejecutivo (Framework SCQA)

### 🖥️ 1. Vista General (Overview)
* **S (Situación):** Andes Retail Group opera en Perú, Chile y Colombia en cuatro categorías. Entre 2024 y 2025 generó **$1,942K en ganancia total**, con un margen bruto constante del **35.1%**.
* **C (Complicación):** El negocio se desaceleró: **los ingresos de 2025 cayeron un -6.7% frente a 2024**, afectando incluso a diciembre (mes de mayor pico histórico).
* **Q (Pregunta):** ¿Dónde está generando valor el negocio hoy y dónde existen palancas claras de mejora sin necesidad de un diagnóstico complejo?
* **A (Respuesta):** Electrónica y Deportes lideran en volumen, mientras que los segmentos *Premium* ($2.598K ingresos) y *Estándar* ($2.437K ingresos) aportan el mayor valor absoluto. Al ser el margen casi idéntico en todos los cortes (~35%), **el problema no es de eficiencia de costos ni de precios, sino de pérdida de volumen de ventas**. La prioridad debe ser recuperar volumen comercial.

---

### 🔎 2. Vista Detalle (Análisis Estacional y Geográfico)
* **S (Situación):** El análisis de fondo revela patrones estacionales marcados: **Ropa y Hogar** sufren caídas drásticas en temporada baja, mientras que **Deportes** se mantiene estable todo el año. El margen de ganancia se mantiene increíblemente plano entre el **34.8% y el 35.5%** en todos los países, categorías y estaciones.
* **C (Complicación):** A pesar de tener la misma eficiencia de margen, **Verano vende 3.4 veces más que Invierno** ($2,241,719 vs $653,513) y Colombia genera un 38% menos de ganancia que Perú ($470K vs $760K).
* **Q (Pregunta):** Si el margen de ganancia es el mismo en todos los cortes, ¿qué causa estas brechas tan marcadas?
* **A (Respuesta):** La diferencia es estrictamente de **volumen de ventas, no de margen de ganancia**. Perú genera más ganancia ($760K) que Colombia ($470K) porque procesa más transacciones, no porque venda con mayor margen. Para activar el negocio se deben enfocar campañas para levantar el volumen en Invierno y expandir la cobertura comercial en Colombia.

---

## 💬 Comunicación Asincrónica para el Equipo (Slack)

> **📊 Actualización Desempeño Comercial | Andes Retail Group**  
> Equipo, el **Margen de Ganancia es ultra consistente (~35%)** en todos los cortes, pero los **ingresos cayeron -6.7% en 2025** frente a 2024.
>
> **2 Hallazgos Clave:**  
> 1️⃣ **Verano vende 3.4x más que Invierno** ($2.24M vs. $653K) → Oportunidad clara de campañas en temporada baja.  
> 2️⃣ **Colombia tiene el mismo margen que Perú/Chile pero vende menos** → El problema es volumen transaccional, no eficiencia.
>
> **Propuesta de Acción:**  
> • Diseñar una promoción estacional para reactivar Ropa y Hogar durante Invierno.  
> • Evaluar cobertura de marketing y distribución en Colombia antes de tocar costos o precios.

---

## 📁 Estructura del Repositorio

```text
├── README.md                         <- Presentación del proyecto e informe ejecutivo
├── visualizaciones/
     ├── vision_general.png            <- Captura de la Vista Overview del Dashboard
│    ├── vision_detallada.png         <- Captura de la Vista Detallada del Dashboard
└── datasets/
    ├── dataset_andes_retail.csv       <- Dataset transaccional (5,000 registros)
└── notebook/
    ├── S10Proyecto.ipynb              <- Código Python de limpieza y validación de datos
