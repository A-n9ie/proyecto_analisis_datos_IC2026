
# Análisis de la Participación Femenina en los Juegos Olímpicos (1896-2022)

## 📌 Descripción

Análisis exploratorio de datos sobre la evolución de la participación femenina en los Juegos Olímpicos desde 1896 hasta 2022. Utilizando técnicas de análisis de datos e interpretación visual, el proyecto identifica patrones históricos de inclusión, tendencias por disciplina y comparativas de desempeño entre géneros.


## 🎯 Objetivo

Analizar la evolución de la participación femenina en los Juegos Olímpicos, identificando patrones de inclusión por disciplina, país y período temporal, así como la relación entre participación y desempeño competitivo.


## 📊 Funciones Implementadas

| # | Función | Descripción | Estado |
|---|---------|-------------|--------|
| 1 | `renombrar_columnas_principales()` | Renombra columnas clave al español (año, sexo, tipo, etc.) | ✅ |
| 2 | `preparar_df_unido()` | Merge de bios y results, limpieza de sexo y años | ✅ |
| 3 | `renombrar_columnas()` | Renombra columnas de resultados agregados (medallas, tasas) | ✅ |
| 4 | `proporcion_femenina_por_anio()` | Calcula % de participación femenina por año | ✅ |
| 5 | `proporcion_femenina_por_anio_y_tipo()` | % por año y tipo (Verano/Invierno) | ✅ |
| 6 | `top_5_paises_participaciones_femeninas()` | Top 5 países por número de participaciones femeninas | ✅ |
| 7 | `participaciones_femeninas_top_disciplinas_evolucion()` | Evolución temporal de las top disciplinas femeninas | ✅ |
| 8 | `comparativa_genero_por_anio()` | Comparación de participaciones masculinas vs femeninas por año | ✅ |
| 9 | `conteo_medallas_por_sexo()` | Distribución de medallas (oro, plata, bronce) por sexo | ✅ |
| 10 | `primer_participacion_femenina_por_disciplina()` | Primer año de inclusión femenina por disciplina + métricas | ✅ |
| 11 | `visualizar_primer_participacion_femenina()` | Visualización del primer año (barras horizontales con color degradado) | ✅ |
| 12 | `participacion_femenina_top5_paises()` | Área apilada de participaciones femeninas en top 5 países | ✅ |
| 13 | `top10_paises_medallas_oro_femeninas()` | Top 10 países con más medallas de oro femeninas | ✅ |
| 14 | `evolucion_disciplinas_con_mujeres()` | Evolución del número de disciplinas con participación femenina | ✅ |


## 🚀 Uso Rápido

### En Jupyter Notebook

```python
from funciones.preparacion_datos import cargar_datos
from funciones.eficiencia_medallas import medal_efficiency_by_gender, visualize_medal_efficiency
from funciones.participacion_historica import first_female_participation_by_discipline, visualize_first_female_participation

# Cargar datos
df = cargar_datos('datos/bios.csv', 'datos/results.csv')

# Análisis 1: Eficiencia de medallas
efficiency = medal_efficiency_by_gender(df)
visualize_medal_efficiency(df, guardar=True, ruta_salida='resultados/eficiencia.png')

# Análisis 2: Participación histórica
first_female = first_female_participation_by_discipline(df)
visualize_first_female_participation(df, top_n=20, guardar=True)
```

### En Google Colab

```python
!git clone https://github.com/A-n9ie/proyecto_analisis_datos_IC2026.git
%cd proyecto_analisis_datos_IC2026
!pip install -r requirements.txt

# Ejecutar análisis completo
exec(open('notebooks/02_analisis_completo.ipynb').read())
```


## 📈 Hallazgos Principales

- **1900:** 2.2% participación femenina
- **1976 (Montreal):** 21%
- **1996 (Atlanta):** 34%
- **2008 (Beijing):** 42%
- **2022:** ~49% (aproximadamente paritario)

**Disciplinas más antiguas con participación femenina:** Tennis (1900)  
**Disciplinas más recientes:** Badminton (1992)



## 📋 Requisitos

```
pandas==2.0.0
numpy==1.24.0
matplotlib==3.7.0
seaborn==0.12.0
scikit-learn==1.2.0
plotly==5.12.0
```

## 📝 Datasets

### bios.csv
- **135,000+** registros de atletas
- Columnas: `athlete_id`, `Sex`, `Full name`, `Nationality`, `Born`, `Measurements`

### results.csv
- **270,000+** participaciones en competencias
- Columnas: `year`, `type`, `discipline`, `event`, `athlete_id`, `medal`, `noc`


## 🔄 Sincronización GitHub-Colab

Para guardar cambios desde Colab a GitHub:

1. En Colab: **File → Save a copy in GitHub**
2. Selecciona rama **master**
3. **Nota:** No hay sincronización automática
