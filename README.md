## Sistema de Gestión de Base de Datos – Portafolio de Inversiones (MVP)

# Descripción
Este proyecto implementa un modelo relacional para la gestión de portafolios de inversión utilizando MySQL ejecutado mediante Docker.
El sistema es completamente reproducible en local sin dependencias externas.
________________________________________
# Requisitos
•	Docker
________________________________________
# Estructura del proyecto (Carpeta SQL_Portafolios)
•	docker-compose.yml
•	01_schema.sql
•	02_data_load.sql
•	03_queries.sql
•	README.md
________________________________________
# Ejecución
Desde la carpeta del proyecto ejecutar (SQL_Portafolios):

docker-compose down -v

docker-compose up -d

# El contenedor creado es:
inversiones_mysql

# La base de datos creada es:
DB_opt_portafolios

# Puerto expuesto:
3307
________________________________________
# Conexión desde terminal
docker exec -it inversiones_mysql mysql -uroot -p200199Ra.
Luego:
	USE DB_opt_portafolios;
	SHOW TABLES;
________________________________________
# Ejecución de consultas representativas
docker exec -i inversiones_mysql mysql -uroot -p200199Ra. DB_opt_portafolios < 03_queries.sql
________________________________________
# Validación
El sistema se considera reproducible si:

•	El contenedor se levanta sin errores.

•	Las tablas se crean automáticamente.

•	Los datos se cargan correctamente.

•	Las consultas devuelven resultados coherentes.



________________________________________

README: Motor Analítico y Optimización de Portafolios (TFM)


Descripción General (Qué muestra el código)

El presente cuaderno de Jupyter contiene el motor analítico central desarrollado para la evaluación y optimización de carteras de inversión. El código integra la Teoría Moderna de Carteras (MPT) con técnicas de Machine Learning (Random Forest Regressor y agrupamiento K-Means). Su propósito principal es procesar cotizaciones históricas, calcular la asignación óptima de capital para maximizar el Ratio de Sharpe, auditar el riesgo sistémico (Beta) y estructurar los resultados para su posterior ingesta en herramientas de Business Intelligence (Tableau).

Instrucciones de Uso (Cómo utilizar la herramienta)
Para garantizar la correcta ejecución del entorno analítico, se deben seguir los siguientes pasos:

Preparación del Entorno: Abrir el archivo .ipynb en Google Colab o en un entorno local compatible con Jupyter Notebook.

Instalación de Dependencias: Ejecutar el primer bloque de código para asegurar la instalación e importación de las librerías fundamentales (yfinance, pandas, numpy, scipy.optimize, scikit-learn e ipywidgets).

Carga de Datos Base: Asegurar que el archivo de metadatos (Metricas_Individuales_Fase_2.csv) o las variables de entorno estén disponibles en el directorio de trabajo para poblar el menú de selección.

Ejecución Interactiva: Correr la celda correspondiente al "Portal de Análisis Integral". Se desplegará una interfaz visual de usuario.

Operativa: Seleccionar un mínimo de dos activos financieros de la lista (utilizando Ctrl/Cmd para selección múltiple), asignar un nombre personalizado a la cartera y hacer clic en el botón verde "Ejecutar Análisis Total".

Resultados y Entregables (Qué esperar tras la ejecución)
Al procesar la solicitud, el sistema automatiza la extracción de datos en tiempo real (Live Fetching) y genera los siguientes resultados de forma inmediata:

Auditoría Cuantitativa: Un reporte impreso en consola que detalla el Retorno Esperado, la Volatilidad, el Ratio de Sharpe maximizado, el coeficiente Beta (riesgo de mercado) y la precisión algorítmica de la IA (R² y MSE).

Dashboard Visual Integrado: La renderización automática de un lienzo analítico con cuatro vistas clave:

Segmentación de perfiles de riesgo mediante clústeres K-Means.

Matriz de correlación térmica entre los activos seleccionados.

Composición óptima del portafolio (pesos asignados por el algoritmo SLSQP).

Gráfico de la Frontera Eficiente trazada a través de 3,000 simulaciones de Monte Carlo.

Preparación para BI: Consolidación de los hallazgos en estructuras de datos tabulares (DataFrames) y archivos CSV estandarizados, diseñados específicamente para integrarse de forma fluida con los cuadros de mando finales en Tableau.


________________________________________



