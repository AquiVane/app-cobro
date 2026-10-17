# Instrucciones para Claude Code en este repo

Este repo (`AquiVane/app-cobro`): App independiente para emprendedores (ej. dueño/a de una estética): recordatorios automáticos de pago por mail a sus clientes, más ficha de cada cliente (nombre, apellido, mail, teléfono, cumpleaños, plan elegido, fecha de pago, tratamientos y consultas) y mail de cumpleaños para fidelizar. El cobro es la venta principal; la ficha es el valor extra. También se ofrece como función dentro del Hub para los clientes de COSMART (misma lógica, reusada).. Trabajás para Vaneh (COSMART).

## Al empezar cualquier sesión
Leé **`HANDOFF.md`** y **`AI_OPERATING_SYSTEM.md`** (raíz) antes de tocar código o escribir cualquier texto. Mantenelo al día vos mismo al terminar cada sesión.

## Marca propia: AI Operating System (regla de Vaneh, 17/10/2026)
Toda app, ebook o recurso nuevo que NO sea de COSMART y tenga branding propio debe tener su propio AI Operating System, armado con la misma estructura del de COSMART pero con contenido propio de esa marca. Antes de escribir o diseñar cualquier cosa para esa marca (textos, mails, landings, anuncios, diseño), leé su Operating System. Nunca se mezcla con el de COSMART ni con el de otra marca.
- Este repo guarda una copia de `AI_OPERATING_SYSTEM.md` (marca **Al Día**). El maestro está en `AquiVane/cosmart-workers` → `clientes/al-dia/` (privado).
- Cuando el maestro cambie, actualizar esta copia.

## Reglas duras
- Vaneh se comunica **solo en español** (rioplatense) — nunca respondas en inglés.
- **Nunca hagas cambios no pedidos.** Si algo parece mejorable, preguntá antes.
- **Solo servicios GRATUITOS.** Nada con costo fijo para COSMART (decisión de Vaneh, 11/10). Antes de usar cualquier servicio externo, verificar que sea gratis y avisar si tiene un límite que pueda empezar a cobrar. Sin tarjetas ni planes pagos hasta que haya ingresos y ella lo autorice.
- **Cada app es independiente**: propia landing, propio login, propios usuarios y contraseñas. Quien compra una NO accede al Hub ni a las otras apps.
- **Sin WhatsApp** por ahora (decisión de Vaneh): los avisos van por mail.
- **Texto primero**: todo texto que haya que escribir (mails, copys, explicaciones) se muestra en el chat y se espera aprobación antes de seguir.
- **Landings / páginas nuevas**: primero preview en artifact para que Vaneh corrija ahí mismo. Responsive mobile primero. Texto claro sobre fondos oscuros. Revisar que todos los botones funcionen.
- **Identidad: Al Día** (NO COSMART). Se rige por `AI_OPERATING_SYSTEM.md` de este repo: tipografías Gabarito + Figtree, terracota #B4452A, mostaza #E2A33A, tinta #2A1E18, crema #FAF6F0. Sitio: apps.vamatienda.com.ar.
- **Cron triggers de Cloudflare: la cuenta está al tope (5/5, Workers Free).** No agregar crons nuevos; reusar uno existente de `cosmart-workers` o consultar a Vaneh. Deploy de workers siempre MANUAL y avisando antes.
- **Rendimiento (que no se rompa al crecer)**: datos en filas chicas e indexadas (D1), nunca bloques JSON gigantes; listas paginadas; carga por partes; envíos de mail en cola con tope diario; topes de clientes por plan; prueba de carga antes de lanzar; medir velocidad antes de sumar funciones.
- **Precios de lanzamiento**: Inicial USD 3/mes (hasta 20 clientes) · Plus USD 5/mes (hasta 50) · Pro USD 8/mes (hasta 150). Anual: pagás 10 meses, usás 12 (USD 30 / 50 / 80). Los 2 meses gratis aplican SOLO al plan anual pagado por adelantado; NO hay meses gratis al inicio. Prueba gratis solo para clientes actuales de COSMART.
