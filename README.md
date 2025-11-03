# Clustering-of-Chemical-and-Toxic-Elements
Este repositorio contiene el **reporte estadístico anonimizado** de un estudio observacional con cuantificación de **elementos químicos y compuestos ambientales** en muestras biológicas. Se ha eliminado o generalizado cualquier referencia que pueda identificar el estudio, la institución, la cohorte o el diagnóstico específico.

## Alcance
- **Objetivo analítico:** caracterización descriptiva y multivariante de concentraciones y relaciones entre compuestos (p.ej. elementos traza, macroelementos, POPs/PCBs).
- **Audiencia:** equipo científico/técnico. El documento no revela ni centros, ni patologías específicas, ni fechas exactas.

## Flujo de trabajo (ETL → Análisis)
1. **Tratamiento y depuración**:
   - Carga de datos.
   - Renombrado/transformación de variables, manejo de valores perdidos y atípicos.
   - Estandarización de variables continuas.
   - Construcción de tablas de correlación y selección de subconjuntos.
2. **Análisis descriptivo:**
   - Resúmenes numéricos, gráficos de distribución y correlación.
3. **Modelado multivariante:**
   - **PCA** para exploración de estructura latente.
   - **Clustering no supervisado**: k-means (inicialización por centroides múltiples) e **jerárquico** con distancias robustas (Manhattan/Canberra) y enlaces average/complete.
4. **Comunicación de resultados:**
   - Tablas y figuras generadas con `kableExtra`, `ggplot2` y `ggpubr`.
   - Documento reproducible con **RMarkdown**.

## Paquetes principales (R)
`tidyverse`, `ggplot2`, `ggpubr`, `naniar`, `broom`, `pwr`, `nortest`, `car`, `kableExtra`, `gridExtra`, `ggfortify`, `reshape`.
