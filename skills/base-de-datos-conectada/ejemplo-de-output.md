# Base · Leads y clientes · Estudio de diseño de interiores · ejemplo con datos ficticios

Herramienta: **Airtable** · Por qué: hay que vincular leads con presupuestos y con pagos; en una planilla suelta eso se copia a mano.

## Qué tiene que poder contestar
- ¿Cuántas consultas entraron esta semana y quién las está siguiendo?
- ¿Qué presupuestos enviados no tienen respuesta hace más de 7 días?
- ¿Qué clientes tienen un pago pendiente?

## Tablas
| Tabla | Una fila = | Se vincula con |
|---|---|---|
| Leads | una consulta de una persona | Equipo, Presupuestos |
| Presupuestos | un presupuesto enviado a un lead | Leads, Pagos |
| Pagos | un pago (o una cuota) de un presupuesto aceptado | Presupuestos |
| Equipo | una persona del equipo, con su rol y si está activa | Leads |

## Campos por tabla

**Leads**
| Campo | Tipo | Para qué |
|---|---|---|
| Nombre | Texto | Identificar al lead |
| WhatsApp | Teléfono | Contactarlo |
| Canal | Selección única (Instagram, Recomendación, Web, Otro) | Saber de dónde vienen |
| Estado | Selección única (Nuevo, Contactado, Presupuestado, Ganado, Perdido) | Ver en qué etapa está |
| Responsable | Vínculo a Equipo | Que nadie quede sin dueño |
| Fecha de entrada | Fecha de creación | Medir cuánto tarda el primer contacto |

**Presupuestos**
| Campo | Tipo | Para qué |
|---|---|---|
| Lead | Vínculo a Leads | No volver a escribir el nombre |
| Monto | Moneda | Saber cuánto se ofreció |
| Fecha de envío | Fecha | Medir días sin respuesta |
| Días sin respuesta | Fórmula (hoy − fecha de envío, si sigue Enviado) | Detectar los que se enfrían |
| Estado | Selección única (Enviado, Aceptado, Rechazado) | Ver qué se cerró |

**Pagos**
| Campo | Tipo | Para qué |
|---|---|---|
| Presupuesto | Vínculo a Presupuestos | Saber de qué trabajo es |
| Monto | Moneda | Cuánto entra |
| Vence | Fecha | Cuándo tiene que entrar |
| Cobrado | Casilla | Separar facturado de cobrado |

## La puerta de entrada
Formulario **"Nueva consulta"**, linkeado en la bio de Instagram y en la web. Campos obligatorios: nombre, WhatsApp, qué necesita, cómo nos conoció. Cada respuesta crea una fila en Leads con Estado = Nuevo. Nadie copia consultas desde el WhatsApp.

## Vistas por rol
| Vista | Filtro | Para quién | Qué mira |
|---|---|---|---|
| Nuevos sin contactar | Estado = Nuevo | Atención al cliente | A quién escribir hoy |
| Presupuestos fríos | Estado = Enviado y Días sin respuesta > 7 | Dirección | A quién hacer seguimiento |
| Pagos pendientes | Cobrado = no, Vence ≤ hoy | Administración | Qué reclamar |

## Cómo armarla (en orden)
1. Crear las 4 tablas vacías.
2. Cargar Equipo con los roles activos.
3. Crear los vínculos entre tablas.
4. Crear los campos simples y después la fórmula.
5. Armar el formulario "Nueva consulta".
6. Cargar 5 leads de prueba (uno sin canal, uno con presupuesto rechazado, uno con pago vencido).
7. Crear las 3 vistas y revisar que cada caso de prueba aparezca donde tiene que aparecer.

## Para confirmar
- [SUPUESTO: entran unas 40 consultas por mes] — confirmarlo con atención al cliente.
- [SUPUESTO: la base se crea en una cuenta del estudio, no en la personal de nadie] — confirmarlo con dirección.
