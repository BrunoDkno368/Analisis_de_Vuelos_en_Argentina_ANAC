# Análisis de Vuelos en Argentina (ANAC)
📊 Proyecto de Análisis de Datos — ETL, EDA y Visualización

Este proyecto realiza un análisis exploratorio de datos (EDA) sobre los aterrizajes y despegues procesados por la Administración Nacional de Aviación Civil (ANAC).
El objetivo es comprender el comportamiento del tráfico aéreo argentino, detectar patrones y obtener información útil sobre los vuelos registrados.

📁 Fuente de Datos
--------
Dataset oficial: Ministerio de Transporte de la Nación - ANAC

Archivo utilizado: https://datos.transporte.gob.ar/dataset/aterrizajes-y-despegues-procesados-por-la-administracion-nacional-de-aviacion-civil-anac/archivo/0706775f-bed9-46e7-aac5-726d7e72e429

Frecuencia de actualización: Mensual

Campos principales:
----
------------------------------------------------------------
:heavy_check_mark:  Fecha y hora del vuelo (datetime_local)

:heavy_check_mark:  Aerolínea (aerolinea_nombre)

:heavy_check_mark:  Tipo de movimiento (aterrizaje o despegue)

:heavy_check_mark:  Aeropuerto (aeropuerto)

:heavy_check_mark:  Cantidad de pasajeros (pasajeros)

:heavy_check_mark:  Tipo de vuelo (Regular, No Regular, Carga, etc.)

⚙️ Proceso ETL
--------
--------------------------------------------
1. Extracción:
--------------------------------------------
Descarga del dataset desde el portal de datos abiertos del Ministerio de Transporte.

Carga inicial en formato .csv con control de delimitadores y codificación UTF-8.

--------------------------------------------
2. Transformación:
---------------------------------------------
Conversión de campos de fecha a formato datetime.

Creación de nuevas variables:

fecha, hora, dia_semana (en español).

Limpieza de datos:
-----------------------------------------------
Reemplazo de valores nulos o “0” en la columna aerolinea_nombre por "SIN_DATOS".

Conversión de campos numéricos (pasajeros) y tratamiento de outliers.

Normalización de textos y eliminación de espacios o inconsistencias.

3. Carga:
-------------------------------------
Dataset limpio y estructurado para análisis exploratorio con pandas, seaborn y matplotlib.

🔎 Análisis Exploratorio (EDA)
-----

-----------------------------------------
📅 Distribución temporal

------------------------------------------------------
Se generaron columnas derivadas para analizar patrones por hora, día y mes.

Los días se mostraron en español (Lunes a Domingo) para mejor interpretación visual.


------------------------------------------------
✈️ Tipo de movimiento

---------------------------------------------
Se observó una distribución equilibrada entre aterrizajes y despegues, como es esperable en operaciones aéreas regulares.

Sin embargo, existen diferencias menores debido a vuelos técnicos o de posicionamiento.


----------------------------------
🧍‍♂️ Distribución de pasajeros

----------------------------------
El histograma muestra una alta concentración en 0 pasajeros (~6.000 vuelos).

Posibles causas:

Vuelos técnicos o de mantenimiento.

Operaciones de carga.

Registros con datos faltantes.

Al excluir estos casos, se observa que la mayoría de los vuelos transportan entre 50 y 150 pasajeros, consistente con aeronaves comerciales medianas.


-----------------------------------------
🕓 Distribución por día y hora

------------------------------------------
Mapa de calor (heatmap) muestra picos de actividad:

Mayor cantidad de operaciones entre 7:00 y 22:00 hs.

Días con más tráfico: Lunes a Viernes (actividad comercial).

Menor movimiento durante fines de semana.


---------------------------------------
📊 Visualizaciones incluidas

--------------------------------------------------
Histograma de pasajeros (sns.histplot)

Con curva KDE para visualizar la densidad.

Mapa de calor día vs hora

Días de la semana en español, mostrando intensidad operativa.

------------------------------------------------
Gráficos de barras

---------------------------------------------
Frecuencia de movimientos por tipo y por aerolínea.

Top aerolíneas y aeropuertos

Ranking de mayor cantidad de vuelos.

🧾 Conclusiones
--------------------
✈️ Equilibrio operacional: El volumen de aterrizajes y despegues es coherente, validando la integridad del dataset.

🧍‍♀️ Valores nulos o atípicos: La presencia de ~6.000 vuelos con “0 pasajeros” requiere revisión — probablemente vuelos técnicos o de carga.

🗓️ Patrones temporales: La actividad se concentra en días hábiles y en horarios diurnos, indicando uso comercial y regular.

🏆 Aeropuertos principales: Los más activos corresponden a grandes hubs (Ezeiza, Aeroparque, Córdoba, Mendoza).

📈 Distribución de pasajeros: La mayoría de los vuelos comerciales transportan entre 50 y 150 pasajeros, con distribución unimodal.

🧰 Herramientas utilizadas
Categoría	Librerías
Procesamiento de datos	pandas, numpy
Visualización	matplotlib, seaborn
Limpieza y formateo	datetime, locale, re
Entorno	Jupyter Notebook / Google Colab
📚 Aprendizajes y recomendaciones

El análisis de vuelos requiere diferenciar vuelos comerciales, técnicos y de carga para evitar sesgos.

Es recomendable que los registros con “0 pasajeros” sean tratados como categoría aparte, no como valor numérico.

Incluir información adicional (tipo de aeronave, ruta, duración) permitiría construir un modelo predictivo de ocupación.

📎 Autor

👨‍💻 Bruno Roberto Argañaraz
📍 Analista de Datos | Power BI | Python | SQL
📧 Contacto profesional bruno.r.arganaraz@gmail.com / https://www.linkedin.com/in/bruno-argañaraz-726a4a199/

🔗 GitHub
