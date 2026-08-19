# Análisis Financiero — Pizzas & Pastas (2025)

Análisis de un año completo (365 días) de ventas, gastos y utilidad de un restaurante real, a partir de su registro contable diario en Excel.

## Contexto

Este proyecto parte de datos operativos reales de un negocio, no de un dataset de práctica. El objetivo fue transformar un registro manual en Excel en un análisis que responda preguntas de negocio concretas y sea la base de un dashboard de monitoreo continuo (Power BI, en desarrollo).

## Preguntas de negocio

1. ¿Cómo evolucionaron las ventas y la utilidad mes a mes?
2. ¿Qué día de la semana es más rentable?
3. ¿Cómo cambió la mezcla de métodos de pago a lo largo del año?
4. ¿Qué tan estable es el margen de gastos mes a mes?
5. ¿Qué días operaron en pérdida, y qué tienen en común?

## Hallazgos principales

- El fin de semana (viernes-sábado) concentra la mayor utilidad promedio por día; lunes y martes son consistentemente los más bajos.
- La participación de **Transferencia** en el ingreso creció de 7.6% (enero) a 20.4% (diciembre), mientras **Tarjeta** cayó de 39.4% a 25.4% — una migración medible en el método de cobro, con implicación directa en comisiones bancarias.
- El sistema de notas manuales del negocio no capturaba los días de pérdida real: los 25 días con utilidad negativa no tenían ninguna nota de alerta, mientras que las notas existentes marcaban días de utilidad inusualmente *alta* (para verificación, no por pérdida).
- Se identificaron 5 problemas de calidad de datos en la primera versión del archivo; tras la corrección del usuario quedan 2 (fecha inválida `29/02/2025` y una fila duplicada), manejados automáticamente por el script de consolidación y documentados de forma transparente en el notebook.

## Stack técnico

- **Python** — Pandas para consolidación, limpieza y agregación de 12 hojas mensuales de Excel
- **Matplotlib / Seaborn** — visualización
- **Jupyter Notebook** — desarrollo y documentación del análisis
- **Power BI** — dashboard interactivo (próxima fase del proyecto)

## Estructura del repositorio

```
├── Analisis_Financiero_PizzasyPastas.ipynb   # Notebook principal con el análisis completo
├── consolidate.py                             # Script de consolidación y limpieza de las 12 hojas
├── cuentas_2025_consolidado.csv               # Dataset limpio y consolidado (365 días)
├── data_quality_issues.json                   # Registro documentado de problemas de datos encontrados
├── charts/                                     # Gráficos exportados en PNG
├── requirements.txt
└── README.md
```

## Cómo ejecutarlo

```bash
pip install -r requirements.txt
python consolidate.py               # regenera el CSV limpio desde el Excel original
jupyter notebook Analisis_Financiero_PizzasyPastas.ipynb
```

## Nota sobre los datos

El archivo Excel original (registro contable del restaurante) no se publica en este repositorio por ser información financiera del negocio; el dataset consolidado (`cuentas_2025_consolidado.csv`) sí se incluye como evidencia del proceso de limpieza.

---

**Autor:** Nicolás González Peláez — Ingeniero Informático (UMNG) | Data Analyst en formación
[LinkedIn](https://linkedin.com/in/nicolas-gonzalez-pelaez) · ngonzalezpelaez@gmail.com
