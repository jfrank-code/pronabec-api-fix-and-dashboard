# Dashboard de Becarios - PRONABEC

Este proyecto presenta una solución integral de análisis de datos desarrollada principalmente en Microsoft Excel, complementada con un diagnóstico técnico en Python para la optimización y corrección del proceso de extracción de datos.

## 🔍 Diagnóstico Técnico e Ingeniería Inversa (Python)

Durante el planteamiento inicial, se identificó que el endpoint oficial de la API pública provisto en la documentación del portal de Datos Abiertos de PRONABEC generaba errores críticos de conexión (Error DNS/getaddrinfo) al intentar consumirse desde herramientas externas como Excel.

![Error de la API Oficial](img/api_error.png)

Para diagnosticar la falla, se utilizó un script en Python que analizó el código fuente de la página web. Este análisis demostró que el dominio de la API oficial se encuentra inoperable y que el portal renderiza sus tablas internamente mediante el plugin `jqGrid`. A través de este diagnóstico, se aislaron las direcciones URL de los controladores internos reales del backend, proporcionando la ruta de acceso definitiva a las bases de datos.

## 🛠️ Extracción, Procesamiento y Modelado de Datos (Power Query)

Una vez identificadas las rutas correctas del servidor, todo el flujo de datos se trasladó a **Microsoft Excel**:

1. **Conexión y Extracción:** Se utilizó el motor de **Power Query** para conectarse directamente a los endpoints ocultos del servidor, logrando importar de forma limpia la totalidad de los registros (incluyendo el dataset masivo de **87,576 filas** de becarios por país de estudio).
2. **Transformación (ETL):** Se realizaron tareas de limpieza, tipado de datos y filtrado estructurado dentro del editor de Power Query para estandarizar las columnas de texto y fechas.

## 📊 Arquitectura del Dashboard (Excel)

El cuadro de mando interactivo se construyó utilizando herramientas analíticas avanzadas de Excel para consolidar las métricas clave del programa de becas:

* **Estructura Dinámica:** Implementación de tablas dinámicas combinadas con funciones lógicas y de búsqueda.
* **Segmentación:** Integración de segmentadores de datos interconectados para permitir filtros multidimensionales por género, modalidad de beca e institución.
* **Componente Geográfico:** Incorporación de un gráfico de mapa optimizado y adaptado visualmente para mantener su estética de fondo oscuro y rendimiento tanto en la aplicación local como en su despliegue en la nube a través de Excel para la Web.

![Dashboard Final de Excel](img/dashboard_final.png)
