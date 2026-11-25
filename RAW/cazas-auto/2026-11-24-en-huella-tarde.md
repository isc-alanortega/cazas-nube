# Caza automática — EN · huella (cola vacía) — 2026-11-24 (tarde)

Evidencia: API `ads_library_search`, `countries: ["US","GB"]`. Snapshot y embudo NO verificados desde la nube (sin URL de landing en la API). "Hoy" ≈ 2026-11-25 UTC; cohorte 7+ = `ad_creation_time` ≤ hoy−7 d y activo.

## Shortlist
### Equine reproduction — page_id 1393630140502286 — US + GB
- Ads Library US: https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=US&view_all_page_id=1393630140502286&search_type=page&media_type=all
- Ads Library GB: https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=GB&view_all_page_id=1393630140502286&search_type=page&media_type=all
- **Cohorte 7+ / activos: US 28/44 · GB 28/36.** Escalonamiento (días): 7·9·11·13·16·20·25 (tandas de 6·6·2·6·3·4·1). Piso: la API devolvió 44 (<50), no truncado.
- Fechas distintas ≥3 y ≥1 ad creado en los últimos 30 d: pasa filtro de zombi por API.
- Oferta (por títulos): guía/tarjetas para veterinarios de equinos — «34 cards with real scans», «A practical guide for veterinarians», «$23 today (was $85)», «73% off for equine vets». Formato probable PDF/tarjetas digitales (no confirmado).
- Ángulos duplicados: «A practical guide for veterinarians» (×7 en cohorte), «Prostaglandin today? Check this first» (×2), «Is she really open?» (×2), «73% off».
- Snapshots: 2194629271091437, 1452490147061997, 1564906545453637, 1611983786969200, 2591847081288191 (guía, 13-25 d).
- Marca personal: página genérica, sin nombre de persona; algún título en primera persona («The guide I gave a colleague») → juzgar en los creativos desde la PC.
- Score: ① longevidad 45+ d: no (25 d) · ② volumen 50+: no · ③ duplicación 10+: no (7) · ④ hueco: no medido → 0-1/4 (observar con vara de 10 cumplida).
- Embudo/precio: NO verificado desde la nube. Precio dicho en copy: $23 (lista $85).

## Veredicto provisorio
Candidata a modelar. Par fuente → destino: US/GB ya es el mercado; veterinaria de nicho profesional → llevar el molde a DE/FR/IT (verificar hueco con `ALL` en próxima corrida). Nunca DESCARTAR.

## Señales
- Impulso Digital (836616152876180): «500+ Patterns for $16.90» (manualidades) — 8/24 en cohorte, escalonado 7-10 d → casi la vara; re-medir.
- Studio Facile (1272162682644374): 359 ads estimados, 50 vistos TODOS creados <1.5 d → fábrica de churn (guías ilustradas de exámenes), cohorte 0/≥50.
- Linework Books (1381943905010114): 126 ads, 50 vistos todos <1.4 d → churn, cohorte 0/≥50 (libros ilustrados + 2 bonos).
- Bev Jessup (111082667173499, GB, «$11» devocional): ~28 ads creados el mismo minuto hace ~11 h → churn, cohorte 0.
- Julie Harper Bookkeeping (1249670194904132): cohorte 1/16 → tester.
- Social Kit Studio (1438498629338489): 4/7 → tester.
- Base Digital (1276224245563902) «Cake Topper $27»: ads de hoy, sin cohorte medida.
- «Made Four Street Boys My Daddies» (cheat sheet / study guide pdf): short-drama, basura.

## Cobertura
| Keyword | País | ACTIVE | Qué trajo |
|---|---|---|---|
| instant download | US,GB | 27 933 est. | ruido; Studio Facile, Linework, Bev Jessup |
| printable planner | US,GB | 593 | planners; Bev Jessup, Hustle Ledger |
| gumroad | US,GB | 1 194 | ruido |
| digital download | US,GB | 14 658 | Impulso Digital, Base Digital |
| cheat sheet | US,GB | 5 165 | short-drama (trampa) |
| payhip | US,GB | 726 | ruido |
| study guide pdf | US,GB | 511 | Studio Facile, Visual Guide Lab, Learned Visually |
Conteos por page_id: Studio Facile, Julie Harper, Linework, Equine (US, GB), Impulso Digital, Social Kit Studio. No se corrió `ALL` (no hubo ceros).
Trampas nuevas: `cheat sheet` trae short-dramas («Made Four Street Boys My Daddies») → usar entregable + tema.
Nodos nuevos propuestos: veterinaria/equinos (virgen→superficial), manualidades/patrones, estudio-examen-ilustrado (Studio Facile, Visual Guide Lab, Learned Visually, Study Pages Co.).
Huellas corridas: 7 de 8-12 (faltaron `blueprint`, `protocol`, precios `$17/$27/$37`).

## Lo que no se pudo verificar
Landing, precio real, formato (PDF vs tarjetas físicas), marca personal en creativos, zombis por snapshot.
