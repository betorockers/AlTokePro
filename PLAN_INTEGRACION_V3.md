# Plan de Integración: BetoGraf Almacenero 🤝 AlToke Pro

El objetivo es conectar **BetoGraf Almacenero** (Punto de Venta en la tienda) y **AlToke Pro** (WMS en la bodega) para que operen como un ecosistema unificado. Esto permitirá a los clientes mantener su flujo de caja y ventas en Almacenero, mientras realizan despachos, recepciones y **auditorías ciegas** de inventario con AlToke Pro.

## Arquitectura Propuesta

Dado que **BetoGraf Almacenero** usa SQLite con sincronización a Supabase, y **AlToke Pro** usa FastAPI con PostgreSQL/Supabase, la mejor forma de integrarlos es a través de **APIs REST y Webhooks**, o aprovechando Supabase como punto de verdad.

1. **Catálogo de Productos (Master):** BetoGraf Almacenero será el maestro de creación de productos, precios y códigos de barra. 
2. **Control de Bodega (Master):** AlToke Pro será el maestro de las existencias reales, mermas y auditorías físicas.

## Flujo de Auditoría Cruzada (Auditoría Ciega)

1. **Preparación:** El encargado de bodega abre AlToke Pro e inicia una "Auditoría Ciega". La app *no* le muestra el stock teórico (el que dice BetoGraf Almacenero), solo le pide escanear.
2. **Conteo:** El encargado escanea los códigos de barra (`codigo_barras` en Almacenero se mapea como `sku` en AlToke Pro) y cuenta las unidades físicas.
3. **Cruce de Datos:** AlToke Pro consulta a BetoGraf Almacenero (vía API o BD compartida) el "Stock Teórico" al instante.
4. **Conciliación:** Se genera el reporte de diferencias (Mermas o Sobrantes).
5. **Ajuste Automático:** Una vez aprobada la auditoría por el administrador, AlToke Pro envía una instrucción a BetoGraf Almacenero para aplicar un "Ajuste de Inventario", igualando el stock del punto de venta con la realidad de la bodega.

## Cambios Propuestos (A Futuro)

### Componente 1: BetoGraf Almacenero (Django / SQLite)
- **[MODIFICAR]** `database/models.py`: Añadir un campo `id_nube` (UUID) o asegurar que el `codigo_barras` sea estricto para emparejar con AlToke Pro.
- **[NUEVO]** `api/`: Crear un par de endpoints (REST API local) o webhooks que permitan a AlToke Pro consultar el stock actual y enviar "Ajustes de Inventario".
- **[MODIFICAR]** `seriales_supabase_sync.sql`: Integrar la lógica para que los productos creados en la caja se envíen a la tabla de productos de AlToke Pro.

### Componente 2: AlToke Pro (FastAPI)
- **[MODIFICAR]** `models/product.py`: Mapear el `sku` estrictamente con el `codigo_barras` de Almacenero.
- **[NUEVO]** `routers/sync.py`: Endpoints para recibir la creación de nuevos productos desde Almacenero.
- **[MODIFICAR]** `models/audit.py`: Añadir el estado de `auditoria_ciega` (booleano) para ocultar las cantidades teóricas en el frontend durante el conteo.

## Consideraciones Estratégicas
1. **Vía de Sincronización:** Definir si ambas apps se hablarán en tiempo real a través de **Supabase** (en la nube) o si AlToke Pro consumirá una **API directa** instalada en la red local del PC del cliente (donde corre BetoGraf Almacenero).
2. **Prioridad de Inventario:** Si un cliente vende algo en la caja mientras el bodeguero está contando ese mismo pasillo, se deberá definir cómo manejar ese desfase (bloquear la venta del producto o congelar el stock temporalmente).
