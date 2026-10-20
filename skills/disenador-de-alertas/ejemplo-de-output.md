# Alerta · Lead sin contactar a las 24 h · ejemplo con datos ficticios

**En una frase:** Cuando un lead nuevo pasa 24 horas en Estado = Nuevo en la base de Airtable, le llega a Atención al cliente por mail un aviso con el nombre y el WhatsApp del lead, para que lo contacte ese mismo día.

**Herramienta:** automatización nativa de Airtable · **Por qué:** el dato ya vive en la base y el aviso va al equipo; no hace falta sumar otra herramienta.

**Dueño:** Atención al cliente · **Ahorro estimado:** ~2 h por semana de revisar la planilla a mano, y evita perder leads que se enfrían (hoy se pierden 3 o 4 por mes, según el negocio del ejemplo).

## Disparador
Un registro entra en la vista **"Alerta · Nuevos +24 h"** de la tabla Leads.
Filtro de la vista: Estado = Nuevo · Fecha de entrada hace más de 24 h · Alerta enviada = no.

## Qué hace, paso a paso
1. Airtable detecta que el lead entró en la vista.
2. Manda un mail a la casilla del rol Atención al cliente.
3. Marca la casilla **Alerta enviada** en ese lead.

## El mensaje (listo para copiar)
> Asunto: Lead sin contactar hace más de 24 h · {Nombre}
>
> {Nombre} escribió el {Fecha de entrada} por {Canal} y todavía no tiene respuesta.
> WhatsApp: {WhatsApp}
> Qué hacer: escribile hoy y pasá el Estado a "Contactado".

## Para que no se repita
La casilla **Alerta enviada** saca al lead de la vista: el aviso sale una sola vez por lead.

## Si algo falla
- Si el lead no tiene WhatsApp cargado, el mail sale igual con "sin teléfono" y el paso es pedirlo por el canal por donde entró.
- Si la automatización se apaga sola o da error, el aviso de falla le llega a quien la activó: tiene que ser una cuenta del negocio.

## Cómo probarla
| Caso | Qué cargás | Qué tiene que pasar |
|---|---|---|
| Normal | Lead de prueba con fecha de entrada de ayer | Llega 1 mail y se marca Alerta enviada |
| Raro 1 | Lead de prueba ya en Contactado | No llega nada |
| Raro 2 | Lead de prueba sin WhatsApp | Llega el mail con "sin teléfono" |

Todos los mails de prueba van a una casilla propia, nunca a clientes.

## Cómo apagarla
Desactivar la automatización en Airtable. Mientras está apagada, Atención al cliente revisa la vista "Alerta · Nuevos +24 h" todos los días a las 10.

## Para confirmar
- [SUPUESTO: el equipo mira el mail del negocio todos los días] — si el canal real es WhatsApp, el mail se reemplaza por un mensaje listo para copiar con link de WhatsApp.
- [SUPUESTO: entran unos 60 leads por mes] — confirmar que entra en las corridas del plan de Airtable.
