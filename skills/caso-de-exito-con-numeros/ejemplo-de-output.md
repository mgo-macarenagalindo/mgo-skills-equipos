# Caso · De 6 horas por semana persiguiendo cobros a una vista que se revisa en 15 minutos · ejemplo con datos ficticios

**Contexto:** una academia online de idiomas con 4 personas en el equipo · **Mi rol:** asistente de operaciones · **Origen:** empleador, anonimizado

## Antes
Los pagos en cuotas se anotaban en una planilla con una columna por mes. Para saber quién debía, la administración revisaba fila por fila y cruzaba con el banco: **unas 6 horas por semana** (3 revisiones de 2 horas). Los atrasos se descubrían a fin de mes.

## Qué cambié
- Diseñé una base con una fila por cuota, en vez de una columna por mes.
- Armé un formulario para cargar cada pago apenas entra.
- Creé una vista "Vencidas" con filtro por fecha y estado.
- Documenté el procedimiento de seguimiento de cobros, con un responsable por paso.

## Después
La administración revisa la vista "Vencidas" una vez por día: **unos 15 minutos**. Los atrasos se ven el mismo día que vencen, no a fin de mes.
[ESTIMADO: el ahorro de ~5 h por semana sale de comparar dos semanas antes y dos después; medirlo un mes completo para confirmarlo.]

## Cómo lo cuento (en una frase)
"Pasé el seguimiento de cobros de una planilla que se revisaba a mano 6 horas por semana a una vista que muestra los atrasos el día que vencen."

## Versión corta para LinkedIn o propuesta
> En una academia online, los atrasos de pago aparecían a fin de mes y revisarlos llevaba 6 h por semana.
> Rediseñé la base (una fila por cuota), sumé un formulario de carga y una vista de vencidas.
> Hoy se revisa en 15 minutos por día y los atrasos se ven el mismo día.

## Para confirmar
- [ESTIMADO] Ahorro de horas: medirlo un mes completo.
- Pedir permiso a dirección antes de nombrar la academia; mientras tanto, va anonimizada.
