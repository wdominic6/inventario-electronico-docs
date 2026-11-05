# Documentación Académica y Técnica – Grupo 6 (UNA Puno 2026-II)

Repositorio `inventario-electronico-docs` del proyecto **Sistema Web de Gestión Logística e Inventario de Productos Electrónicos**.
- **Universidad**: Universidad Nacional del Altiplano (UNA Puno) – Escuela Profesional de Ingeniería de Sistemas.
- **Curso**: Ingeniería de Software (Semestre 2026-II).
- **Docente**: Ing. Marga Isabel Ingaluque Arapa.

## Integrantes y Roles Oficiales
| Integrante | Rol Oficial | Dominio en Código y Documentación |
| :--- | :--- | :--- |
| **Quispe Cruz Anthony Junior** | Desarrollador Backend (Base de Datos, Consultas y QA) | DER, modelo relacional MySQL 8.4, historias de usuario, endpoints de consultas/reportes y plan/casos de prueba (PHPUnit y concurrencia) |
| **Quispe Huaman Franklin Victor** | Desarrollador Frontend (Requisitos, Módulo Ventas y Reportes) | Especificación de requisitos, arquitectura de módulos, vistas de consultas multi-sucursal, dashboard gerencial y alertas de bajo stock |
| **Tito Monteagudo William Dominic** | Desarrollador Backend (Arquitectura API y Transacciones) | Entorno Docker (`infra`), arquitectura API REST (Laravel 13 + Sanctum), catálogo técnico y motor transaccional ACID (`lockForUpdate`) |
| **Vilca Carpio Carlos Daniel** | Desarrollador Frontend (UI/UX y Módulo de Almacén) | Prototipos UI/UX, diseño responsivo Vue 3.5, vistas de autenticación/usuarios, catálogo con ubicación en estantería y movimientos de almacén |

## Hitos del Semestre
- **Semana 3 (16/09/2026)**: Plan de Proyecto de Software (`PlanificacionProyecto_Grupo6.docx.txt` y `REVISION_PLAN.md`).
- **Semana 8 (21/10/2026)**: Informe Técnico de Análisis y Diseño (`informes/`, `uml/`, `prototipos/`).
- **Semana 13 (25/11/2026)**: Informe Técnico de Construcción y Verificación.
- **Semana 17 (23/12/2026)**: Informe Técnico Final + Producto de Software Funcional.

## Regla Principal para el Agente
Cualquier informe, diagrama UML (Casos de Uso, Clases, Secuencia), DER o especificación de requisitos que redactes o actualices en este repositorio **debe coincidir exactamente** con:
1. Las correcciones de `REVISION_PLAN.md`.
2. El stack real implementado en `../infra`, `../backend` y `../frontend`.
3. El contrato de endpoints definido en `../backend/.agents/rules/contrato-endpoints.md`.
