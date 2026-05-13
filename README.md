# Proyecto-Ténicas-de-Investigación
Proyecto en grupo

# Análisis de Temperaturas Extremas: Comparativa Histórica (1948 vs 2018)

## 1. Introducción
Este proyecto analiza la evolución de los días cálidos y extremadamente cálidos utilizando datos de múltiples estaciones meteorológicas. Se comparan dos periodos específicos: el año 1948 y el año 2018, con el objetivo de identificar cambios en la frecuencia de temperaturas altas. Se aplican métodos estadísticos y gráficos que permiten evaluar diferencias significativas y visualizar patrones en los datos.

## 2. Pregunta de Investigación
¿Existe una diferencia estadísticamente significativa en el número de días con temperaturas superiores a los 70 °F y 90°F  en las estaciones meteorológicas seleccionadas entre los años 1948 y 2018?

### Hipótesis Estadística
* Hipótesis Nula ($H_0$): No hay diferencia en el promedio de días calurosos entre 1948 y 2018 
* Hipótesis Alternativa ($H_1$): Existe una diferencia significativa en el promedio de días calurosos entre 1948 y 2018

## 3. Datos
La base de datos utilizada es climate70, obtenida del repositorio de datos de OpenIntro.

# Descripción de la base
Los datos provienen de una muestra aleatoria de estaciones de monitoreo de la NOAA (National Oceanic and Atmospheric Administration) que cuentan con registros completos para los dos años de interés.

## Detalles del Dataset
#### Observaciones: 197 observaciones (estaciones meteorológicas).
# Variables
#### station: Identificador de la estación de monitoreo.
#### latitude / longitude: Ubicación geográfica.
#### dx70_1948 / dx70_2018: Días con temperatura máxima > 70°F en cada año respectivo.
#### dx90_1948 / dx90_2018: Días con temperatura máxima > 90°F en cada año respectivo.

###### Nota: Dado que los datos comparan la misma unidad experimental (la misma estación) en dos momentos distintos, los datos se consideran dependientes, lo que justifica el uso de una Prueba t para muestras pareadas.

## 4. Metodología

### Variables Utilizadas
Para este análisis se seleccionaron las variables de temperatura máxima agrupadas por umbrales:
* **Dependientes:** `dx70` (días > 70°F) y `dx90` (días > 90°F).
* **Independiente (Factor):** Año de registro (`1948` vs. `2018`).
* **Unidad de control:** `station` (ID de la estación meteorológica).

### Explicación de la Prueba t Utilizada
Se aplicó una **Prueba t de Student para muestras pareadas**. Este método es el adecuado cuando las observaciones de ambos grupos están vinculadas entre sí (en este caso, pertenecen a la misma ubicación geográfica). La prueba evalúa si la media de las diferencias individuales entre 2018 y 1948 es significativamente distinta de cero.

  
## 5. Resultados e Interpretación

### Tablas de Resumen
| Periodo | Media dx70 | Media dx90 |
| :--- | :--- | :--- |
| **1948** | 157.69 | 32.34 |
| **2018** | 161.77 | 35.24 |

### Gráficos
Se generaron gráficos de **Violín** y **Boxplots** para comparar las distribuciones. En ambos umbrales (70°F y 90°F), se observa un desplazamiento ascendente de la media en 2018 respecto a 1948.


### Interpretación de Resultados
Tras ejecutar el análisis en R, se obtuvieron los siguientes valores de significancia:
* **Umbral 70°F:** p-valor = **0.0411**
* **Umbral 90°F:** p-valor = **0.0187**

**Conclusión:** Dado que en ambos casos el **p-valor < 0.05**, se rechaza la hipótesis nula. Existe evidencia estadística suficiente para afirmar que el número de días calurosos aumentó significativamente en estas estaciones entre 1948 y 2018.

## 6. Reproducibilidad
Para correr este proyecto en RStudio:

1. **Descargar** el archivo `climate70.csv` y el script de R en la misma carpeta.
2. **Abrir** RStudio y establecer el directorio de trabajo: `Session > Set Working Directory > To Source File Location`.
3. **Instalar** la librería necesaria ejecutando: `install.packages("tidyverse")`.
4. **Ejecutar** el script completo para generar los resultados y gráficos automáticamente.

