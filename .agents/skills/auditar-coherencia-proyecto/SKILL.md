---
name: auditar-coherencia-proyecto
description: >-
  Audita la coherencia entre la documentación académica (informes, diagramas UML,
  DER y planificación en docs/) y la implementación real en backend, frontend e
  infra. Úsalo cuando el usuario pida redactar un informe de hito, generar
  diagramas UML/DER o verificar que la documentación coincida con el código.
---

# Auditoría de Coherencia entre Documentación y Código

Sigue este procedimiento para asegurar que los entregables de `docs/` (Semanas 3, 8, 13 y 17) reflejen fielmente el software real del Grupo 6.

## Pasos

1. **Verificar Esquema de Datos (DER vs. Migraciones)**:
   - Inspecciona las migraciones en `../backend/database/migrations/` y los modelos en `../backend/app/Models/`.
   - Comprueba que los diagramas en `docs/uml/` incluyan las tablas clave: `users`, `branches`, `locations`, `categories`, `products` (con `specs` JSON y `min_stock`), `product_stocks`, `inventory_movements` (y su detalle) y `audit_logs`.

2. **Verificar Casos de Uso y Diagramas de Secuencia vs. Endpoints**:
   - Contrasta los actores (`Administrador`, `Personal de Almacén`, `Personal de Ventas`) y los casos de uso con la tabla maestra en `../backend/.agents/rules/contrato-endpoints.md`.
   - En los diagramas de secuencia de movimientos de stock, refleja el paso de validación y bloqueo de fila (`SELECT ... FOR UPDATE` en MySQL 8.4 InnoDB) dentro de la transacción.

3. **Verificar Prototipos vs. Vistas Vue 3**:
   - Revisa `../frontend/src/views/` para asegurar que los nombres de pantallas y campos en `docs/prototipos/` e `informes/` coincidan con los módulos de **Carlos** (`catalogo`, `movimientos`, `auth`) y **Franklin** (`consultas`, `reportes`).

4. **Validar Reglas de Forma (Checklist de `REVISION_PLAN.md`)**:
   - ¿Dice MySQL 8.4 en vez de PostgreSQL?
   - ¿Está redactado íntegramente en 3ra persona y sin textos de plantilla de la docente?
   - ¿Están las 4 citas y referencias en APA 7 ordenadas alfabéticamente?
   - ¿El reparto de actividades respeta el rol real de Anthony (BD, Consultas y QA), William (API y Transacciones), Carlos (UI/UX y Almacén) y Franklin (Requisitos, Ventas y Reportes)?
