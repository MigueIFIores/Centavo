# Análisis de Población y Conversión de Monedas de Países a MXN

**Autor:** Miguel Ángel Flores Álvarez  
**Correo:** floresalvarezmiguelangel1@gmail.com

## Descripción
Este proyecto permite obtener información de países usando APIs públicas (World Bank y BDC) y convertir valores monetarios a pesos mexicanos (MXN). 
Incluye:
- Población de los países.
- Moneda oficial de cada país.
- Región geográfica de cada país.
- Conversión de población monetaria a MXN considerando 1 centavo por persona y tasas de cambio actuales.

## Objetivo
Demostrar habilidades de Data Engineering y análisis de datos mediante:
- Consumo de APIs REST y manejo de JSON.
- Limpieza y transformación de datos.
- Uso de pandas para creación y manipulación de DataFrames.
- Conversión de monedas a MXN con respaldo de distintas fuentes.
- Documentación, reproducibilidad y buenas prácticas de programación en Python.

## Contenido del proyecto
- `el_centavo.ipynb`: Notebook principal con el código completo.
- `requirements.txt`: Dependencias necesarias para ejecutar el proyecto.
- `README.md`: Documentación del proyecto.

## Uso
1. Ejecutar el notebook directamente en Jupyter o Jupyter Lab.

2. Inicializar la clase Indicadores:
   ind = Indicadores()

3. Obtener los 30 países más poblados en 2021:
   df_top = ind.poblacion(top=30, fecha=2021)

4. Inicializar la clase CambioMXN para convertir los valores a pesos mexicanos:
   conv = CambioMXN()
   df_mxn = conv.conversion(df_top)

5. Visualizar los resultados:
   print(df_mxn)

El DataFrame resultante incluye las columnas:
- `Pais`: Nombre del país
- `ISO3`: Código ISO3 del país
- `Poblacion`: Población del país
- `Moneda`: Moneda oficial del país
- `Tipo_cambio`: Tasa de cambio respecto a MXN
- `MXN_total`: Población multiplicada por 1 centavo convertido a MXN
