# Proyecto-T-nicas-de-Investigaci-n
Proyecto en grupo

# Análisis de Temperaturas Extremas: Comparativa Histórica (1948 vs 2018)

##1. Introducción
Este proyecto desarrolla un análisis estadístico reproducible utilizando el lenguaje R y el entorno RStudio, integrando el control de versiones mediante GitHub. El objetivo central es evaluar cambios en los patrones de temperatura a lo largo de un periodo de 70 años, aplicando buenas prácticas de organización de proyectos científicos y colaboración en parejas.

## 2. Pregunta de Investigación
¿Existe una diferencia estadísticamente significativa en el número de días con temperaturas superiores a los 70 °F en las estaciones meteorológicas seleccionadas entre los años 1948 y 2018?

# Hipótesis
#Hipótesis nula (H0): No hay diferencia en el promedio de días calurosos entre 1948 y 2018 
#Hipótesis alternativa (H1): Existe una diferencia significativa en el promedio de días calurosos entre 1948 y 2018

## 3. Datos
La base de datos utilizada es climate70, obtenida del repositorio de datos de OpenIntro.

# Descripción de la base
Los datos provienen de una muestra aleatoria de estaciones de monitoreo de la NOAA (National Oceanic and Atmospheric Administration) que cuentan con registros completos para los dos años de interés.

#Detalles del Dataset
#Observaciones: 197 observaciones (estaciones meteorológicas).
#Variables
#### station: Identificador de la estación de monitoreo.
#### latitude / longitude: Ubicación geográfica.
#### dx70_1948 / dx70_2018: Días con temperatura máxima > 70°F en cada año respectivo.
#### dx90_1948 / dx90_2018: Días con temperatura máxima > 90°F en cada año respectivo.

### Nota: Dado que los datos comparan la misma unidad experimental (la misma estación) en dos momentos distintos, los datos se consideran dependientes, lo que justifica el uso de una Prueba t para muestras pareadas.
