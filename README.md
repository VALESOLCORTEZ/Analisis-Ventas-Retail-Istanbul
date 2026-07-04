# Analisis-Ventas-Retail-Istanbul
 Análisis de ventas y comportamiento de clientes en el sector retail. Incluye proceso ETL en Python, diseño de base de datos normalizada en SQL , EDA y y extracción de KPIs para optimización de estrategias comerciales.
# Análisis de Ventas y Comportamiento de Clientes - Retail (Oriente Shopping)

**Proyecto Integrador (ABP) - Innovación de Datos | T.S. Ciencia de Datos e Inteligencia Artificial**

## Resumen del Proyecto
Este proyecto busca transformar datos transaccionales crudos en conocimiento estratégico para una importante firma de centros comerciales en la región metropolitana de Estambul. A través de un análisis sistemático de casi 100,000 transacciones, se identificaron patrones de compra, se normalizó una base de datos relacional y se detectaron oportunidades comerciales accionables.

- **Ventas Totales Analizadas:** $68.55 millones.
- **Volumen:** 99,457 transacciones únicas y 298,712 unidades vendidas.
- **Herramientas Utilizadas:** Python (Pandas, Matplotlib), SQL, Excel, Google Colab.

---

## Metodología y Fases del Proyecto

### 1. Extracción, Transformación y Carga (Proceso ETL)
El procesamiento inicial de los datos se realizó en Python (Google Colab) garantizando la calidad y consistencia de la información para el análisis posterior. Los pasos documentados incluyen:

- **Extracción:** Carga de los conjuntos de datos de clientes y ventas (`customer_data.csv` y `sales_data.csv`) utilizando la codificación `latin-1` para evitar errores con caracteres especiales.
- **Limpieza y Transformación:** 
  - Exploración inicial mediante `.head()` e `.info()` para identificar tipos de datos y valores nulos.
  - Estandarización de nombres de columnas (renombramiento de `ï»¿customer_id` a `customer_id`) para permitir la correcta integración.
  - **Imputación de datos:** Tratamiento de 119 valores nulos detectados en la columna `age` (edad) imputando la mediana estadística.
  - **Casteo de variables:** Conversión de la columna `invoice_date` de tipo `object` a formato estructurado `datetime` (`%d-%m-%Y`) para permitir el análisis temporal.
- **Carga (Merge):** Unificación exitosa de ambos DataFrames mediante la clave primaria `customer_id`, consolidando la base en un único dataset limpio preparado para el análisis exploratorio.

### 2. Modelado de Base de Datos (SQL)
Para garantizar la integridad y escalabilidad de los datos, se diseñó un modelo Entidad-Relación normalizado.
- Creación de una tabla temporal (`Staging_Data`) para la importación inicial masiva.
- Diseño e inserción de datos únicos en tres tablas maestras: `Customer`, `Shopping_Mall`, y `Product`.
- Construcción de una tabla de hechos (`Transaction`) enlazando las entidades mediante claves foráneas (Foreign Keys).

### 3. Análisis Exploratorio de Datos (EDA)
Se calcularon KPIs fundamentales (Ventas Totales, Cantidad Vendida, Valor Promedio por Transacción). Además, se agruparon los datos para descubrir tendencias por categoría de producto, método de pago, género, intervalos de edad y rendimiento por centro comercial.

---

## Hallazgos Clave e Insights de Negocio

1. **Rendimiento por Categoría:** Las categorías de Ropa, Calzado y Tecnología lideran indiscutidamente la facturación.
2. **Métodos de Pago:** El efectivo domina el volumen de transacciones, seguido por la tarjeta de crédito, lo cual representa una oportunidad de digitalización comercial.
3. **Segmentación Demográfica:** Las mujeres generan una proporción significativamente superior de ventas respecto a los hombres. El segmento etario más activo se ubica entre los 18 y 64 años.
4. **Comportamiento por Sucursal:** Los centros comerciales "Mall of Istanbul", "Kanyon" y "Metrocity" lideran en volumen de ventas, indicando ubicaciones estratégicas de alto tráfico.

## Recomendaciones Estratégicas
- Impulsar categorías de bajo rendimiento (Libros, Souvenirs, Alimentos) mediante reubicación estratégica y promociones.
- Fomentar la digitalización y el uso de tarjetas mediante incentivos para mejorar la eficiencia operativa.
- Diseñar campañas de marketing dirigidas específicamente al segmento masculino y a grupos etarios menos representados para ampliar la cuota de mercado.

---
*Este proyecto fue desarrollado en colaboración académica por el equipo: Amaya P., Cortez V., Manrique A., Martinez C., Melchiorre M.
