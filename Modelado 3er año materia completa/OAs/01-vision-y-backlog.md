# 01 · Visión y backlog — FBA Viviendas (borrador para revisión)

> Borrador. Nada cargado todavía en GitHub. Puntos en escala Fibonacci. Prioridad MoSCoW.

## Visión del producto

Para el personal de **FBA Viviendas** (Ventas, Administración, Cobranzas, Adjudicación y Fabricación), que hoy trabaja con planillas Excel separadas, papel y WhatsApp, **FBA Gestión** es un sistema web que unifica en un único registro (ID por proyecto, ej. FBA001) los datos del cliente, el presupuesto, los pagos, el contrato y la orden de fabricación. A diferencia de las planillas actuales, valida los datos antes de pasar un pedido a Fabricación, calcula pagos y adjudicación al 70 % (cuota 7) automáticamente, deja historial de cada cambio y muestra el estado de cada vivienda. Objetivo: eliminar errores de transcripción, duplicación de versiones y papeles perdidos (mandato ampliado de OAS).

## Roles

Vendedor · Administrativo/a · Cobranzas · Adjudicación · Capataz (Fabricación) · Dirección/Socio · Cliente (solo informado, fuera de alcance en esta etapa).

## Épicas y features (con trazabilidad a OAS)

| Épica | Features | Sale de (trabajo de campo OAS) |
|---|---|---|
| **E1 · Registro único de clientes y proyectos** | F1.1 Alta de cliente/proyecto con ID único · F1.2 Presupuesto y condiciones de venta | Problema 2 (duplicación de datos); soluciones 2.1; soluciones aplicadas 1.1 y 1.2; mandato ampliado obj. 2; entrevista a Ventas (contado / financiado) |
| **E2 · Pagos, cobranzas y adjudicación** | F2.1 Registro de pagos y plan de cuotas · F2.2 Seguimiento de mora y recordatorios · F2.3 Adjudicación al 70 % | Entrevistas a Cobranzas y Adjudicación (30 % de abandono, recordatorios 1-10 / 11-20 / 21-30, cuota 7); soluciones aplicadas 1.2 |
| **E3 · Pase validado de Ventas a Fabricación** | F3.1 Revisión de control y resumen de pedido · F3.2 Estados y panel de seguimiento · F3.3 Cambios y agregados | Problema 1 (errores de transmisión); soluciones 1.1, 1.3, 3.1, 3.3; soluciones aplicadas 2.2, 3.1, 3.2, 4.2; límite 2.1 a 2.4 del mandato |
| **E4 · Documentación digital y permisos** | F4.1 Contratos y documentos digitales · F4.2 Usuarios, permisos y reportes | Problema 3 (falta de digitalización); soluciones 2.2, 2.3; entrevista a Administración y Contratos |

## Historias de usuario

