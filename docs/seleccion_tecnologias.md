# Selección de Tecnologías NoSQL para el E-commerce

## Resumen
Para el desarrollo del e-commerce sin pasarela de pagos, se propone una arquitectura basada en tres tecnologías NoSQL complementarias.
Cada una cumple un rol específico para cubrir necesidades de almacenamiento, velocidad y búsqueda avanzada.

---

## 1. MongoDB – Base principal (Modelo de documentos)
**Rol:** Almacenar la información principal del sistema.

**Uso en el proyecto:**
- Productos y sus atributos (precio, descripción, imágenes, stock).
- Categorías de productos.
- Pedidos realizados por los usuarios.
- Reseñas y valoraciones.

**Ventajas:**
- Esquema flexible, ideal para productos con atributos variables según la categoría.
- Documentos en formato JSON fáciles de manejar en el desarrollo.
- Buen soporte para consultas complejas y filtrado.
- Escalabilidad horizontal.

---

## 2. Redis – Capa de rendimiento (Modelo clave-valor en memoria)
**Rol:** Manejar datos temporales y operaciones rápidas.

**Uso en el proyecto:**
- Almacenamiento temporal de carritos de compra.
- Gestión de sesiones de usuario (aunque en este proyecto no hay registro, podría usarse para identificar visitantes).
- Cacheo de resultados frecuentes para mejorar tiempos de respuesta.

**Ventajas:**
- Extremadamente rápido para lecturas y escrituras.
- Reduce la carga sobre MongoDB en operaciones de alta frecuencia.
- Perfecto para datos que no necesitan persistir permanentemente.

---

## 3. Elasticsearch – Motor de búsqueda y análisis
**Rol:** Proporcionar búsquedas rápidas y relevantes.

**Uso en el proyecto:**
- Búsqueda de productos por nombre, descripción o palabras clave.
- Filtrado por precio, categoría o marca.
- Ordenamiento por relevancia o popularidad.

**Ventajas:**
- Diseñado para búsquedas a gran escala con tiempos de respuesta mínimos.
- Soporte de búsquedas parciales y tolerancia a errores ortográficos.
- Fácil integración con MongoDB mediante sincronización de datos.
