# Caza EN · 2026-11-28 (sábado, mañana) · modo C agenda

**Modo:** C agenda (sáb). La agenda de `cazas/cazas.md` y la tabla «Operadores a seguir» estaban vacías → re-medición por `page_id` de las señales EN de los días anteriores. Fecha/hora: 2026-11-28 06:33 America/Mexico_City (epoch ~1795869230; vara 7 d = creados antes de 1795264430).

## Mediciones

| Operador | page_id | País | Activos | Cohorte 7+ | Lectura |
|---|---|---|---|---|---|
| MAX SHEETS | 180395578482259 | US | 13 | **12/13** | tandas de ~11-02, 11-09, 11-14, 11-23, 11-27; ads nuevos <1 d |
| MAX SHEETS | 180395578482259 | GB | 25 | **≈18/25** | (excluido un ad dinámico `{{product.name}}` de 2024) |
| Fenix Library | 1455853117614278 | US | 252 | 0/50 (piso) | el más viejo ~1.3 d (2026-11-27 04:09 UTC) |
| The Dailee | 237698842762300 | US | 168 | ≥47/50 (piso) | planners; físico vs digital sin verificar |
| Excel Sheets Pro | 948639911672809 | US/GB | 18 | 0 | creados 11-26/27 |

Búsquedas de huella: `Download Studio` (US, ruido), `EaseUp Planners` (US, ruido de novelas), `Excel project tracker templates` (US, 3 resultados: Excel Sheets Pro, The Dailee).

## Decisiones
- **Tarjeta:** MAX SHEETS (US+GB). Pasa vara (cohorte ≥10), no es marca personal, no está en `descartados.md`, no tiene ficha. Zombis: ≥3 fechas de creación distintas y ≥1 ad en los últimos 30 d. Embudo no verificado (el API no trae URL).
- **Señal, no tarjeta:** The Dailee (marca con producto físico probable; thedailee.com no resolvió desde la nube, WebFetch bloqueado por red). Excel Sheets Pro y Fenix Library, cohorte 0.
- Nota: la medición del 11-26 (8/29) subestimaba; hoy con `page_ids` + `ACTIVE` y por país sale 12/13 US y ≈18/25 GB.

## Cobertura
7 consultas a la API (4 con `page_ids`, 3 por keyword) en US y GB. Nodo tocado: `plantillas-negocio-word-excel`. Sin conflictos de git. Pendiente en la PC: landing de MAX SHEETS y The Dailee.
