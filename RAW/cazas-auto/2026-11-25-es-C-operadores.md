# Caza automática — ES · C operadores (cola/agenda vacías → huellas + conteo por page_id) — 2026-11-25

Países: MX, CO, AR, PE, CL, BO, EC, GT, ES. Hoy epoch ≈ 1795610827; corte cohorte 7+ d = creación ≤ 1795006027.

## Shortlist
**Medical System Global (antes «Aula de Enfermería»), page_id 1299254193268099 — PASA (tarjeta).**
- AR: 39 activos (total estimado 39, no truncado), cohorte 7+ = **12/39** (3 de 7,08 d: creados 1794999385/424/442 «500 páginas con esquemas»; 9 de 16 a 64 d, nombre viejo Aula de Enfermería). Sin los 3 límite: 9. MX: 19 activos, cohorte 0. ES: 0.
- ≥ 10 fechas de creación distintas; ads de hoy (operador vivo); ad más viejo 64,6 d (1790031099).
- Oferta por títulos: Vademécum +1.600 fármacos, atlas de farmacología con esquemas 500 págs, 190 ECG reales, 53 capítulos de farmacología, mapas del sistema nervioso, código azul. Producto = PDF/atlas de enfermería. Precio y landing: no visibles por API.
- No es marca personal (marca de producto). Voseo argentino en copy.
- Snapshots: 1856894558846600 (Vademécum), 1613025823430304 (500 páginas), 2190010214931192 (190 ECG), 1121927700467577 (53 capítulos).

## Señales (no pasan)
- Estudiando+ (244436822091978) PE: 56 activos (muestra 50 = piso), cohorte 7+ = 12 en la muestra, pero todos los títulos son «OFERTA SOLO HOY / SOLO 10 SOLES»: oferta no identificable por API → no pasa el gate; abrir snapshot en la PC.
- Doctor PDF (114914206902993) MX: 16 activos, cohorte 7 (fichas visuales enfermería/guardias, MXN) → cerca; re-medir ~12-02.
- Valentina Ríos (1245937505280284): 26 activos, cohorte 3 («+3000 ya lo descargaron»; lead magnet probable).
- Educa Virtual (952043601324431): 27 activos mezcla de packs (mapas fisioterapia, corte láser, collares…); cohorte 2; catálogo-fábrica multi-SKU.
- Fer Rendon (1977647735819349) MX: 116 activos (muestra 50), plantillas Excel costeo menú/finanzas constructoras; ads 3,8 d y <1 d, cohorte 0; re-medir (parece persona).
- Andrea (1514478781740559): 10 ads «7 cuadernillos + 5 plantillas Excel», cohorte 5.
- Megapack Digital (1242267238975066): 13 ads, cohorte 3. Biblioteca Médica Digital (1221024867757656): 9, cohorte 0. Aprendia (1212143988641032) PE: 9, cohorte 1 (calendarios 2027 S/5, bordados). Mundo de Patrones Amigurumi (655883567616410): 9, cohorte 1 (+15.000 patrones $97 MXN / $9.000 COP).
- Mapa Fiscal / Reforma tributaria / Academia Contable: mismo creativo «más de 100 páginas del DOF… o un mapa» (mapas de reforma fiscal 2027), todos <1 d; red de páginas: re-medir en 7 d.
- Salud en un Minuto (1236525139551527): «Guía Completa de Farmacología» 6 ads de <1 d.
- Excluidos ignorados: GeriPlan (adultos mayores), recetas bebé, ministerio juvenil/fe.

## Veredicto provisorio
ENTRAR → llevar «atlas/vademécum de farmacología y ECG de enfermería en PDF» (fuente ES/AR) a **IT, PT, FR, DE**; US/GB solo si existe versión en inglés. Medir primero en esos mercados con page_ids (trampa de la cola: `farmacologia` IT/PT infla el mercado).

## Cobertura
| Keyword | País | ACTIVE | ALL | Qué trajo |
|---|---|---|---|---|
| plantillas excel | bloque ES 9 países | 1103 | — | Fer Rendon, Andrea, Lekton, Cer Solutions; todo <2 d salvo Fer Rendon |
| acceso inmediato PDF | bloque ES | 6019 | — | Educa Virtual, Valentina Ríos, GeriPlan(excl.), Aprendia; churn |
| apuntes enfermería | bloque ES | 212 | — | Medical System Global, Doctor PDF, Estudiando+, Bioma Lívido (100 mapas embriología) |
| mapas mentales | bloque ES | 2802 | — | Mapa Fiscal red, Aprendo Fácil (Chatea), Salud en un Minuto |
| page_ids ×14 | bloque ES / AR / MX / PE / ES | — | — | ver arriba; ALL no corrido (no hubo ceros relevantes salvo MSG-ES = 0 con ACTIVE) |

Trampas nuevas: `apuntes enfermería` sí rinde (212 resultados, nombres útiles); `Chatea con nosotros` (Aprendo Fácil, Camino Interior) = títulos de CTA genéricos sin oferta, no sirven; «OFERTA SOLO HOY» (Estudiando+) oculta la oferta.
Nodos nuevos propuestos: enfermeria-farmacologia-pdf (superficial, ES→EU), mapas-fiscales-mx (virgen).

## Lo que no se pudo verificar
Landing, precio y embudo de MSG (la API no trae URL ni cuerpo del copy); snapshots no abiertos; fecha real de arranque de los 3 ads de 7,08 d (delivery start 6,98 d). Cohorte de Estudiando+ es piso.
