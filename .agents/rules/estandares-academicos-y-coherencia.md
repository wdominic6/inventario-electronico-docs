# Estándares Académicos y Coherencia Técnica (`docs`)

Al redactar o revisar documentos en `informes/`, `uml/`, `prototipos/` o en la planificación del Grupo 6, aplica estrictamente las siguientes reglas:

## 1. Coherencia con el Producto Real (Prohibido Contradecir el Código)
- **Motor de Base de Datos**: El sistema utiliza **MySQL 8.4 (LTS)** con motor **InnoDB** (transacciones ACID y bloqueo a nivel de fila `FOR UPDATE`). **No menciones PostgreSQL**, salvo para justificar técnicamente la migración a MySQL 8.4.
- **Stack Backend y Frontend**: Especifica siempre las versiones reales: **Laravel 13 (PHP 8.4)** con **Laravel Sanctum** en el backend, **Vue.js 3.5 (Pinia 4, Vue Router 5, Vite 8)** en el frontend y **Docker Compose + Nginx** en infraestructura.
- **Herramientas de Prueba**: Menciona **PHPUnit 12** (pruebas automatizadas de endpoints y concurrencia en Laravel), **Postman** (pruebas de colecciones API) y **Oxlint / ESLint** en frontend.
- **Límites de Alcance (Sección 10)**:
  - El sistema es de **uso logístico interno multi-sucursal** para pymes de componentes electrónicos.
  - **Excluidos del alcance**: Comercio electrónico (tienda virtual para clientes finales / pasarelas de pago), facturación electrónica SUNAT, contabilidad/planillas, apps móviles nativas, órdenes de compra a proveedores y reservas previas de mercadería.
  - **Incluidos en el alcance**:
    1. Seguridad, Roles (`Administrador`, `Almacén`, `Ventas`) y Auditoría.
    2. Catálogo Técnico (con especificaciones electrónicas: voltaje, resistencia, tolerancia, encapsulado) + Sucursales y Ubicaciones físicas (estante, nivel, casillero).
    3. Movimientos Logísticos Transaccionales (Entradas por compras, Salidas por ventas/bajas y Traslados entre sucursales).
    4. Consultas en Tiempo Real de disponibilidad cruzada entre sucursales.
    5. Reportes Estratégicos (rotación ABC, Kardex) y Alertas de Bajo Stock (`min_stock`).

## 2. Redacción Académica y Formato APA 7
- **Voz gramatical**: Redacta siempre en **tercera persona impersonal** (ejemplo: *"Este antecedente proporcionará al proyecto..."*). Está prohibido usar primera persona (*"me proporciona"*, *"nosotros hicimos"*).
- **Limpieza de plantillas**: Nunca dejes párrafos de instrucciones de la docente (como *"El grupo deberá explicar..."* o *"INDICACIONES FINALES"*) dentro de los entregables finales.
- **Citas y Referencias (APA 7)**:
  - Todos los antecedentes deben llevar cita en el texto: `(Part-DB, s. f.)`, `(Chávez Palomino, 2024)`, `(Lugmaña Llumiquinga, 2025)`, `(Lima Camizan, 2024)`.
  - La lista de referencias final debe incluir las 4 fuentes completas ordenadas alfabéticamente.

## 3. Modelo de Proceso: Iterativo e Incremental
- Se trata de **un solo modelo** (*el modelo iterativo e incremental*, en singular).
- Se estructura en **3 iteraciones** alineadas con los hitos del sílabo:
  - **Iteración 1 (Semanas 4–8)**: Ingeniería de requisitos, diseño arquitectónico, DER, prototipos y esqueleto Docker + autenticación y catálogo base.
  - **Iteración 2 (Semanas 9–13)**: Construcción e integración de catálogo técnico, sucursales/ubicaciones, motor transaccional de entradas/salidas/traslados y consultas multi-sucursal.
  - **Iteración 3 (Semanas 14–17)**: Reportes, alertas de stock mínimo, pruebas de concurrencia y validación integral para el despliegue final.
