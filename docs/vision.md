# Visión del Sistema – Distribuidor de Frutas y Verduras
# 1. Objetivo del Sistema

El objetivo del sistema es digitalizar, ordenar y centralizar la operación diaria de un distribuidor de frutas y verduras mediante una plataforma web desarrollada sobre Odoo y altamente personalizada al modelo real del negocio. El sistema permitirá gestionar pedidos, clientes, repartos, stock, proveedores y movimientos de dinero desde un único lugar, garantizando trazabilidad completa, control de inventario en tiempo real y claridad en las cuentas corrientes, reduciendo errores operativos y eliminando la dependencia de memoria o registros informales.

---

# 2. Alcance del Sistema (Qué NO hará por ahora)

Para mantener un desarrollo controlado y enfocado, el sistema no incluirá en esta primera versión:

* Registro público de usuarios o auto-creación de cuentas.
* Tienda online abierta al público general.
* Integraciones automáticas con pasarelas de pago externas.
* Facturación electrónica automática con organismos fiscales.
* Optimización automática de rutas de reparto mediante algoritmos.
* Aplicación móvil nativa (el sistema será web responsive).
* Integraciones con marketplaces externos.
* Automatizaciones financieras complejas o contabilidad completa empresarial.

Estas funcionalidades podrán evaluarse en futuras versiones una vez estabilizado el sistema principal.

---

# 3. Problemas del Negocio que el Sistema Busca Solucionar

El distribuidor actualmente presenta un alto volumen de ventas acompañado por desorganización operativa, lo que genera pérdidas de tiempo, errores y decisiones basadas en suposiciones. El sistema busca resolver:

* Falta de control real del stock disponible.
* Compras innecesarias o faltantes de mercadería por desconocimiento del inventario.
* Ausencia de trazabilidad sobre ingresos y egresos de productos.
* Dificultad para conocer saldos reales de clientes y proveedores.
* Gestión manual y desordenada de pedidos.
* Falta de seguimiento claro de repartos y entregas.
* Devoluciones de mercadería sin registro formal.
* Dependencia de la memoria del administrador para operar el negocio.
* Información dispersa en múltiples medios (papel, mensajes, recuerdos).

El sistema permitirá tomar decisiones basadas en datos reales y registrados.

---

# 4. Actores del Sistema

# Administrador

Responsable de la gestión completa del sistema. Puede crear y administrar clientes, productos, proveedores, pedidos, movimientos de stock y registros financieros. Define precios, controla operaciones y supervisa el estado general del negocio.

Responsabilidades principales:

* Alta y gestión de clientes.
* Gestión de productos y stock.
* Registro de compras y ventas.
* Control de cuentas corrientes.
* Supervisión de repartos.

---

# Cliente

Usuario del sistema con acceso limitado a su propia información comercial.

Puede:

* Realizar pedidos.
* Consultar pedidos anteriores.
* Ver el estado de pedidos actuales.
* Consultar su saldo en cuenta corriente.

No puede:

* Acceder a información de otros clientes.
* Modificar precios o stock.
* Administrar el sistema.

---

# Repartidor

Usuario operativo encargado de las entregas físicas.

Puede:

* Visualizar pedidos asignados.
* Ver detalles de entrega (cliente, dirección, productos).
* Marcar pedidos como entregados.
* Registrar pagos y métodos de pago.
* Informar devoluciones de mercadería.

No puede:

* Crear pedidos.
* Modificar precios.
* Administrar clientes o productos.

---

# Proveedor (Actor Pasivo)

Entidad externa que suministra mercadería al distribuidor. No interactúa directamente con el sistema, pero su información es utilizada para registrar compras, ingresos de stock y movimientos de cuenta corriente.

---

# 5. Principios del Sistema

* El sistema será altamente personalizado, evitando comportamientos genéricos.
* Ningún flujo será universal: clientes pueden operar bajo reglas comerciales distintas.
* Toda operación deberá generar trazabilidad.
* El stock nunca se modificará manualmente sin registrar un movimiento.
* El sistema debe adaptarse al negocio real, no forzar al negocio a cambiar su forma de trabajo.

---

# 6. Resultado Esperado

Al finalizar el desarrollo, el distribuidor contará con un sistema centralizado que permita operar diariamente con información confiable, reducir errores humanos, mejorar el control financiero y escalar el negocio con procesos claros y repetibles.
