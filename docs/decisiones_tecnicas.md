# 📘 Decisiones Técnicas del Proyecto

## 1. Introducción

Este documento establece las decisiones técnicas fundamentales adoptadas para el desarrollo del sistema de gestión del distribuidor de frutas y verduras. Su propósito es definir un marco tecnológico estable que permita avanzar en el desarrollo sin replantear herramientas o arquitectura durante etapas posteriores del proyecto.

Las decisiones aquí definidas deberán considerarse base del proyecto y solo podrán modificarse ante una justificación técnica significativa.

---

## 2. Plataforma Base

### 2.1 ERP Base Seleccionado

El sistema será desarrollado utilizando **Odoo Community Edition** como plataforma principal.

#### Motivos de elección

* Arquitectura modular extensible.
* Código abierto y altamente personalizable.
* Integración nativa entre ventas, stock y contabilidad básica.
* Uso de Python y PostgreSQL, tecnologías robustas y ampliamente utilizadas.
* Permite construir un sistema a medida evitando desarrollo desde cero.

#### Criterio de diseño

Odoo será utilizado como **framework de negocio**, no como sistema estándar cerrado.
Los módulos base serán extendidos mediante módulos personalizados propios.

---

## 3. Arquitectura Tecnológica

### 3.1 Backend

* Lenguaje principal: **Python**
* Framework interno: ORM de Odoo
* Lógica de negocio implementada mediante modelos y herencias.

---

### 3.2 Base de Datos

* Motor: **PostgreSQL**
* Gestión de datos exclusivamente mediante ORM de Odoo.
* No se realizarán modificaciones directas sobre la base de datos salvo mantenimiento técnico excepcional.

#### Principio adoptado

> Toda modificación de datos debe pasar por la lógica del sistema para garantizar trazabilidad.

---

### 3.3 Frontend

* Sistema web basado en vistas XML de Odoo.
* Uso de QWeb para reportes y documentos PDF.
* Personalizaciones visuales mediante herencia de vistas.
* Diseño responsive accesible desde dispositivos móviles.

No se desarrollará una aplicación móvil nativa en esta etapa.

---

## 4. Arquitectura Modular

El sistema se organizará mediante módulos personalizados independientes ubicados en:

```
custom_addons/
```

### Módulos previstos

* usuarios_distribuidor
* pedidos_distribuidor
* stock_distribuidor
* repartos_distribuidor
* facturacion_cc
* proveedores_distribuidor

#### Principios modulares

* Cada módulo tendrá responsabilidad única.
* Evitar dependencias innecesarias entre módulos.
* Extender módulos oficiales antes de reinventar funcionalidades existentes.
* Mantener desacoplamiento para facilitar mantenimiento futuro.

---

## 5. Control de Versiones

### Herramienta seleccionada

* Git
* Repositorio remoto en GitHub.

### Alcance del versionado

Se versionará:

* Módulos personalizados.
* Documentación técnica.
* Archivos de configuración necesarios.

No se versionará:

* Base de datos (la información histórica permanecerá almacenada íntegramente dentro del sistema y accesible mediante reportes y filtros desde la interfaz web, pero no será gestionada mediante control de versiones Git).
* Archivos temporales.
* Addons oficiales de Odoo.

---

### Convención de commits

Formato sugerido:

```
[MODULO] descripcion corta del cambio
```

Ejemplo:

```
[stock] agregado movimiento de devolucion
```

---

## 6. Entorno de Desarrollo

### Desarrollo local

El sistema será desarrollado inicialmente en entorno local con:

* Odoo ejecutándose en localhost.
* Base de datos local PostgreSQL.
* Instalación manual de módulos personalizados.

Objetivos del entorno local:

* Desarrollo rápido.
* Pruebas seguras.
* Iteración continua.

---

## 7. Infraestructura de Producción

### Plataforma Cloud

El sistema será desplegado en **Amazon Web Services (AWS)**.

Servicios previstos:

* EC2 → servidor de aplicación Odoo.
* PostgreSQL (instancia propia o servicio administrado).
* Nginx como proxy inverso.
* Certificados SSL para conexión segura HTTPS.

---

### Modelo de costos

* Infraestructura bajo modelo de pago mensual.
* Escalable según crecimiento del negocio.
* Posibilidad de ampliar recursos sin migraciones complejas.

---

## 8. Dominio y Acceso Web

El sistema utilizará subdominios asociados al dominio principal de la empresa desarrolladora.

Ejemplo:

```
cliente.simpliarg.com
```

#### Ventajas

* Identidad de marca integrada.
* Reducción de costos de dominios adicionales.
* Escalabilidad para múltiples clientes futuros.

---

## 9. Seguridad

Principios adoptados:

* Control de acceso basado en roles.
* Restricción de datos mediante reglas de registro.
* Acceso HTTPS obligatorio en producción.
* No exposición directa de la base de datos a internet.

---

## 10. Estrategia de Desarrollo

Se adopta un enfoque incremental por bloques:

1. Usuarios
2. Pedidos
3. Stock
4. Repartos
5. Facturación y cuentas corrientes
6. Ajustes y optimización

Cada bloque deberá estar funcional antes de avanzar al siguiente.

---

## 11. Principios Técnicos del Proyecto

* El sistema debe adaptarse al negocio real.
* Evitar soluciones genéricas rígidas.
* Priorizar trazabilidad sobre automatización excesiva.
* Toda operación importante debe dejar registro.
* Mantener simplicidad operativa para usuarios no técnicos.

---

## 12. Criterio de Estabilidad Técnica

Una vez iniciado el desarrollo funcional:

* No se cambiará la plataforma base.
* No se migrará de base de datos.
* No se modificará la arquitectura general salvo causa crítica.

Esto garantiza continuidad y evita retrabajos costosos.

---
