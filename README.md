# Meridiano – versión funcional (servidor Python + base de datos)

Guías de viaje por Europa para público latino. Los datos se guardan de verdad en una base SQLite
(`meridiano.db`, se crea sola la primera vez). Solo necesitas Python 3, sin instalar nada más.

## Cómo iniciarla
- **Windows:** doble clic en `iniciar.bat`
- **Mac / Linux:** `./iniciar.sh` (o `python3 server.py`)

Luego abre http://localhost:5002 en el navegador. Para cerrar: Ctrl + C.

## Panel CMS
Entra a la pestaña "Panel CMS". Clave por defecto: `meridiano2026`.
Para cambiarla: `MERIDIANO_PASS=tuclave python3 server.py`
(en Windows: `set MERIDIANO_PASS=tuclave` y luego `python server.py`).

## Qué funciona de verdad
- Destinos, precios y guías guardados en la base de datos; el CMS agrega y elimina destinos.
- Fotos de la comunidad: quedan pendientes y solo se publican cuando el administrador las aprueba.
- Pedidos: cada compra queda registrada y desbloquea la guía para ese dispositivo.
- Login de administrador con sesión: sin sesión nadie puede editar ni moderar.

## Qué sigue siendo simulado
- El pago no se conecta a ninguna pasarela (falta integrar Stripe, Mercado Pago o Przelewy24).
- Los tipos de cambio son fijos y aproximados.
- Cada cliente se identifica por su navegador, sin cuentas de usuario.
- No incluye HTTPS: para publicarlo en internet, ponlo detrás de un proxy con HTTPS (Caddy, Nginx)
  o en un hosting con Python.

## Archivos
`server.py` (servidor y API) · `index.html` (la app) · `seed.json` (datos iniciales) ·
`sw.js` y `manifest.webmanifest` (PWA) · iconos · `iniciar.bat` / `iniciar.sh`

Si abres `index.html` con doble clic, sin servidor, funciona como demo local (datos en el navegador).
