# Despliegue-BaseDeDatos-Railway

# 🚀 Despliegue de Base de Datos PostgreSQL a Railway (Servidor en la Nube)

## Objetivo del Proyecto
El objetivo fue migrar y desplegar la base de datos `blog`, **creada y administrada manualmente en pgAdmin**, a un servidor en la nube utilizando Railway.

---

## 🛠️ Proceso de Migración Detallado

1. **Corrección de la Estructura (CREATE TABLE):**
   * El código SQL inicial para la creación de tablas generó errores de secuencias en Railway (error: `relation "usuarios_id_usuario_seq" does not exist`).
   * Esto se corrigió implementando la sintaxis moderna de PostgreSQL: **`GENERATED ALWAYS AS IDENTITY`**.
   * Todas las tablas fueron creadas con éxito.

2. **Restauración de Datos (Restore):**
   * Los archivos de datos (`.sql`) adjuntos en este repositorio fueron restaurados con éxito al servidor de Railway, confirmado por el mensaje **"Process completed"**.

3. **Prueba de Conexión y Despliegue (Confirmación Final):**
   * **Conexión:** La **`DATABASE_URL`** obtenida de Railway (ver archivo `conexion.py`) demuestra la URL de acceso público al servidor desplegado.
   * **Prueba de Datos:** Se verificó en `pgAdmin` que el servidor **Railway-Cloud Final** contiene todas las filas de datos reales (ej. en la tabla `usuarios`), confirmando la migración completa.

---

## 🔗 Código de Conexión (Prueba de Acceso a la Nube)
* **Archivo de Datos:** Ver carpeta `blog/` con todos los archivos `.sql`.
* **Archivo de Conexión:** Ver **`conexion.py`**. Este archivo simula la configuración que usaría una aplicación para conectarse al servidor desplegado.
