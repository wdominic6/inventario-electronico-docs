# Revisión del Plan de Proyecto – Grupo 6

Documento revisado: `PlanificacionProyecto_Grupo6.docx.txt` (Plan de Proyecto, semana 3).
Fecha de revisión: 02/11/2026.

Este informe recoge observaciones y **texto sugerido** para corregir el `.docx` original. Están ordenadas por prioridad.

| Prioridad | Significado |
|---|---|
| 🔴 Alta | Contradicción con el producto real o error de forma que la docente notará |
| 🟡 Media | Incoherencia interna o vacío en el alcance |
| 🟢 Baja | Mejora de redacción o de presentación |

---

## 🔴 1. Base de datos: el documento dice PostgreSQL, el proyecto usa MySQL 8.4
**Sección 13.** El entorno Docker (`infra/compose.yaml`) y el backend usan **MySQL 8.4**.

**Texto sugerido (fila "Base de datos"):**
> MySQL 8.4 (LTS), motor relacional con soporte de transacciones ACID (InnoDB) y bloqueo a nivel de fila, necesario para registrar entradas y salidas de stock concurrentes desde varias sucursales sin inconsistencias.

Si en el Informe de Análisis y Diseño se menciona el cambio, justificarlo según la nota de la plantilla ("podrán modificarse… cuando exista una justificación técnica").

## 🔴 2. Faltan referencias de dos antecedentes
**Sección Referencias.** Solo están Part-DB y Lugmaña (2025). Faltan:

```text
Chávez Palomino, A. M. (2024). Implementación de un sistema web y el control de inventario para una empresa de Lima, 2023 [Tesis de pregrado, Universidad Nacional del Callao]. Repositorio Institucional UNAC. https://hdl.handle.net/20.500.12952/9110

Lima Camizan, J. W. (2024). Sistema web basado en el modelo ABC, para el control de inventarios en la empresa Negocios Prieto Company S.A.C. [Tesis de licenciatura, Universidad Católica Santo Toribio de Mogrovejo]. Repositorio de Tesis USAT. <URL del repositorio>
```
> ⚠️ **Verificar el año de Chávez Palomino:** según el repositorio de la UNAC se publicó en **2024**; el "2023" forma parte del título. El documento dice "Año: 2023". Para Lima Camizan, copiar la URL exacta del repositorio USAT.

Además, ordenar las referencias **alfabéticamente** (APA 7): Chávez Palomino → Lima Camizan → Lugmaña Llumiquinga → Part-DB.

## 🔴 3. Faltan citas en el texto de los antecedentes 2, 3 y 4
Solo el antecedente 1 tiene cita "(Part-Db, s. f.)". Añadir al final de cada "Descripción breve":
- Antecedente 2: `(Chávez Palomino, 2024)`
- Antecedente 3: `(Lugmaña Llumiquinga, 2025)`
- Antecedente 4: `(Lima Camizan, 2024)`

## 🔴 4. El antecedente 4 está en primera persona
> "Como Arquitecto de Base de Datos y Tester, este antecedente **me** proporciona…"

Además, "Arquitecto de Base de Datos y Tester" no es un rol definido en la sección 14.

**Texto sugerido:**
> Este antecedente proporcionará al proyecto una guía metodológica validada para estructurar el diagrama Entidad-Relación (DER) del sistema logístico, asegurando que las tablas críticas (productos electrónicos, especificaciones técnicas y movimientos) estén correctamente normalizadas. Asimismo, servirá como referencia para diseñar los planes y casos de prueba, verificando que las transacciones de actualización de stock funcionen sin errores de concurrencia cuando varias sucursales operen al mismo tiempo.

## 🔴 5. Quedó texto de instrucciones de la plantilla
Borrar los párrafos que son instrucciones de la docente y no contenido del grupo:
- Secc. 8: "El grupo deberá realizar una búsqueda inicial…", "Podrán considerarse artículos…", "Se presentará como mínimo…", "El grupo deberá explicar…", "Los antecedentes deberán redactarse…".
- Secc. 11: "Identificar las principales funcionalidades…".
- Secc. 12: "Seleccionar el modelo de proceso…", "Explicar por qué el modelo…", "No será suficiente presentar…", "Explicar cómo se proyecta…", "Indicar los principales productos…".
- Secc. 13: "Indicar preliminarmente…".
- Secc. 14: "Establecer la organización inicial…".
- Secc. 15: "Planificar las principales actividades…", "El cronograma deberá ser coherente…", "A partir de estos hitos, el grupo deberá elaborar…".
- Referencias: "Registrar las fuentes académicas…", "Las referencias deberán presentarse…".
- Todo el apartado **"INDICACIONES FINALES"**.
- Valorar también quitar la introducción genérica de la plantilla (párrafos "El Plan de Proyecto constituye…" y "Por tratarse de un documento de planificación…").

---

## 🟡 6. La justificación del modelo (12.1) contradice el alcance
> "…futuras tecnologías que permitan a los usuarios una mejor referencia al producto que están observando **para su posterior compra**…"

Esto describe una tienda en línea, y el **e-commerce está excluido** en la sección 10. Además dice "los modelos iterativo e incremental **son**", cuando se trata de **un solo modelo**.

