# NovaRetail+: factores asociados al ingreso de clientes

Proyecto del bootcamp de Análisis de Datos de **TripleTen** (Sprint 8).

## Objetivo

Identificar qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual que genera cada cliente en NovaRetail+, una plataforma de comercio electrónico en Latinoamérica, durante 2024.

> Este es un análisis **correlacional** (exploratorio): describe asociaciones, no relaciones causales.

## Datos

- **15,000 clientes** y **12 variables**, sin valores nulos ni duplicados.
- Variables numéricas: edad, nivel de ingreso, visitas y compras mensuales, gasto en publicidad dirigida, satisfacción e ingreso anual.
- Variables binarias: membresía premium y abandono.
- Variables categóricas: tipo de dispositivo y región.

Archivo: `novaretail_comportamiento_clientes_2024.csv`

## Herramientas

Python · pandas · NumPy · Matplotlib · Seaborn · SciPy

## Metodología

1. Exploración y limpieza de datos (tipos, duplicados, distribuciones).
2. Visualización de relaciones (heatmap de correlaciones y scatterplots de pares clave).
3. Cálculo de coeficientes según el tipo de variable:
   - **Pearson y Spearman** para variables numéricas.
   - **Punto biserial** para variables binarias vs. numéricas.
   - **V de Cramér** para variables categóricas.
4. Verificación de correlaciones engañosas (relaciones por construcción y variables de confusión).
5. Interpretación de resultados para el negocio.

## Hallazgos principales

1. **El ingreso depende casi por completo del número de compras** (r = 0.97). Sin embargo, la relación se explica por cómo se genera el ingreso: cada compra aporta en promedio ≈ 30. El **30.4 % de los clientes no realizó compras**.
2. **Las visitas se asocian con el ingreso; la publicidad dirigida no.** La asociación aparente entre publicidad e ingreso (r = 0.20) desaparece al comparar clientes con un número similar de visitas (r entre 0.004 y 0.066): las visitas actúan como **variable de confusión**.
3. **El perfil del cliente aporta poca información sobre su valor.** Edad, nivel de ingreso personal, región y dispositivo no se asocian con el ingreso. La membresía premium muestra una asociación muy débil (r = 0.09) y el abandono ocurre en todos los niveles de ingreso.

## Recomendaciones

- Activar al 30.4 % de clientes sin compras, la mayor oportunidad de crecimiento.
- Usar la frecuencia de visitas como indicador temprano de potencial de compra.
- Validar el efecto de la publicidad dirigida con un **A/B test** antes de aumentar su presupuesto.
- Revisar la propuesta de valor del programa premium y las estrategias de retención.

## Limitaciones

- El análisis es correlacional y corresponde solo a 2024.
- No incluye variables como precios, promociones o categorías de producto.
- Con 15,000 registros, incluso correlaciones mínimas son estadísticamente significativas; las conclusiones se basan en la **magnitud** de los coeficientes.

## Estructura del repositorio

| Archivo | Descripción |
|---|---|
| `novaretail_analisis_correlacion.ipynb` | Notebook con el análisis completo |
| `novaretail_comportamiento_clientes_2024.csv` | Dataset utilizado |

## Cómo ejecutarlo

En la celda de carga de datos, reemplaza la ruta `/datasets/novaretail_comportamiento_clientes_2024.csv` por `novaretail_comportamiento_clientes_2024.csv` para leer el archivo incluido en este repositorio.

## Autor

**Stefan Loosveld** · Análisis de Datos
