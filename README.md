# Ranking de Precios de Pasajes Aéreos por Aerolínea y Clase

Análisis exploratorio de precios de pasajes aéreos en Python, aplicando el **modelo de visualización de Ben Fry** (Acquire → Parse → Filter → Mine → Represent → Refine → Interact), complementado con un dashboard interactivo en Flourish.

Trabajo práctico de la materia **Visualización de la Información** — ITBA.

**Dataset:** [Airline Ticket Prices Dataset — Kaggle](https://www.kaggle.com/datasets/syedaeman2212/airline-ticket-prices-dataset)

## Dashboard interactivo

🔗 [Ver dashboard en Flourish](https://public.flourish.studio/story/3715814/)

## Pregunta de interés

¿Cómo cambia el ranking de precio de cada aerolínea según la clase del pasaje? ¿Hay aerolíneas consistentemente caras o baratas, o el orden relativo varía entre clases? ¿Cómo influye la distancia promedio del vuelo en ese precio?

## Enfoque técnico

- **Adquisición**: dataset descargado directamente desde Kaggle con `kagglehub`.
- **Limpieza de datos**: eliminación de nulos en variables clave, filtrado de outliers de precio con el método IQR (rango intercuartílico), y ordenamiento categórico de las clases de pasaje (Economy → Premium Economy → Business → First).
- **Análisis**: agregación de precio mediano y distancia promedio por aerolínea y clase mediante tablas pivote.
- **Visualización**: **bump chart** con curvas suavizadas (interpolación smoothstep), tamaño de punto proporcional a la distancia promedio del vuelo, precio mediano anotado en cada punto y paleta de color dinámica por aerolínea.
- **Librerías**: pandas, numpy, matplotlib, seaborn, kagglehub.

## Principales hallazgos

- El ranking de precios entre aerolíneas **no es estático**: una aerolínea económica en clase Economy no necesariamente lo es en Business o First.
- La relación entre distancia de vuelo y precio **no es consistente** — la distancia influye, pero no es el factor determinante del precio.
- Los mayores cambios de ranking se concentran en el salto **Economy → Business**; entre Business y First los rankings se estabilizan.

## Estructura del repositorio

```
ranking_precios_aerolineas.ipynb   → notebook con el análisis y la generación del bump chart
```

## Cómo ejecutar

Abrir `ranking_precios_aerolineas.ipynb` en Jupyter, Google Colab, o VS Code con la extensión de Jupyter, y correr las celdas en orden.

*(Requiere una cuenta de Kaggle configurada para la descarga automática del dataset vía `kagglehub`, o descargar el CSV manualmente desde el link del dataset.)*