**Texto sugerido:**
> Se eligió el modelo iterativo e incremental porque los requisitos del sistema (especificaciones técnicas de los componentes, reglas de stock y necesidades de cada rol) se conocerán progresivamente durante la Ingeniería de Requisitos y es previsible que cambien. El modelo permite entregar el producto en incrementos funcionales (primero autenticación y catálogo; luego movimientos logísticos; después consultas, reportes y alertas) alineados con los hitos del curso (semanas 8, 13 y 17). Cada iteración incluye análisis, diseño, construcción y pruebas, de modo que los errores se detectan pronto y la retroalimentación de la docente y de los usuarios se incorpora en el incremento siguiente. Este enfoque se ajusta a un equipo de cuatro integrantes con roles de backend y frontend que pueden trabajar en paralelo sobre módulos independientes.

## 🟡 7. Se mezcla vocabulario de Scrum sin explicarlo
Las secciones 12.3 y 6.2 mencionan *Product Backlog* e *historias de usuario* (artefactos de Scrum), pero el modelo elegido es iterativo-incremental. No es un error, pero conviene aclararlo en 12.2:
> Como herramientas de apoyo se usarán historias de usuario y un backlog priorizado, gestionados en un tablero de GitHub Projects, para planificar el contenido de cada iteración.

## 🟡 8. Funciones mencionadas que no están en el alcance
- **Sección 7 (Ventas):** "…y **reserva de artículos** para ventas".
- **Sección 7 (Proveedores):** "Recepción clara de **órdenes de compra**…".

Ninguna aparece en las secciones 10 u 11. Hay que **añadirlas** al alcance o **declararlas fuera de alcance**. Por ejemplo, añadir en "El proyecto no comprenderá":
> Gestión de órdenes de compra a proveedores ni reservas de mercadería: el sistema registrará las entradas una vez recibida la mercadería y las salidas efectivas, pero no gestionará el ciclo de compra ni la reserva previa de stock.

## 🟡 9. Multi-sucursal sin módulo de sucursales
Todo el documento habla de "múltiples sucursales" y de "disponibilidad cruzada", pero ningún módulo permite **registrar sucursales o almacenes**. Para que el stock sea por sucursal hace falta.

**Sugerencia (secc. 10, nuevo ítem):**
> Módulo de Sucursales y Ubicaciones: registro de sucursales/almacenes y de ubicaciones físicas (estante, nivel, casillero), de modo que el stock de cada componente se controle por sucursal y ubicación, incluidos los traslados entre sucursales.

## 🟡 10. "Tiempo real" sin tecnología definida
Las secciones 6.1, 9 y 16 prometen actualización "en tiempo real", pero la sección 13 no indica cómo se logrará. Precisarlo en la 13 ("Otras herramientas"):
> Para reflejar los cambios de stock en tiempo real se evaluará el uso de WebSockets mediante Laravel Reverb; como alternativa mínima, la interfaz consultará la API periódicamente (polling).

Otra opción es suavizar el término a "información actualizada al instante de cada consulta".

## 🟡 11. Herramientas de prueba incompletas
La sección 13 solo menciona Postman. El objetivo específico 4 habla de "pruebas técnicas de endpoints y **concurrencia**", que no se pueden automatizar con Postman solo.

**Texto sugerido (fila "Herramientas para pruebas"):**
> PHPUnit (pruebas unitarias y de integración de la API Laravel, ya incluido en el framework), Postman (pruebas manuales y colecciones de endpoints), Vitest (pruebas de componentes Vue) y las herramientas de desarrollo del navegador.

## 🟡 12. Reparto de carga y roles incoherente en el cronograma
- **Anthony Junior** tiene en la sección 14 el rol "BD, Consultas y **QA**", pero las semanas de pruebas (**12 y 14**) están asignadas a **Franklin** (frontend). Anthony solo aparece en las semanas 4, 5 y 7.
- **Carlos Daniel** solo es responsable en las semanas 7, 10 y 15.
- La semana 6 ("estructura de la base de datos") va a Franklin (frontend), no a Anthony (BD).

**Sugerencia de reasignación:**

| Semana | Actual | Sugerido |
|---|---|---|
| 6 | Franklin | Franklin y Anthony (modelo de datos) |
| 10 | Carlos | Carlos y Franklin |
| 11 | William | William y Anthony (consultas de stock) |
| 12 | Franklin | Franklin (reportes) y Anthony (pruebas técnicas) |
| 14 | Franklin | Anthony (QA) y Franklin |

## 🟢 13. Cronograma sin fechas
Tomando la semana 3 = 16/09/2026 (fecha de presentación):

| Semana | Fecha (miércoles) |
|---|---|
| 3 | 16/09/2026 |
| 8 | 21/10/2026 |
| 13 | 25/11/2026 |
| 17 | 23/12/2026 |

> ⚠️ A la fecha de esta revisión (02/11/2026, **semana 10**), el hito de la semana 8 ya pasó y el código está en el estado previsto para la semana 9 (esqueleto de Laravel y Vue con Docker). Conviene repriorizar las semanas 10–12.

## 🟢 Otras observaciones menores
- Secc. 2 y portada: hay un espacio sobrante antes de "Vilca Carpio Carlos Daniel".
- Secc. 13: escribir "Vue.js 3" y "Laravel 13" con versión, para mayor precisión.
- Secc. 12.2: decir cuántas iteraciones habrá (p. ej., 3 iteraciones: semanas 4–8, 9–13 y 14–17).
- Secc. 1/9: unificar el nombre del producto (algunas veces "Sistema Web de Gestión Logística…" y otras "herramienta").
- Revisar la ortografía de "Part-Db" → "Part-DB" en la cita del antecedente 1.
