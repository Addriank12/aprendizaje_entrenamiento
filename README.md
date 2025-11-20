# Análisis y Predicción de Ventas

Proyecto completo de análisis exploratorio de datos (EDA) y predicción de ventas utilizando técnicas de Machine Learning y Deep Learning.

## 📋 Descripción del Proyecto

Este proyecto realiza un análisis exhaustivo de datos de ventas y desarrolla modelos predictivos para forecasting de demanda. El proyecto consta de dos componentes principales:

1. **Análisis Exploratorio de Datos (EDA)** - `analisis.ipynb`
2. **Predicción de Ventas** - `StockPred.ipynb`

## 📊 Dataset

- **Archivo:** `practica_completo.csv`
- **Período analizado:** Último año de datos (365 días desde la fecha más reciente)
- **Características principales:**
  - Datos de ventas por producto
  - Información temporal (fechas, días de la semana, meses)
  - Precios unitarios y stock disponible
  - Identificación de feriados ecuatorianos
  - Antigüedad de productos en catálogo

## 🔍 Análisis Exploratorio de Datos

### Componentes del Análisis (`analisis.ipynb`)

#### 1. Carga y Exploración Inicial
- Optimización de memoria mediante tipos de datos eficientes
- Filtrado de datos del último año
- Creación de variables temporales y especiales:
  - `dia_semana`, `mes`, `fin_semana`
  - `feriado` (feriados ecuatorianos 2024)
  - `antiguedad_producto` (días desde primera venta)
  - `ratio_vendida_stock` (rotación de inventario)

#### 2. Análisis de Fines de Semana y Feriados
- Comparación de ventas: días laborables vs fin de semana vs feriados
- Distribución de ventas por tipo de día (boxplots)
- Análisis de productos más antiguos
- Relación antigüedad vs ventas totales
- Cálculo de impacto porcentual de feriados

#### 3. Análisis Temporal de Ventas
- Evolución de ventas diarias con medias móviles (7 y 30 días)
- Diversidad de productos vendidos por día
- Patrones semanales con diferenciación de fines de semana
- Tendencias mensuales y estacionalidad
- Top 5 y Bottom 5 meses de ventas

#### 4. Análisis de Productos
- Top 15 productos más vendidos
- Curva de Pareto (regla 80/20)
  - Identificación de productos que generan 50% y 80% de ventas
- Análisis de ventas vs frecuencia de compra
- Distribución de ventas por producto con mediana y promedio
- Análisis de precios y stock

#### 5. Análisis de Distribuciones y Outliers
- Identificación de outliers mediante:
  - Método IQR (Rango Intercuartílico)
  - Z-score (> 3 desviaciones estándar)
- Visualizaciones: histogramas, boxplots, Q-Q plots
- Distribución acumulada (CDF)
- Violin plots por día de la semana

#### 6. Análisis de Correlaciones
- Matriz de correlación entre variables numéricas
- Heatmap de correlaciones
- Correlaciones con la variable objetivo (ventas)

#### 7. Resumen Ejecutivo
- Métricas generales del negocio
- Patrones temporales identificados
- Insights de productos
- Detección de outliers y anomalías
- Recomendaciones accionables

## 🤖 Predicción de Ventas

### Componentes del Modelo (`StockPred.ipynb`)

El notebook de predicción incluye modelos de Machine Learning y Deep Learning con seguimiento de experimentos usando MLflow.

### Visualizaciones Generadas

El proyecto genera las siguientes visualizaciones de análisis del modelo:

- `training_history.png` - Historial de entrenamiento
- `prediction_analysis.png` - Análisis de predicciones
- `residual_analysis.png` - Análisis de residuos
- `outlier_analysis.png` - Análisis de outliers
- `ensemble_analysis.png` - Análisis de ensemble

## 🛠️ Tecnologías Utilizadas

### Python Libraries
- **Análisis de Datos:** pandas, numpy
- **Visualización:** matplotlib, seaborn
- **Machine Learning:** scikit-learn, scipy
- **Deep Learning:** TensorFlow/Keras
- **Tracking:** MLflow

