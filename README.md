# 📈 Dashboard Comercial y Análisis de Desempeño (2024–2025) | Andes Retail Group

---

## 🎯 Contexto y Desafío de Negocio

**Andes Retail Group** opera en **Perú, Chile y Colombia** comercializando productos en cuatro categorías: **Electrónica, Ropa, Deportes y Hogar** a través de tres segmentos de clientes (**Consumidor, PyME y Corporativo**).

El negocio gestionaba ~10,000 transacciones sin una visión analítica unificada. La dirección ejecutiva requería una solución de inteligencia de negocios para responder a 6 preguntas clave sobre el desempeño 2024–2025:

1. **Evolución Temporal:** ¿Cómo han evolucionado los ingresos 2024 vs. 2025 y cuáles son los meses críticos?
2. **Segmentación:** ¿Qué segmentos generan mayor volumen e ingreso de ganancia?
3. **Impacto por Categoría:** ¿Cuál es la participación de Electrónica, Ropa, Deportes y Hogar?
4. **Desempeño Geográfico:** ¿Existen desviaciones o brechas de desempeño entre países y regiones?
5. **Estacionalidad:** ¿Cómo afectan las estaciones climáticas (Verano, Invierno, Primavera, Otoño) la venta?
6. **Oportunidades:** ¿Dónde están los cuellos de botella del negocio (¿Problema de margen o de volumen?)?

---

## 🛠️ Metodología y Modelo de Datos

* **Limpieza y Preparación (Python):** Validación de 5,000+ registros transaccionales, estandarización de tipos de datos (`Ingresos` y `Precio Unitario` a decimales), formato regional en español y creación de variables condicionales (`Nivel_Venta`).
* **Modelado y Campos Calculados:** Implementación de fórmulas de negocio para `Ganancia = Ingresos - Costo`, `% Margen de Ganancia = (Ganancia / Ingresos) * 100`, `YoY Growth` y agrupación por estaciones del año.
* **Arquitectura de Dashboard (2 Vistas):**
  * **Vista 1: Overview Ejecutivo:** Diseñada para lectura en segundos por directivos (KPIs principales, evolución temporal, categorías y oportunidades por país).
  * **Vista 2: Análisis Detallado:** Diseñada para analistas (Análisis de estacionalidad clima × categoría, dispersión Ingresos vs. Margen y tabla comparativa).

---

## 💡 Informe Ejecutivo (Framework SCQA)

### 🖥️ 1. Vista General (Overview)

* **S (Situación):** Andes Retail Group generó **$1,942K en ganancia total** entre 2024 y 2025 a través de sus operaciones en Perú, Chile y Colombia, manteniendo un margen saludable y consistente del **35.1%**.
* **C (Complicación):** Los ingresos del año **2025 sufrieron una caída del -6.7% frente a 2024**, afectando incluso a diciembre, tradicionalmente el mes más fuerte del año.
* **Q (Pregunta):** ¿Dónde se genera el valor del negocio hoy y qué palancas deben activarse para revertir la caída sin perder rentabilidad?
* **A (Respuesta):** Electrónica y Deportes concentran la mayor venta, mientras que los segmentos *Corporativo* y *Consumidor* aportan el volumen principal. Al evaluar el margen por corte (~35%), descubrimos que **la rentabilidad no se ha degradado**. El problema es estrictamente de **caída en volumen de ventas**, por lo que la prioridad comercial debe ser recuperar tracción transaccional y no ajustar precios o costos.

---

### 🔎 2. Vista Detalle (Deep-Dive Estacional y Geográfico)

* **S (Situación):** Tras detectar la caída en volumen, el desglose temporal muestra un patrón estacional severo: las categorías de **Ropa y Hogar** caen drásticamente en temporada baja, mientras que **Deportes** mantiene una demanda estable todo el año.
* **C (Complicación):** El margen porcentual se mantiene plano e idéntico en todos los cortes analizados (entre **34.8% y 35.5%**). Sin embargo, las ventas en **Verano son 3.4 veces superiores a las de Invierno** ($2.24M vs. $653K) y Colombia genera **38% menos ganancia total** que Perú ($470K vs. $760K).
* **Q (Pregunta):** Si el margen es idéntico entre países y estaciones, ¿qué causa las enormes brechas de ganancia neta?
* **A (Respuesta):** La brecha es de **volumen operativo, no de eficiencia de precios**. Colombia y la temporada de Invierno venden a los mismos márgenes saludables de ~35%, pero procesan un número significativamente menor de transacciones. La oportunidad está en activar la demanda en temporada baja y expandir la cobertura comercial en Colombia.

---

## 🔍 Hallazgos Clave

| Dimensión Analizada | Métrica / Ratio | Diagnóstico de Negocio |
| :--- | :---: | :--- |
| **Evolución Interanual (YoY)** | **-6.7%** (2025 vs 2024) | Pérdida de volumen transaccional en 2025 con impacto en Q4. |
| **Estacionalidad (Verano vs Invierno)** | **3.4x** diferencia | Fuerte dependencia estacional; contracción severa en Invierno. |
| **Eficiencia de Margen** | **34.8% – 35.5%** | Margen **ultra consistente** en todos los países, categorías y estaciones. |
| **Mercado Líder en Ganancia** | **Perú ($760K)** | Supera a Colombia ($470K) por mayor volumen de transacciones. |
| **Categoría Resiliente** | **Deportes** | Única categoría que mitiga caídas en temporadas frías. |

---

## 🚀 Recomendaciones de Negocio & Próximos Pasos

1. **Estrategia Anti-Cíclica para Invierno:** Lanzar promociones y paquetes especiales en las categorías de **Ropa y Hogar** durante el bimensual de menor tráfico para suavizar el valle estacional de Invierno.
2. **Plan de Expansión de Volumen en Colombia:** Replicar la estrategia de distribución y alcance de Perú en el mercado colombiano; al tener márgenes sanos (~35%), cada incremento en volumen se traducirá directamente en ganancia neta.
3. **Fidelización del Segmento Corporativo:** Desarrollar acuerdos comerciales B2B exclusivos para clientes corporativos, quienes registran el mayor ticket promedio y aportación de ganancia.

---

## 💬 Comunicación Asincrónica de Negocio (Ejemplo Slack)

> **📊 Actualización Desempeño Comercial | Andes Retail Group**  
> Equipo, comparto el diagnóstico ejecutivo 2024–2025:  
> El **margen de ganancia es impecable y consistente (~35%)** en todos los países y categorías, pero registramos una **caída de ingresos del -6.7% en 2025** impulsada por volumen.
>
> **2 Hallazgos Clave:**  
> 1️⃣ **Efecto Clima:** Verano vende **3.4x más que Invierno** ($2.24M vs. $653K).  
> 2️⃣ **Oportunidad Geográfica:** Colombia tiene el mismo margen que Perú (~35%), pero genera $290K menos de ganancia por menor volumen.
>
> **Propuesta de Acción:**  
> • Activar campaña promocional estacional en Invierno para reactivar categorías frías (Ropa/Hogar).  
> • Auditar cobertura de marketing y ventas en Colombia antes de tocar precios o costos.

---

## 📁 Estructura del Repositorio

```text
├── README.md                         <- Presentación del proyecto e informe ejecutivo
├── dashboard_andes_retail.twbx       <- Archivo fuente del Dashboard interactivo en Tableau
└── datasets/
    ├── dataset_andes_retail.csv      <- Dataset transaccional (5,000 registros)
    └── jupyter_exploracion.ipynb     <- Código Python de limpieza y validación de datos
