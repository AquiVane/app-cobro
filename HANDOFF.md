# HANDOFF — app-cobro (App de Cobro)

*Creado: 11/10/2026.*

## Qué es
App independiente para emprendedores (ej. dueño/a de una estética): recordatorios automáticos de pago por mail a sus clientes, más ficha de cada cliente (nombre, apellido, mail, teléfono, cumpleaños, plan elegido, fecha de pago, tratamientos y consultas) y mail de cumpleaños para fidelizar. El cobro es la venta principal; la ficha es el valor extra. También se ofrece como función dentro del Hub para los clientes de COSMART (misma lógica, reusada).

## Estado
Repo recién creado, vacío de código. Decisiones tomadas en la sesión "Aplicaciones sin hacer para vender" (11/10):
- Validado en investigación: el mercado de recordatorios de cobro ya tiene competidores (Wati, Leadsales, YoFacturo); el hueco es precio bajo, simpleza y español local.
- Datos en D1 (gratis). Mails por Brevo gratis (tope diario a confirmar).
- Los recordatorios cuelgan del cron diario existente de marketing-hub; no crear crons nuevos.

## Pendiente real
1. Landing en preview artifact (aprobación de Vaneh).
2. Login propio + ficha de clientes + recordatorios por mail.
3. Pago de la suscripción (mensual/anual) — definir medio sin costo fijo.
4. Prueba gratis con clientes actuales de COSMART.

## Reglas duras
- Vaneh se comunica **solo en español** (rioplatense) — nunca respondas en inglés.
- **Nunca hagas cambios no pedidos.** Si algo parece mejorable, preguntá antes.
- **Solo servicios GRATUITOS.** Nada con costo fijo para COSMART (decisión de Vaneh, 11/10). Antes de usar cualquier servicio externo, verificar que sea gratis y avisar si tiene un límite que pueda empezar a cobrar. Sin tarjetas ni planes pagos hasta que haya ingresos y ella lo autorice.
- **Cada app es independiente**: propia landing, propio login, propios usuarios y contraseñas. Quien compra una NO accede al Hub ni a las otras apps.
- **Sin WhatsApp** por ahora (decisión de Vaneh): los avisos van por mail.
- **Texto primero**: todo texto que haya que escribir (mails, copys, explicaciones) se muestra en el chat y se espera aprobación antes de seguir.
- **Landings / páginas nuevas**: primero preview en artifact para que Vaneh corrija ahí mismo. Responsive mobile primero. Texto claro sobre fondos oscuros. Revisar que todos los botones funcionen.
- **Branding COSMART** (para el uso interno y los clientes de COSMART): brújula/viajeros/destinos; Playfair Display + DM Sans; colores `#0D2B6B` `#1A4DAA` `#3A8FC7` `#E02020` `#F2EDE6`. Ver `cosmart-workers/clientes/cosmart/AI_OPERATING_SYSTEM.md`. Para el resto de los clientes de las apps, textos neutros.
- **Cron triggers de Cloudflare: la cuenta está al tope (5/5, Workers Free).** No agregar crons nuevos; reusar uno existente de `cosmart-workers` o consultar a Vaneh. Deploy de workers siempre MANUAL y avisando antes.
- **Rendimiento (que no se rompa al crecer)**: datos en filas chicas e indexadas (D1), nunca bloques JSON gigantes; listas paginadas; carga por partes; envíos de mail en cola con tope diario; topes de clientes por plan; prueba de carga antes de lanzar; medir velocidad antes de sumar funciones.
- **Precios de lanzamiento**: Inicial USD 3/mes (hasta 20 clientes) · Plus USD 5/mes (hasta 50) · Pro USD 8/mes (hasta 150). Anual: pagás 10 meses, usás 12 (USD 30 / 50 / 80). Los 2 meses gratis aplican SOLO al plan anual pagado por adelantado; NO hay meses gratis al inicio. Prueba gratis solo para clientes actuales de COSMART.