| ID | Feature | Historia | MoSCoW | SP | Depende de |
|---|---|---|---|---|---|
| HU-001 | F1.1 | Como **vendedor** quiero registrar un cliente y su proyecto con un ID único para no duplicar datos entre áreas. | Must | 5 | — |
| HU-002 | F1.2 | Como **vendedor** quiero definir si la venta es de contado o financiada y cargar sus condiciones para que se apliquen las reglas de pago correctas. | Must | 5 | 001 |
| HU-003 | F1.2 | Como **vendedor** quiero armar el presupuesto (modelo, m², materiales, transporte, descuentos) para dar un precio único al cliente. | Must | 8 | 001 |
| HU-004 | F1.1 | Como **vendedor** quiero buscar proyectos por ID, cliente o estado para encontrar rápido cualquier pedido. | Should | 3 | 001 |
| HU-005 | F2.1 | Como **administrativo** quiero registrar el pago de una cuota para mantener el plan al día. | Must | 5 | 002 |
| HU-006 | F2.1 | Como **cobranzas** quiero ver el total abonado, saldo y % pagado calculados automáticamente para no hacer cuentas a mano. | Must | 3 | 005 |
| HU-007 | F2.2 | Como **cobranzas** quiero un listado de clientes con cuotas vencidas para contactarlos y evitar que abandonen el plan. | Must | 5 | 005 |
| HU-008 | F2.2 | Como **cobranzas** quiero recordatorios de cuota en las ventanas del 1-10, 11-20 y 21-30 para no enviarlos a mano por WhatsApp. | Should | 8 | 007 |
| HU-009 | F2.3 | Como **responsable de adjudicación** quiero que el sistema marque al cliente habilitado al llegar al 70 % (cuota 7) para adjudicar sin errores. | Must | 5 | 006 |
| HU-010 | F3.1 | Como **administrativo** quiero una revisión de control (pagos confirmados, documentos cargados, campos obligatorios) antes de enviar a Fabricación para que no lleguen pedidos incompletos. | Must | 8 | 005, 013 |
| HU-011 | F3.1 | Como **capataz** quiero recibir el pedido validado con medidas y materiales en un resumen imprimible para fabricar sin consultar por WhatsApp. | Must | 5 | 010 |
| HU-012 | F3.1 | Como **capataz** quiero confirmar el inicio de producción o devolver el pedido a Ventas con una observación para detectar inconsistencias a tiempo. | Must | 5 | 011 |
| HU-013 | F4.1 | Como **administrativo** quiero adjuntar el contrato y comprobantes digitalizados al proyecto para no depender de carpetas físicas. | Must | 5 | 001 |
| HU-014 | F3.2 | Como **usuario de cualquier área** quiero ver el estado de cada pedido (En presupuesto, En fabricación, En entrega, Finalizado) para saber en qué etapa está. | Should | 5 | 010 |
| HU-015 | F3.3 | Como **vendedor** quiero que todo cambio en un proyecto quede en un historial con fecha, área y motivo para saber cuál es la versión válida. | Must | 5 | 001 |
| HU-016 | F3.3 | Como **vendedor** quiero registrar agregados o ampliaciones pedidos por el cliente con su impacto en costo y fecha de entrega. | Should | 5 | 015, 003 |
| HU-017 | F4.2 | Como **dirección** quiero administrar usuarios y permisos por área (Ventas, Administración, Fabricación) para controlar quién edita qué. | Should | 5 | — |
| HU-018 | F4.2 | Como **socio** quiero un reporte de mora, abandono y proyectos por estado para tomar decisiones. | Could | 5 | 007, 014 |
| HU-019 | F1.1 | Como **vendedor** quiero registrar consultas que no compran y su seguimiento para retomarlas más adelante. | Could | 5 | — |
| HU-020 | — | Como **cliente** quiero consultar el estado de mi vivienda online. | Won't (esta etapa) | 8 | 014 |

Total: 20 HU, 108 puntos (100 sin la Won't).

## Candidatas para las 4 HU completas (punto 8) y patrones GoF

| HU | Patrón sugerido | Problema que resuelve |
|---|---|---|
| HU-002 / 005 | Strategy | Reglas distintas de pago: contado (entrega 30-45 días) vs financiado (70 % + pagarés) |
| HU-010 / 014 | State | El pedido cambia de estado con reglas sobre qué transiciones se permiten |
| HU-015 | Memento o Command | Historial de cambios y versiones |
| HU-012 / 008 | Observer | Aviso a Ventas/Cobranzas ante cambios de estado o mora |

Sugerencia: HU-002, HU-010, HU-015 y HU-009 (una por integrante, al menos una usa un patrón).

## Supuestos y huecos a completar

- El trabajo OAS propone planillas en Google Sheets; acá se reencuadra como aplicación web con las mismas reglas y datos (a justificar en el README y en el ADR).
- Mandato original (Ventas ↔ Fabricación) vs. ampliado (suma Administración, Cobranzas, Adjudicación): se toma el ampliado.
- Faltan volúmenes (clientes, proyectos por mes) para los RNF: se van a asumir y declarar.
- No revisé las imágenes del TDC (flujograma, organigrama, planilla): conviene que el equipo confirme que el flujo TO-BE coincide.
