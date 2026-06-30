# 📖 Manual de Usuario - AlToke Pro

¡Bienvenido a **AlToke Pro**! Este manual está diseñado para guiarte paso a paso en el uso de la plataforma, desde la configuración inicial hasta el dominio del escáner de inventario. 

AlToke Pro es un sistema profesional de control de inventario y logística (Back-office) diseñado para que tu equipo trabaje rápido, sin errores y sin importar si hay conexión a internet.

---

## Índice
1. [Primeros Pasos y Dashboard](#1-primeros-pasos-y-dashboard)
2. [Gestión de Tiendas y Sucursales](#2-gestión-de-tiendas-y-sucursales)
3. [Clasificación: Categorías y Subcategorías](#3-clasificación-categorías-y-subcategorías)
4. [Catálogo de Productos](#4-catálogo-de-productos)
5. [Auditoría e Inventario (Uso del Escáner)](#5-auditoría-e-inventario-uso-del-escáner)
6. [Modo Offline (Sin Conexión)](#6-modo-offline-sin-conexión)

---

## 1. Primeros Pasos y Dashboard

Al iniciar sesión en AlToke Pro, la primera pantalla que verás es tu **Panel de Control (Dashboard)**.

<div align="center">
  <img src="https://raw.githubusercontent.com/betorockers/AlTokePro/main/screenshot_desktop.png" alt="Dashboard de AlToke Pro" width="100%" style="border-radius: 10px; box-shadow: 0 4px 15px rgba(0,0,0,0.1);" />
</div>

### ¿Qué encuentras aquí?
- **Resumen Financiero y Logístico:** Tarjetas con el valor total de tu inventario, cantidad de productos con stock crítico (por debajo del mínimo) y el total de sucursales activas.
- **Gráficos en Tiempo Real:** Visualiza las entradas y salidas de mercancía de los últimos 7 días.
- **Notificaciones Push:** Si un producto llega a su nivel de re-orden (stock crítico), el sistema te enviará una alerta automática.

---

## 2. Gestión de Tiendas y Sucursales

Antes de agregar productos, necesitas definir **dónde** los vas a guardar. AlToke Pro es multi-sucursal, lo que significa que puedes controlar múltiples bodegas o locales comerciales.

### ¿Cómo crear una Tienda?
1. Dirígete a la pestaña **Tiendas** en el menú de navegación inferior.
2. Verás una lista con tus sucursales actuales. Para agregar una nueva, busca la sección **"Crear Tienda"**.
3. Ingresa los siguientes datos:
   - **Nombre de la Tienda:** (Ej. "Bodega Central", "Local Providencia").
   - **Dirección:** Ubicación física para fácil referencia.
   - **Teléfono:** (Opcional).
4. Presiona el botón **"Crear"**. La tienda aparecerá inmediatamente en tu lista.

> **💡 Tip de Operación:** Si tienes furgonetas de despacho, puedes crear una tienda llamada "Furgoneta 1" para transferir stock a ella y saber exactamente qué mercancía va en tránsito.

---

## 3. Clasificación: Categorías y Subcategorías

Un inventario ordenado es la clave del éxito. En AlToke Pro agrupas tus productos usando un sistema de dos niveles: **Categoría Principal > Subcategoría**.

### Crear una Categoría Principal
1. Ve a la pestaña **Categorías** (ícono de carpeta).
2. En la primera tarjeta, "Categorías Principales", ingresa el nombre general. 
   - *Ejemplo: Ropa, Herramientas, Alimentos.*
3. Presiona **"Crear"**.

### Crear una Subcategoría
Una vez que tienes al menos una categoría principal, puedes agregarle subdivisiones.
1. En la misma pantalla, baja hasta la sección **"Crear Subcategorías"**.
2. **Selecciona una Categoría Padre:** Usa el menú desplegable para elegir la categoría principal que creaste en el paso anterior.
3. **Nombre de Subcategoría:** Escribe el nombre de la subdivisión.
   - *Ejemplo: Si el padre es "Ropa", la subcategoría puede ser "Poleras" o "Pantalones".*
4. Presiona **"Crear Subcategoría"**.

---

## 4. Catálogo de Productos

Aquí es donde defines la "ficha técnica" de lo que vendes. Todavía no les asignaremos cantidad (eso se hace en inventario), solo los registraremos en el sistema.

### Agregar un Producto
1. Dirígete a la sección **Catálogo** o al momento de auditar presiona "Nuevo Producto".
2. Completa la ficha:
   - **Nombre:** (Ej. "Polera Básica Cuello V").
   - **Categoría:** Selecciona a qué categoría y subcategoría pertenece.
   - **SKU / Código de Barras:** Este es el código único. **Puedes presionar el ícono de la cámara aquí mismo** para escanear el código de barras del producto físico y que se llene automáticamente.
   - **Precio de Costo y Venta:** Para calcular el valor de tu inventario.
3. Presiona **Guardar**.

---

## 5. Auditoría e Inventario (Uso del Escáner)

¡Esta es la función estrella de AlToke Pro! Convierte tu teléfono en una terminal logística.

<div align="center">
  <img src="https://raw.githubusercontent.com/betorockers/AlTokePro/main/screenshot_mobile.png" alt="Escáner y App Móvil" width="300" style="border-radius: 10px; box-shadow: 0 4px 15px rgba(0,0,0,0.1);" />
</div>

### ¿Cómo auditar o sumar/restar stock?
1. Ve a la pestaña **Inventario** (ícono de caja/documento).
2. En la parte superior, asegúrate de **seleccionar la Tienda/Bodega** en la que estás físicamente trabajando.
3. Presiona el gran botón de **"Escanear Producto"** (o el ícono de código de barras).
4. **Usando la Cámara:**
   - La cámara de tu teléfono se abrirá.
   - Apunta al código de barras del producto.
   - Al detectarlo, el sistema vibrará (en Android) y cargará la ficha del producto instantáneamente.
5. **Usando Pistola USB/Bluetooth:**
   - Si prefieres usar una pistola lectora tradicional, simplemente conéctala a tu celular o PC.
   - Ubica el cursor en el buscador principal de inventario y "dispara". El sistema buscará el código al instante.

### Realizar el Movimiento (Entrada/Salida)
Una vez que el producto está en pantalla tras ser escaneado:
- Verás el stock actual en esa bodega.
- Usa los botones **[+]** o **[-]** para agregar recepciones de mercadería o registrar salidas/mermas.
- Presiona **"Confirmar"**. El movimiento queda registrado con la fecha, hora y el usuario que lo realizó.

---

## 6. Modo Offline (Sin Conexión)

Sabemos que en el fondo de una bodega o en subterráneos la señal de internet falla. AlToke Pro está blindado contra esto.

### ¿Cómo funciona?
1. Si pierdes la conexión (aparecerá un indicador rojo o de falta de red), **sigue trabajando con normalidad**.
2. Puedes seguir escaneando códigos y sumando/restando inventario. El sistema guardará todos los movimientos en la bóveda de memoria de tu celular.
3. **Sincronización:** En cuanto camines hacia una zona con señal o Wi-Fi, la app detectará la conexión y **sincronizará automáticamente en segundo plano** todos los movimientos retenidos. No perderás ni un solo dato.

---
<div align="center">
  <i>AlToke Pro es un producto impulsado por la innovación y la eficiencia operativa.</i><br>
  <b>¿Necesitas ayuda adicional?</b> Escríbenos a <a href="mailto:contacto@betograf.cl">contacto@betograf.cl</a> o a nuestro <a href="https://wa.me/56933445244">WhatsApp de Soporte</a>.
</div>