### Entorno
- **Python:** 3.12
- **Entorno Virtual:** tf-env
- **Kernel Jupyter:** Python (tf-env)

## 📁 Estructura del Proyecto

```
aprendizaje/
├── README.md                    # Este archivo
├── analisis.ipynb              # Análisis exploratorio de datos
├── StockPred.ipynb             # Modelos de predicción
├── practica_completo.csv       # Dataset principal
├── mlruns/                     # Experimentos MLflow
├── ensemble_analysis.png       # Visualización ensemble
├── outlier_analysis.png        # Visualización outliers
├── prediction_analysis.png     # Visualización predicciones
├── residual_analysis.png       # Visualización residuos
└── training_history.png        # Visualización entrenamiento
```

## 🚀 Instalación y Uso

### 1. Configurar el Entorno Virtual

```bash
# Activar entorno virtual
source ~/tf-env/bin/activate

# Instalar dependencias (si es necesario)
pip install pandas numpy matplotlib seaborn scikit-learn scipy tensorflow mlflow ipykernel

# Registrar kernel para Jupyter
python -m ipykernel install --user --name=tf-env --display-name="Python (tf-env)"
```

### 2. Ejecutar los Notebooks

```bash
# Abrir Jupyter Notebook o VS Code
# Seleccionar kernel "Python (tf-env)"
# Ejecutar las celdas en orden
```

### 3. Análisis Exploratorio

1. Abrir `analisis.ipynb`
2. Ejecutar todas las celdas secuencialmente
3. Revisar los gráficos y estadísticas generadas

### 4. Predicción de Ventas

1. Abrir `StockPred.ipynb`
2. Ejecutar el notebook completo
3. Revisar las métricas de MLflow
4. Analizar las visualizaciones generadas

## 📈 Principales Hallazgos

### Patrones Temporales
- Variabilidad significativa en ventas por día de la semana
- Tendencias estacionales mensuales y trimestrales identificadas
- Impacto medible de feriados en el comportamiento de ventas

### Concentración de Productos
- Principio de Pareto confirmado (~20% productos → ~80% ventas)
- Alta concentración de demanda en productos específicos
- Oportunidades de optimización de inventario identificadas

### Outliers y Anomalías
- Presencia significativa de valores atípicos
- Necesidad de análisis específico para casos extremos
- Importante para robustez del modelo predictivo

### Correlaciones
- Relaciones identificadas entre variables temporales y ventas
- Comportamiento no lineal entre precio, stock y demanda

## 💡 Recomendaciones

1. **Gestión de Inventario:**
   - Enfocar inventario en productos que generan 80% de ventas
   - Implementar reabastecimiento basado en patrones temporales

2. **Estrategia de Ventas:**
   - Preparar stock adicional para días pico identificados
   - Considerar promociones en días/períodos de bajas ventas
   - Aprovechar impacto de feriados

3. **Optimización:**
   - Investigar y validar outliers extremos
   - Implementar sistema de predicción automático
   - Monitorear antigüedad de productos en catálogo

4. **Próximos Pasos:**
   - Implementar modelos de predicción en producción
   - Desarrollar dashboard interactivo
   - Análisis detallado por categoría de producto
   - Detección automática de anomalías en tiempo real

## 📝 Notas Técnicas

- **Optimización de Memoria:** Los datos se cargan con tipos optimizados (int32, float32)
- **Feriados:** Lista configurable de feriados ecuatorianos 2024
- **Filtrado Temporal:** Análisis enfocado en último año para mayor relevancia
- **Visualizaciones:** Optimizadas para claridad y accionabilidad

## 🔄 Seguimiento de Experimentos

El proyecto utiliza MLflow para tracking de experimentos. Los resultados se almacenan en:
```
mlruns/
├── 0/                          # Experimento default
└── 120979648417389380/         # Experimentos numerados
```

## 📧 Contacto

Para preguntas o sugerencias sobre este proyecto, contactar al equipo de análisis.

---

**Última actualización:** Noviembre 2025