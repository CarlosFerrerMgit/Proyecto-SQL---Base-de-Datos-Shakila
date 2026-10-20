# 🎬 Proyecto SQL: Análisis y Lógica Relacional sobre Shakila Database

> **Módulo 4: Lógica y Consultas SQL**  
> **PostgreSQL (Gestión y entorno en DBeaver)**  
> **Fecha: Octubre 2026** 

## 📌 1. Descripción del Proyecto

Este repositorio contiene la resolución estructurada y optimizada de las 64 consultas analíticas planteadas sobre la base de datos relacional Shakila. El objetivo central del proyecto es demostrar el dominio técnico del lenguaje SQL bajo el gestor PostgreSQL, abarcando desde consultas elementales hasta modelados avanzados mediante subconsultas correlacionadas, vistas dinámicas, agregaciones estadísticas y estructuras de datos temporales.

## 🛠️ 2. Metodología, Pasos Seguidos e Informe del Análisis

El despliegue y desarrollo del proyecto se ejecutó íntegramente mediante la herramienta **DBeaver** conectada a una instancia local de **PostgreSQL**

### A. Pasos Seguidos durante el Proyecto
1. **Configuración del Entorno de Trabajo (PostgreSQL y DBeaver):**
   * Creación de la base de datos `shakila` asignando como propietario al superusuario `postgres`.
   * Habilitación del modo multibase de datos (*Show all databases*) en los ajustes de conexión.
   * Creación del esquema lógico `Diagrama_Shakila` y fijación del esquema activo de trabajo (`SET search_path TO public;`).
2. **Carga e Inspección de Datos:**
   * Ejecución íntegra del script oficial `BBDD_Proyecto_shakila_sinuser.sql` con la definición DDL de 15 tablas relacionales y su carga DML de registros.
   * Auditoría del Diagrama Entidad-Relación (ER) generado en DBeaver para trazar las claves primarias (PK), foráneas (FK) y cardinalidades del negocio.
3. **Desarrollo y Testeo de Consultas:**
   * Creación de un editor de pruebas en DBeaver para validar iterativamente cada consulta.
   * Redacción del archivo maestro de entrega `Consultas SQL.txt` en VS Code, documentando cada una de las 64 consultas con su enunciado y comentarios explicativos.
4. **Documentación y Despliegue:**
   * Exportación en alta resolución del esquema relacional (`postgres-Proyecto_Shakila-public.png`).
   * Estructuración del repositorio y redacción del presente `README.md` como memoria técnica.

### B. Competencias Técnicas Demostradas en las Consultas
* **Consultas Monotabla y Filtrado Condicional:**
  * Uso exhaustivo de operadores de comparación (`<`, `>`, `=`) y pertenencia (`BETWEEN`, `IN`, `NOT IN`).
* **Métricas y Dispersión Estadística:**
  * Funciones de agregación (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) combinadas con medidas de variabilidad (`VARIANCE()`, `STDDEV()`) y formateadas con `ROUND()`.
* **Familias de Relaciones (Joins):**
  * `INNER JOIN`: Cruces relacionales precisos entre catálogo y tablas puente (`film_actor`, `film_category`).
  * `LEFT JOIN`: Preservación de tablas maestras para auditar registros con balance cero o identificar elementos huérfanos con `WHERE campo IS NULL` (ej. actores sin filmografía o clientes sin alquileres).
  * `CROSS JOIN`: Análisis del producto cartesiano y su aplicabilidad en matrices teóricas de asignación (`staff` vs. `store`) frente a su invalidez analítica en entidades independientes.
* **Control del Flujo de Agrupación (`WHERE` vs. `HAVING`):**
  * Diferenciación estricta entre el filtrado a nivel de fila individual previo al agrupamiento (`WHERE`) y el filtrado sobre agregados consolidados post-agrupación (`HAVING COUNT(DISTINCT film_id) >= 7`).
* **Subconsultas y Modularidad:**
  * Subconsultas escalares en el `WHERE` para evaluar umbrales dinámicos (duración y precios medios) y subconsultas multivalor para acotar hitos temporales.
* **Estructuras Avanzadas de Datos:**
  * Vistas (`CREATE VIEW actor_num_peliculas`) para encapsular lógicas recurrentes.
  * Tablas temporales (`CREATE TEMPORARY TABLE`) como `cliente_rentas_temporal` y `peliculas_alquiladas` para optimizar consultas en memoria de sesión.

### C. Informe Ejecutivo del Análisis de Negocio
El análisis global de la operativa de Sakila revela los siguientes hallazgos clave:
* **Comportamiento de la Facturación:** El videoclub acumula unos ingresos totales de 67.416,51€ , manteniendo una concentración de gasto donde el top 5 de clientes supera los 180 € por usuario.
* **Estructura del Catálogo:** La duración media se sitúa en 115,27 minutos, oscilando en un rango acotado entre un mínimo de 46 minutos y un máximo de 185 minutos.
* **Preferencias de Consumo:** La categoría *Sports* y *Animation* lideran la demanda de alquileres sobre el inventario, mientras que las categorías más largas (como *Action*) demandan mayor tiempo de retención.
* **Control Operativo y Devoluciones:** El análisis de desvíos temporales identificó que la totalidad de alquileres cerrados con más de 8 días de retención (`return_date - rental_date > INTERVAL '8 days'`) representan posibles candidatos a penalizaciones por recargo tarifario.

## 📁 3. Estructura del Proyecto
```text
├── data/
│   ├── BBDD_Proyecto_shakila_sinuser.sql            # Base de datos para el proyecto
├── docs/
│   ├── Consultas SQL.txt                            # Respuesta a las consulta
│   ├── EnunciadoDataProject_SQL.Lógica.pdf          # Consultas a realizar
│   └── postgres-Proyecto_Shakila-public.png         # Imagen del diagrama
└── README.md                                        # Documentación principal del repositorio
```

## 🗺️ 4. Esquema y Modelo Entidad-Relación (ER)
<img width="764" height="684" alt="image" src="https://github.com/user-attachments/assets/2e5cf91b-3527-44c7-875f-64fe82049399" />


 ## 🤝 Contribuciones

 Las contribuciones, sugerencias y mejoras son bienvenidas. 
 
 ## 👤 Autor
 
 Carlos A. Ferrer Mendoza — Ingeniero Electrónico | MBA y Alumno del Máster en Data & Analytics (ThePower Business School).
 www.linkedin.com/in/carlos-ferrer-mendoza-835294292
