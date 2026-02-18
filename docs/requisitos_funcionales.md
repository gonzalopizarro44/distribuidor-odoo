# 📘 Requisitos del Sistema – Ingeniería de Requisitos

## 1. Introducción

Este documento define los requisitos funcionales y no funcionales del sistema de gestión para un distribuidor de frutas y verduras. Su objetivo es establecer de forma clara qué funcionalidades deberá cumplir el sistema y bajo qué condiciones deberá operar, sirviendo como base para el diseño técnico, desarrollo modular y validación del proyecto.

El sistema estará orientado a reflejar el funcionamiento real del negocio, priorizando flexibilidad operativa, trazabilidad y control total sobre stock, pedidos y movimientos financieros.

---

# 2. Requisitos Funcionales

Los requisitos funcionales describen las acciones y comportamientos que el sistema debe permitir.

---

## 2.1 Bloque Usuarios

### RF-U1 — Gestión de roles

El sistema deberá permitir la existencia de distintos roles de usuario con permisos diferenciados:

* Administrador
* Cliente
* Repartidor

Cada rol tendrá acceso únicamente a las funcionalidades autorizadas.

---

### RF-U2 — Administración de usuarios

El administrador deberá poder:

* Crear usuarios manualmente.
* Asignar roles.
* Activar o desactivar accesos.
* Asociar usuarios a clientes existentes.

No existirá registro público automático.

---

### RF-U3 — Acceso del Cliente

El cliente deberá poder:

* Crear pedidos.
* Consultar pedidos anteriores.
* Visualizar estado del pedido actual.
* Consultar saldo de cuenta corriente.

El cliente solo podrá acceder a su propia información.

---

### RF-U4 — Acceso del Repartidor

El repartidor deberá poder:

* Visualizar pedidos asignados.
* Ver detalles de entrega.
* Marcar pedidos como entregados.
* Registrar pagos realizados.
* Registrar devoluciones parciales.

---

### RF-U5 — Control de permisos

El sistema deberá impedir accesos no autorizados mediante reglas de seguridad y filtrado de datos por usuario.

---

## 2.2 Bloque Pedidos

### RF-P1 — Creación de pedidos

El sistema deberá permitir crear pedidos asociados a un cliente incluyendo:

* Productos
* Cantidades
* Unidad de medida
* Precio aplicado al cliente

---

### RF-P2 — Estados del pedido

Un pedido deberá atravesar los siguientes estados:

* Borrador
* Confirmado
* Preparado
* En reparto
* Entregado
* Cerrado

---

### RF-P3 — Personalización comercial

El sistema deberá permitir:

* Precios distintos por cliente.
* Unidades de venta distintas por cliente.
* Facturación opcional o parcial.

---

### RF-P4 — Historial

Todos los pedidos deberán quedar almacenados y consultables.

---

## 2.3 Bloque Stock

### RF-S1 — Unidad base

El sistema deberá manejar una unidad base estandarizada (kilogramo) para el control interno del inventario.

---

### RF-S2 — Ingreso de mercadería

El administrador deberá poder:

* Seleccionar productos existentes.
* Incrementar stock.
* Asociar proveedor.
* Crear proveedor desde el mismo flujo si no existe.

---

### RF-S3 — Movimientos de stock

El stock solo podrá modificarse mediante movimientos registrados:

* Ingreso
* Egreso por pedido
* Devolución
* Ajuste manual autorizado

---

### RF-S4 — Devoluciones

El sistema deberá permitir devolver productos desde pedidos entregados, reintegrando automáticamente el stock.

---

### RF-S5 — Reportes de inventario

El sistema deberá generar reportes filtrables por fecha mostrando:

* Stock inicial
* Ingresos
* Egresos
* Stock final del día

---

## 2.4 Bloque Proveedores

### RF-PR1 — Gestión de proveedores

El administrador deberá poder:

* Crear proveedores.
* Editar datos.
* Asociarlos a compras de mercadería.

---

### RF-PR2 — Compras

Cada compra deberá registrar:

* Proveedor
* Productos
* Cantidades
* Fecha
* Impacto en stock

---

## 2.5 Bloque Facturación y Pagos

### RF-F1 — Cuenta corriente clientes

El sistema deberá registrar movimientos financieros:

* Deudas
* Pagos
* Ajustes

---

### RF-F2 — Cuenta corriente proveedores

El sistema deberá registrar obligaciones económicas hacia proveedores.

---

### RF-F3 — Registro flexible de pagos

El sistema deberá permitir:

* Pagos totales o parciales.
* Métodos múltiples (efectivo, transferencia, combinados).
* Registro manual de pagos realizados fuera del sistema.

---

### RF-F4 — Trazabilidad financiera

Todo movimiento deberá indicar:

* Usuario responsable
* Fecha
* Origen del movimiento
* Método de pago

---

## 2.6 Bloque Repartos

### RF-R1 — Asignación de reparto

El administrador deberá poder asignar pedidos a repartidores.

---

### RF-R2 — Gestión de entrega

El repartidor deberá poder:

* Confirmar entrega.
* Registrar cobro.
* Informar devoluciones.

---

### RF-R3 — Impacto automático

Las acciones de reparto deberán afectar automáticamente:

* Estado del pedido.
* Stock.
* Cuenta corriente.

---

# 3. Requisitos No Funcionales

---

## RNF-1 — Usabilidad

El sistema deberá ser simple y rápido para usuarios no técnicos.

---

## RNF-2 — Trazabilidad

Toda acción relevante deberá quedar registrada.

---

## RNF-3 — Flexibilidad comercial

El sistema deberá permitir configuraciones distintas por cliente sin comportamientos rígidos o universales.

---

## RNF-4 — Seguridad

Los usuarios solo podrán acceder a datos permitidos según su rol.

---

## RNF-5 — Escalabilidad

El sistema deberá permitir agregar nuevos módulos sin modificar los existentes.

---

## RNF-6 — Disponibilidad

El sistema deberá poder ejecutarse en servidores cloud con acceso web permanente.

---

# 4. Criterio de Aceptación General

El sistema se considerará funcional cuando:

* El flujo completo desde pedido hasta entrega pueda realizarse dentro del sistema.
* El stock refleje exactamente la realidad física.
* Los saldos financieros coincidan con la operación real del negocio.
* Cada actor pueda operar únicamente dentro de su rol definido.

---

# 5. Observación de Diseño

El sistema no será un ERP genérico adaptado parcialmente, sino una personalización profunda orientada al modelo operativo específico del distribuidor.
