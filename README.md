# Modelado Relacional y Consultas SQL para Inventario Agroquímico

Este repositorio documenta la creación de un modelo de base de datos relacional en SQLite para una empresa ficticia del sector agroquímico. A través de este proyecto se diseñan tablas, se definen relaciones entre ellas y se desarrollan consultas SQL que permiten explorar datos operativos, evaluar niveles de inventario y realizar análisis de ventas.

## Objetivo

Construir una base de datos bien estructurada para representar productos, pedidos, inventarios y clientes en el contexto de una empresa agroquímica, utilizando comandos SQL robustos y consultas de análisis.

## Estructura del proyecto

### 1. Diseño de la base de datos
- Creación de la base `agroquimicos.db`
- Definición de tablas:
  - `Productos`: id, nombre, tipo, unidad, nivel_stock, etc.
  - `Inventario`: id_producto, cantidad_actual, fecha_actualización
  - `Clientes`: id_cliente, nombre, ubicación, tipo
  - `Pedidos`: id_pedido, id_cliente, fecha, estado
  - `DetallePedidos`: id_detalle, id_pedido, id_producto, cantidad

### 2. Consultas implementadas

#### Relaciones entre tablas
- `INNER JOIN`: Productos con sus pedidos activos
- `LEFT JOIN`: Visualización de productos sin pedidos asociados

#### Condicionales
- `CASE WHEN`: Clasificación de productos según nivel de inventario (`Crítico`, `Suficiente`, `Excedente`)

#### Subconsultas
- **Semi-Join**: Productos presentes en al menos un pedido
- **Anti-Join**: Productos que nunca han sido pedidos
- Subconsulta para identificar clientes con más de X pedidos

## Funciones utilizadas

- `GROUP BY`, `HAVING`
- `ROW_NUMBER()`, `SUBSTRING()`, `COALESCE()`
- `SUM()`, `AVG()`, `MAX()`, `MIN()`
- Claúsula `WHERE` con múltiples condiciones

## Tecnologías

- SQLite3  
- Python 3.x  
- pandas (para visualización opcional)  
- DB Browser for SQLite / SQLiteStudio
- Ayuda para generar datos al azar https://www.mockaroo.com

## Conclusiones

- La estructura relacional del modelo permite una exploración detallada y segmentada de los datos.
- El uso de `JOIN`, `CASE`, y subconsultas mejora la capacidad de análisis del inventario y pedidos.
- Este proyecto puede servir como base para sistemas de gestión de inventarios en empresas de distribución.
