# Cola de caza — el árbol de nichos

Fuente de trabajo del programa de caza automatizado ([[automatizar-la-caza-de-winners]]). Cada sesión
(EN · EU · BR · ES) elige de acá **qué** cazar y en **qué modo**, y al terminar actualiza su nodo.

> ⛔ **Regla madre: el cero no descarta.** Un nodo pasa a `descartado-eje` solo después de (a) 4-5
> keywords nativas, (b) un nivel de subnichos perforado (modo B) y (c) `ad_active_status: ALL` mirado.
> Antes de eso vuelve como `superficial`. Los 🔴 los pone **el dueño**, nunca una sesión automática.

## Estados

| Estado | Significa | Qué hace la sesión con él |
|---|---|---|
| `virgen` | nunca se barrió | **prioridad 1** — modo A o B |
| `superficial` | se barrió con pocas keywords o un solo mercado | **prioridad 2** — modo B (perforar) |
| `profundo` | 4+ keywords nativas por mercado, subnichos mirados | solo modo C (operadores/agenda) |
| `ENTRAR` | hay molde y destino; el producto está en el catálogo o en camino | modo C: vigilar la ventana |
| `propio` | producto nuestro vivo en el nicho | modo C: vigilar competidores |
| `descartado-eje` | ese eje, en esos mercados, no da infoproducto modelable | no se toca; los hermanos sí |
| `🔴` | descarte permanente del dueño | no se toca |
| `🟡 <fecha>` | revisable en fecha | modo C cuando llega la fecha |

**Orden de elección:** `virgen` más viejo → `superficial` más viejo → `🟡` vencido. Dentro del mismo
estado, primero el nodo cuyo mercado coincide con la sesión. Una sesión no repite un nodo que otra
sesión tocó en los últimos 7 días.

---

## El árbol

Cargá acá tus nichos. Un nodo por nicho o subnicho (`nicho/subnicho`). Las keywords literales viven en
la página del nicho de tu wiki; acá va el conteo y la fecha. La columna Mercados dice a qué sesión
le toca (EN · EU · BR · ES). Si el árbol está vacío, las sesiones arrancan en modo A (huella) y lo van llenando con
los nichos que emergen.

| Nodo | Padre | Mercados | Estado | Cobertura | Próxima acción |
|---|---|---|---|---|---|
| religion | — | todas | 🔴 | — | **EXCLUIDO por el dueño en la instalación: no se busca, no se perfora, no se agrega como hijo** |
| neurokids | — | todas | 🔴 | — | **EXCLUIDO por el dueño en la instalación: no se busca, no se perfora, no se agrega como hijo** |
| recetarios | — | todas | 🔴 | — | **EXCLUIDO por el dueño en la instalación: no se busca, no se perfora, no se agrega como hijo** |
| actividades-para-adultos-mayores | — | todas | 🔴 | — | **EXCLUIDO por el dueño en la instalación: no se busca, no se perfora, no se agrega como hijo** |
| relaciones | — | todas | 🔴 | — | **EXCLUIDO por el dueño en la instalación: no se busca, no se perfora, no se agrega como hijo** |
| kita-actividades | — | EU (+IT/PT/ES) | superficial | 2026-11-25 EU: Rachel Bennett DE cohorte 14 | perforar subnichos (Kita DE, Vorschule, Krippe) y re-medir en 7 días; apareció por huella el 2026-11-25 |
| fichas-visuales-pdf | — | EU (+EN/ES) | superficial | 2026-11-25 EU: Studio Facile PT 16, Bianca FR 15/IT 13 | red de 10+ páginas; medir cohorte vieja de Studio Facile IT (497 ads) y Crearis; perforar por oficio; apareció por huella el 2026-11-25 |
| material-docentes-pdf | — | EU | superficial | 2026-11-25 tarde EU: Emito DE 42/50, EDT Labs FR 18/27, L'Année Prête FR 14/17 (2 tarjetas); IT y PT sin cohorte | re-medir Sara Brooks PT ~2026-12-02; perforar por nivel/asignatura (lengua, ciencias) en FR/DE y verificar landing en PC |
| mapas-mentales-idiomas | — | EU (+PT/BR) | superficial | 2026-11-26 EU: Lingua Chiara IT ≥33/36, DE ≥31/50; Camille Dubois FR ≥46/50 de 268 (tarjeta); 9 clones <3 d en FR/IT/PT; 2026-11-27 EU: Mappe di Fluidità IT 50/66 piso (tarjeta, oferta no legible), Céline Moreau FR 8/34, Mapa do Inglês PT 2/50 | re-medir Céline Moreau ~2026-11-29 y clones ~2026-12-03; medir inglés-para-hispanos y espagnol/francés en PT/DE; verificar landing en PC |
| plantillas-negocio-word-excel | — | EU/EN | superficial | 2026-11-26 tarde EN: 9 keywords + 12 page_ids; Dragon Fire Method = libro de autoayuda, plantillas ≤3 de cohorte (la «23+» eran ads del libro); MAX SHEETS 8/29, Session Ready 0/50+ (<2 d), Contractor Sheet/Sunday Budget/Starr 0 | re-medir MAX SHEETS, Sunday Budget, Session Ready ~2026-12-03; perforar plantillas por oficio (contratistas, guarderías, terapeutas) y moldes DE/FR/IT/PT |
| patrones-crochet-pdf | — | EU | superficial | 2026-11-26 tarde EU: Leah Marlowe DE ≥23/25 (biblioteca patrones PDF); Stitchy DE 17/40, Crochet school DE 10/23 (2 tarjetas); Katie McDow IT 7/39 FR 5/21 | verificar landing en PC (¿PDF o kit?); medir tricot (Strickanleitung PDF, patron tricot, schema maglia, padrão tricô); re-medir Puntada Maestra/Katie McDow ~2026-12-03 |
| haccp-restauracion | — | EU (PT) | virgen | Clear Guides, Makers Bench PT (cohorte 0, lanzamientos) | re-medir en 7 días |
| fichas-ilustradas-oficios-br | — | BR (fuente→EU) | superficial | 2026-11-25 BR: Ideias que Inspiram 8 ads/cohorte 2 (anatomía/impermeabilización/fono), O Eletricista Ilustrado 11 ads de 1 d, Magna Forja, Escala 47; 2026-11-26 tarde BR: ola de ~25 páginas clon <3 d (Guias para Restaurantes 10, Ana Lurdes, Motricidade Orofacial, Mapa Desenhado, Guias Visuais Brasil WA); Vitrine Essencial maçonaria 15/25 (borde religion) | re-medir ~2026-12-03 con page_ids las páginas de la ola (mismo molde «fichas visuales» de EU); apareció por huella el 2026-11-25 |
| planillas-listas-br | — | BR (fuente→EU/EN) | virgen | 2026-11-25 BR: Escala Nova «escala 5x2 R$17,90» 13 ads/cohorte 2; Tera Studio (R$27 planillas, mezcla con servicio web) 12 ads de 1 d; Patrick James 3 ads | re-medir Escala Nova ~2026-12-02 |
| mapas-visuales-concursos-br | — | BR | virgen | 2026-11-25 BR: Escrevente em Mapas, João Silva (+100 mapas guarda municipal), Edital Organizado 9 ads/cohorte 2 (kits R$27-49) | contar con page_ids a los 7 días; apareció por huella el 2026-11-25 |
| kits-profesores-br | material-docentes-pdf | BR (fuente→EU FR/DE) | virgen | 2026-11-25 tarde BR: Explora Ciencias 22/38 (tarjeta); Pequenos Gênios 6/6; Mapas Visuais & ilustrados 6 verificados de 184 | abrir snapshots en la PC; re-medir Mapas Visuais con page_ids ~2026-12-02; apareció por huella |
| mapas-ingles-br | — | BR (fuente→EU) | virgen | 2026-11-25 BR: Mapinhas de Inglês 15 ads, todos <1 d (+500 mapinhas) | re-medir ~2026-12-02 |
| adhd-planners | — | EN | superficial | 2026-11-25 EN tarde: 5 keywords; red física `Brain Dump Planner Pad` (ignorar); EaseUp Planners US 50/50 piso | verificar si EaseUp es digital; re-medir Hustle Ledger/vireondigital ~2026-12-02 |
| fichas-psicopatologia-pdf | fichas-visuales-pdf | EN (fuente→EU) | virgen | 2026-11-25 EN: Zentra Digital US 29/45, GB 25/36 (tarjeta) | verificar landing en PC; buscar clones y copias en DE/FR/IT/PT |
| planes-anuales-docentes-en | material-docentes-pdf | EN (fuente→EU FR/DE) | virgen | 2026-11-26 EN: The Teaching Desk US 12/32 (tarjeta); Download Studio US 7/27 GB 6/21; Social Kit Studio, Sproutpals cohorte 0 | verificar landing en PC; re-medir Download Studio/Sproutpals ~2026-11-30; probar GB; perforar por materia (coro, teatro, idiomas, PE); apareció por huella el 2026-11-26 |
| mapas-visuais-br | fichas-visuales-pdf | BR (fuente→EU) | superficial | 2026-11-26 BR: Mapas Visuais & ilustrados 1316538911539485 ≥29/133 (tarjeta); copy solo «⭐ 9.8/10» | abrir landing en la PC (tema, precio, PDF o no); re-medir ~2026-12-03; buscar clones |
| acuarela-workbook-pdf | — | EN (fuente→EU) | virgen | 2026-11-26 EN: Clara Hayes US 29/32 · GB 24/27 (tarjeta) | verificar en la PC si es marca personal y landing; buscar clones (dibujo botánico, lettering, calligraphy workbook) y moldes DE/FR/IT/PT; apareció por huella el 2026-11-26 |
| enfermeria-farmacologia-pdf | — | ES (fuente→EU) | superficial | 2026-11-25 ES: Medical System Global AR 12/39 (atlas farmacología, ECG); Doctor PDF MX 7 | medir en IT/PT/FR/DE con page_ids; perforar subnichos (ECG, fichas guardias, mapas); apareció por huella el 2026-11-25 |
| mapas-fiscales-mx | — | ES | superficial | 2026-11-25 tarde ES: red «100 páginas del DOF… o un mapa» (3 páginas) cohorte 0 (<2 d; Reforma tributaria ~5 d); Formación Práctica kit contable ≤4 | re-medir red ~2026-12-02; perforar RESICO/nómina/aguinaldo |
| contabilidad-kit-pais-es | mapas-fiscales-mx | ES (fuente→EU) | superficial | 2026-11-25 tarde ES: Ebookify GT 18/23, MX 5/10 (tarjeta); 2026-11-26 tarde ES: Formación Práctica AR ≥12/152 (tarjeta); Magnus 14/30 sin oferta legible; Contabilidad Fácil Colombia cohorte 0 | verificar landings en PC; re-medir Contabilidad Fácil Colombia ~2026-12-03; buscar moldes por país en DE/FR/IT/PT |
| planner-vaciar-cabeza-es | adhd-planners | ES (fuente→EN/EU) | virgen | 2026-11-26 ES: Planner Hoy Solo 3 MX 45/50 piso (tarjeta); Método HACER «$5» y Planner/FIT sin cohorte | verificar landing en PC; re-medir ~2026-12-03; buscar clones (planner TDAH, brain dump PDF) en CO/AR/PE/CL; apareció por huella el 2026-11-26 |
| cuaderno-carrera-app-es | — | ES (fuente→EU) | virgen | 2026-11-26 ES: Cuaderno de Derecho MX 19/50 · AR+CL+ES 22/50 (tarjeta); Página a Página cohorte 0 (36 ads, vence ~11-27); Educa Virtual conocido | verificar si es app o PDF; re-medir Página a Página ~2026-11-27; buscar «cuaderno de» + carrera (medicina, psicología, contabilidad) y moldes IT/PT/FR/DE; apareció por huella el 2026-11-26 |
| notas-clinicas-plantillas-en | plantillas-negocio-word-excel | EN (fuente→EU) | virgen | 2026-11-26 tarde EN: Session Ready US 0/50+ (91 activos, <2 d; kits $9.99 y «5 for $27» PTA/OT/ABA/FNP/psiquiatría/quiropráctica); Clinical Documentation Kit 1 ad | re-medir Session Ready ~2026-12-03; probar GB; moldes DE/FR/IT/PT; apareció por perforar el 2026-11-26 |
| dossier-familia-fr | — | EU (FR) | virgen | 2026-11-27 EU: Atelio Guides FR 23/42, 3 fechas (11-16, 11-19, 11-25); DE/IT/PT 0 | verificar en la PC si es PDF o carnet físico; probar moldes DE/IT/PT («dossier au cas où», documentos para la familia); apareció re-midiendo señal el 2026-11-27 |
| patrones-mascotas-fr | — | EU (FR) | virgen | 2026-11-27 EU: Atelio Guides SKU nuevo «+400 patrons pour chiens et chats» 9 ads del 11-25, cohorte 0 | re-medir ~2026-12-03; ¿PDF de patrones de costura para mascotas?; probar DE/IT/PT |
| guias-visuales-oficios-multi-sku | fichas-psicopatologia-pdf | EN (fuente→EU) | virgen | 2026-11-27 EN: Central Pack US 11/50 piso (Gelato 4, Olive Oil 3, Lubrication 3, Stage Lighting 1); Smart Digital misma red cohorte 0 | verificar landing shopsmartdigital en la PC (precio, PDF vs video); re-medir Central Pack/Smart Digital ~2026-12-02; probar GB propio y moldes DE/FR/IT/PT; apareció perforando el 2026-11-27 |

---

## Trampas de keyword (no se repiten)

Cada sesión la lee antes de generar keywords y **agrega** las que descubre.

| Keyword / patrón | Por qué falla | Qué usar |
|---|---|---|
| `book` `novel` `read` (EN) | short-dramas (cientos de miles de resultados) | entregable + tema |
| `Google Sheets` / `sheets` | short-dramas | pares: `spreadsheet template`, `planilha controle` |
| keywords idénticas en ES/IT/PT (`farmacologia`, `peptide`, `dietoterapia`) | el mercado parece 3-8× más grande | la palabra que **no** se comparte; leer el idioma de cada creativo |
| siglas cortas (`EKG`) | spam de webnovelas | frase de 3+ palabras |
| préstamos del inglés (`barista`, `latte art`, `Meal Prep`) | traen anunciantes de otros países | la palabra nativa |
| keywords amplias en nichos de churn | solo devuelven las últimas 48 h | **angosto para ver la cola** |
| frases largas en `search_terms` | el matcher es **AND por token** | pares de palabras |
| huellas anchas en 🇧🇷 (`acesso imediato`, `apostila`, `kiwify`, precios) | decenas de miles de ads, los 50 primeros son de hoy: sirven para leer nombres de página, no para medir | barrer → anotar ~30 páginas → contar cada una con `page_ids` + `countries`; rinden `guia prático pdf`, `planilha pronta`, `ebook completo`, `material digital` |
| bloque `es` sin BO / EC / GT | subcuenta a los operadores andinos | `countries: ["MX","CO","AR","PE","CL","BO","EC","GT","ES"]` |
| `contabilidad plantillas`, `declaración anual` (MX, nov-2026) | despachos, seguros, academias en vivo y asesorías | `kit contable PDF Excel` y los títulos de ad («70 casos», «una multa del SAT cuesta más que este kit») traen el infoproducto |
| `Chatea con nosotros`, `OFERTA SOLO HOY` (ES, nov-2026) | títulos de CTA sin oferta (Aprendo Fácil, Estudiando+) | leer el nombre de página y abrir snapshot; sí rinde `apuntes enfermería` |
| `te lo envío WhatsApp PDF`, `hotmart acceso inmediato`, `resúmenes flashcards oposiciones PDF` (ES, nov-2026) | 1.526 y 402 resultados de CTA sin oferta, religión/recetas (excluidos) y churn de hoy; la frase larga da 0 (AND por token) | sí rinden `planner imprimible PDF`, `apuntes PDF resúmenes`, `plantillas Excel descarga inmediata` |
| `page_ids` + `ACTIVE` devuelve 0 aunque la keyword ACTIVE lista la página (Leah Marlowe DE, nov-2026) | el filtro por página puede fallar | contar con la keyword ACTIVE y reportar piso; no declarar muerta |
| ids de ad tomados como page_id (huella EU 11-25: Stitchy/Crochet school) | `page_ids` con ad_id devuelve 0 | leer `page_id` del resultado, no `id` |
| `ad_creation_time` viejo sin impresiones | ads zombis | abrir el snapshot: «isn't in the Ad Library / no impressions» no cuenta |
| follow ads («Visit Instagram profile») | infl an la longevidad | la longevidad se lee **sobre el ad que vende** |
| `limit: 50` que devuelve 50 ads de hoy | cohorte truncada | reportar como piso, repetir con `page_ids` + `countries` |
| snapshot sin espera | `get_page_text` devuelve solo el encabezado | `wait` 4 s antes de leer |
| landing de operador 🇧🇷 | geo-redirige por idioma | el precio del mercado cazado se mira desde el checkout |
| página que devuelve **0 con `ALL`** | no está pausada: ya no existe | anotarla como desaparecida |
| `notion template`, `canva templates bundle` (EN, nov-2026) | spam de páginas «Online Store»/«Welcome», revendedores PLR/MRR y Notion OS a $4; nada modelable | no usar; sí `lesson plans pdf`, `worksheets bundle pdf`, `cheat sheets pdf` (rinden Teaching Desk, Clara Hayes, redes de atlas) |
| `ADHD planner` / `ADHD Brain Dump Planner Pad` (EN, nov-2026) | red de >25 páginas clon de dropshipping físico, todo <2 d | usar `ADHD workbook pdf`, `ADHD digital planner` + page_ids; `ADHD printable` desborda a otros nichos (rindió Zentra) |
| `printable planner`, `spreadsheet template`, `digital guide pdf` (EN, nov-2026) | solo devuelven ads de las últimas 24-48 h (Black Friday); Linework Books clona 50+ ads/país en un día | re-medir con `page_ids`+`countries` a los 7 días |
| `digital download pdf` GB (nov-2026) | solo churn <48 h: patrones de crochet PDF y planners ADHD | page_ids + `countries` a los 7 días |
| un whale migra de página sin apagar el negocio | contar solo la página madre lo da por muerto | contar también las páginas hermanas de su ficha |
| precios (`nur 9,99`, `seulement 19,90`, `a soli 9,99`, `apenas 19,90`) y `E-Book` en DE/FR/IT/PT | 100 % retail, Black Friday, novelas | no usar; sí `Planer PDF`, `guide PDF`, `passo dopo passo PDF`, `checklist PDF`, `download imediato` |
| `passo a passo PDF` (PT) y `mini curso` | matchean `passo a passo` suelto: clínicas, stands, dramas, coaches | `download imediato`, `planeador PDF` |
| `digistore24` (DE) | coaches, lead magnets, agencias | no usar |
| copy en otro idioma dentro de un país (Lingua Chiara IT en DE, Dragon Fire EN) | infla el país | leer el idioma de cada título y contar en el país del copy |
| `kit imprimível` (BR, nov-2026) | solo 85 resultados: rinde para ver ads de 5-15 d (no churn) | usar como huella de cola en BR; `checklist pdf`/`download imediato`/`planner pdf` devuelven churn <1 d |
| `mapas visuais ilustrados` (BR, nov-2026) | 720 resultados mezclados con biblias ilustradas, hemodinámica y concursos; ads de hoy | no mide: contar con `page_ids` + `countries` |
| `ebook completo`, `material digital`, `acesso vitalício` (BR, nov-2026) | 5.000-54.000 resultados; los 50 primeros son de las últimas 24 h (Black Friday, Natal) y mezclan receitas, mentores y concursos | barrer para leer nombres de página y contar cada una con `page_ids` + `countries`; en BR la mayoría de las páginas de infoproducto tiene 3-15 ads y <2 d de vida |
| `Unterrichtsmaterial Download`, `programações anuais`, `materiale didattico maestre`, `fichas de trabalho` (nov-2026) | DE devuelve instituciones (Carlsen, Aktion Tagwerk); PT/IT dan 0 o dramas | en FR y DE rinde el título del ad: `cours de maths prêts`, `Mathestunden vorbereitet`, `prête dès lundi` |
| `Mindmaps`/`Lernkarten` DE (nov-2026) | 4 resultados o 0, nada de idiomas | en DE el producto aparece con copy IT/FR; medir con `page_ids`+país |
| `atlas visual`, `fichas visuais pdf`, `guia visual pdf` (BR, nov-2026) | 1.100 / 276 / 638 resultados: ola de clones <3 d, mezcla con Karen Baldin/Carlos Mendoza (clínicos, marca personal) y dropshipping «Últimas Unidades» | leer nombres de página y contar con `page_ids` + `countries`; `pranchas ilustradas` (106) es la que trae ads de 10+ d |
| `Dragon Fire Method` y páginas con libro + plantillas (EN, nov-2026) | los ads del libro de autoayuda inflan la cohorte de la página de plantillas | contar solo los ads de plantillas («300 … templates») |
| `business plan template`, `SOP templates` (EN, nov-2026) | 661 / 86 resultados de servicios, consultores, SaaS y manuales de $2.499 | `excel dashboard template`, `HR templates Word` y `page_ids` |
| `DSM-5 cheat sheets` (EN, nov-2026) | 0 resultados | `psychology study sheets` y `nursing study sheets pdf` sí rinden; `therapy worksheets bundle` trae regalos gratis (Healing with Carol) |
| `anatomy visual guide pdf` (EN, nov-2026) | mezcla de fábricas multi-SKU (Central Pack, Smart Digital, SkillForge, Labdigital) y BR/AED | sirve de huella de fábricas; medir con `page_ids` + `countries` |

## Operadores a seguir (modo C)

Fábricas multi-SKU y whales que muestran el próximo producto antes de que aparezca por keyword. Se
enumeran con `page_ids` + `countries`, siempre con el país. Cadencia: quincenal salvo que diga otra cosa.

| Operador | page_id | País | Por qué se lo sigue |
|---|---|---|---|
| | | | |

## Rotación vigente

| Día | EN | EU | BR | ES |
|---|---|---|---|---|
| Lun | A huella | B perforar | C operadores | A huella |
| Mar | B perforar | C operadores | A huella | B perforar |
| Mié | C operadores | A huella | B perforar | C operadores |
| Jue | A huella | B perforar | C operadores | A huella |
| Vie | B perforar | C operadores | A huella | B perforar |
| Sáb | C agenda | A huella | B perforar | C agenda |
| Dom | lint de la cola | lint de la cola | lint de la cola | lint de la cola |

## Bitácora de la cola

Una línea por sesión, la más nueva arriba. La sesión la escribe **antes** de cazar (con «en curso») y
la completa al terminar.

| Fecha | Sesión | Modo | Nodo | Keywords corridas | Resultado | Nodo queda en |
|---|---|---|---|---|---|---|
| 2026-11-27 mañana | BR | A huella (vie) — en curso | — | — | — | — |
| 2026-11-27 mañana | EU | C operadores (vie; tabla y agenda vacías → re-medición por page_id de señales EU 11-25/26) | — | 10 page_ids (Mapa do Inglês, Céline Moreau, Mappe in inglese, Atril Estudio, Mappe di Fluidità, Puntada Maestra, Katie McDow, Atelio Guides, Impulso Digital, Sara Brooks, Emito) + «Mappe Fluidità» ALL | 2 tarjetas: Atelio Guides FR 23/42 (dossier «au cas où», SKU nuevo mascotas); Mappe di Fluidità IT 50/66 piso (oferta no legible); Céline Moreau FR 8/34 cruza 10 el ~11-28 | nodos nuevos dossier-familia-fr y patrones-mascotas-fr; mapas-mentales-idiomas sigue superficial |
| 2026-11-27 mañana | EN | B perforar (vie; virgen más viejo EN: fichas-psicopatologia-pdf) | fichas-psicopatologia-pdf | 5 keywords EN (psychology study sheets, DSM-5 cheat sheets, therapy worksheets bundle, nursing study sheets pdf, anatomy visual guide pdf) + 5 page_ids (Zentra, Central Pack US/GB, Labdigital, Nursing Cheat Sheets, Smart Digital) | 1 tarjeta: Central Pack US 11/50 piso (fábrica multi-SKU de guías visuales por oficio, 4 SKUs); Zentra re-medido ≥12/69; clones Psyacademy/Nexora | superficial; hijo nuevo guias-visuales-oficios-multi-sku |
| 2026-11-26 tarde | ES | B perforar (todos los nodos ES tocados <7 d; se toma el virgen más viejo: contabilidad-kit-pais-es) | contabilidad-kit-pais-es | 5 consultas nativas (kit contable casos prácticos, contabilidad Excel plantillas casos, combo contable, nómina Excel plantilla, RESICO aguinaldo guía PDF) + page_ids Ebookify, Formación Práctica, Contabilidad Fácil Colombia, Magnus | 1 tarjeta: Formación Práctica AR ≥12/152 (kit/combo contable); Magnus 14/30 oferta no identificable | superficial |
| 2026-11-26 tarde | EN | B perforar (virgen más viejo con mercado EN: plantillas-negocio-word-excel) | plantillas-negocio-word-excel | 9 keywords (excel dashboard template, invoice template bundle, business plan template, HR templates Word, SOP templates, bookkeeping spreadsheet, contract templates freelancers, excel templates bundle small business ALL, clinical note templates therapists) + Dragon Fire + 12 page_ids | 0 tarjetas: Dragon Fire = libro (plantillas ≤3 en cohorte); Session Ready ola <2 d; ninguna página llega a 10 | superficial |
| 2026-11-26 tarde | BR | B perforar (virgen más viejo BR: fichas-ilustradas-oficios-br; ningún nodo BR sin tocar en 7 d, se toma el más viejo) | fichas-ilustradas-oficios-br | 7 keywords nativas (fichas ilustradas, guia visual pdf, pranchas ilustradas, manual ilustrado eletricista, atlas visual, fichas visuais pdf, cola de bolso ilustrada ALL) + 12 page_ids | 0 tarjetas: ola de ~25 páginas clon <3 d; única cohorte: Vitrine Essencial 15/25 (maçonaria, borde de «religion» → señal, no tarjeta) | superficial |
| 2026-11-26 tarde | EU | B perforar (virgen más viejo libre: plantillas lo tocó EN 11-25 → patrones-crochet-pdf) | patrones-crochet-pdf | 5 consultas nativas (Häkelanleitung PDF, Häkelmuster Anleitung Download, schema uncinetto PDF, modèle crochet PDF, receita crochê PDF) + page_ids Stitchy, Crochet school, Leah Marlowe, Katie McDow, Immagina e Crea, Puntada Maestra | 2 tarjetas: Leah Marlowe DE ≥23/25; Stitchy 17/40 + Crochet school 10/23 DE (¿PDF o kit?); resto señales | superficial |
| 2026-11-26 mañana | ES | A huella (jue; cola ES sin nodos libres tocados <7 d) | — | 7 huellas bloque ES (guía PDF acceso inmediato, plantillas Excel descarga inmediata, apuntes PDF resúmenes, hotmart acceso inmediato, planner imprimible PDF, te lo envío WhatsApp PDF, resúmenes flashcards oposiciones PDF) + 9 page_ids | 2 tarjetas: Planner Hoy Solo 3 MX 43/50 piso; Cuaderno de Derecho MX 19/50 · AR+CL+ES 22/50 (formato app, verificar); resto señales | nodos nuevos virgen: planner-vaciar-cabeza-es, cuaderno-carrera-app-es |
| 2026-11-26 mañana | BR | C operadores (jue; tabla y agenda vacías → re-medición de señales BR 11-25 por page_id) | — | 8 page_ids BR + `mapas visuais ilustrados` + Mapinhas ALL | 1 tarjeta: Mapas Visuais & ilustrados BR ≥29/133 (producto no legible); Explora Ciencias 22/38 sin cambio; resto sin cohorte | nodo nuevo mapas-visuais-br |
| 2026-11-26 mañana | EN | A huella (jue) | — | 6 huellas US+GB (worksheets bundle pdf, canva templates bundle, lesson plans pdf, flashcards pdf download, notion template, cheat sheets pdf) + 14 page_ids | 2 tarjetas: The Teaching Desk US 12/32 (planes anuales docentes); Clara Hayes US 29/32 · GB 24/27 (workbook acuarela, verificar marca personal); resto señales | nodos nuevos virgen: planes-anuales-docentes-en, acuarela-workbook-pdf |
| 2026-11-26 mañana | EU | B perforar (jue; virgen más viejo EU: mapas-mentales-idiomas) | mapas-mentales-idiomas | 7 keywords/consultas nativas (mappe mentali inglese/spagnolo, Sprachen Mindmaps, Englisch Lernkarten PDF, cartes mentales anglais/espagnol, mapas mentais inglês/espanhol) + page_ids Lingua Chiara IT/DE, Camille Dubois FR, Céline Moreau FR | 1 tarjeta: Lingua Chiara IT ≥33 + Camille Dubois FR ≥46 (520 mapas inglés 12,90 €); 9 clones <3 d señalados | superficial |
| 2026-11-25 tarde | ES | B perforar (nodo libre: mapas-fiscales-mx, virgen; el resto de nodos ES tocado hoy) | mapas-fiscales-mx | 6 (mapa fiscal, declaración anual, contabilidad plantillas, RESICO guía, kit contable PDF Excel) + page_ids Ebookify, Reforma tributaria, Andrea | 1 tarjeta: Ebookify GT 18/23 · MX 5/10 (kit contable por país); red «mapa DOF» cohorte 0 | superficial; nodo nuevo contabilidad-kit-pais-es |
| 2026-11-25 tarde | BR | A huella (ningún nodo BR libre: todos tocados hoy) | — | 7 huellas (checklist pdf, modelos editáveis, kit imprimível, download imediato, pronto para imprimir, planner pdf, Aula da Saudade) + 9 page_ids | 1 tarjeta: Explora Ciencias BR 22/38 (kits profes); señal Mapas Visuais (cohorte inferida) | nodo nuevo virgen: kits-profesores-br |
| 2026-11-25 tarde | EU | B perforar | material-docentes-pdf | ~12 keywords nativas DE/FR/IT/PT (Unterrichtsmaterial Download, Arbeitsblätter Grundschule PDF, Lehrer Vorlagen, fiches pédagogiques, Maths Prêtes, materiale didattico maestre, schede didattiche PDF, programações anuais, fichas de trabalho, planificações professores) + page_ids Emito, EDT Labs, L'Année Prête, Belle Plume, Marie Bernard, Tiny Makers, Impulso Digital | 2 tarjetas: Emito DE 42/50 + EDT Labs FR 18/27 (molde «cours de maths prêts»); L'Année Prête FR 14/17. IT y PT sin cohorte (0 ads) | material-docentes-pdf: profundo en DE/FR, superficial en IT/PT |
| 2026-11-25 tarde | EN | B perforar (ningún nodo EN libre → se abrió `adhd-planners`, virgen de la mañana EN) | adhd-planners | 5 keywords (ADHD planner US/GB, workbook pdf, printable, digital planner, template notion) + 5 page_ids | 1 tarjeta: Zentra Digital US 29/45 · GB 25/36 (210 fichas psicopatología); señal EaseUp Planners (US 50/50 piso, tipo no verificado) | adhd-planners superficial; nodo nuevo fichas-psicopatologia-pdf |
| 2026-11-25 mañana | ES | C operadores (tabla y agenda vacías → huellas ES + conteo por page_id) | — | 4 huellas (plantillas excel, acceso inmediato PDF, apuntes enfermería, mapas mentales) + 17 page_ids | 1 tarjeta: Medical System Global AR cohorte 12/39 (atlas farmacología enfermería); resto señales | nodo nuevo superficial |
| 2026-11-25 mañana | BR | A huella (mié = B perforar, pero la cola no tenía nodos BR → cola vacía para BR) | — | 6 huellas BR (guia prático pdf, planilha pronta, mapas mentais, ebook completo, material digital, acesso vitalício) + 11 page_ids | 0 tarjetas: ninguna página llega a cohorte 10 (todo <2 d; mejores: Escala Nova 13 ads/2 cohorte, Edital Organizado 9/2) | 4 nodos nuevos `virgen` |
| 2026-11-25 mañana | EN | C operadores (tabla y agenda vacías → re-medición de señales 11-24 + huellas nuevas) | — | page_ids Excelbychris, Bev Jessup, Alisson Drusk, Portal da Pedagogia + `digital download pdf` GB | 1 tarjeta: Excelbychris US (32/50 cohorte 7+); resto señales | nodos nuevos `virgen`: crochet-patrones-pdf, adhd-planners; plantillas-excel con candidato |
| 2026-11-25 mañana | EU | A huella (cola vacía) | — | 10 huellas × DE/FR/IT/PT (PDF Anleitung, Download sofort, E-Book, Vorlage Download, Planer PDF, Checkliste PDF, Mini-Kurs, guide PDF, passo dopo passo PDF, download imediato, precios 9,99/19,90…) + 4 barridos por país + 60 conteos por page_id | 2 tarjetas: Rachel Bennett (Kita 5 €) y red de fichas visuales PDF (Studio Facile PT, Bianca FR/IT); señal fuerte Emito DE | nodos nuevos `virgen`/`superficial` abajo |
| 2026-11-24 tarde | EN | A huella (cola vacía) | — | 11 huellas × US+GB (printable planner, instant/digital download, gumroad, payhip, cheat sheet, study guide, spreadsheet template, digital guide pdf, $9.99, $17, blueprint protocol) | 0 tarjetas; todo churn de <48 h salvo Bev Jessup (workshop gratis) | nodos nuevos `virgen`: plantillas-excel, planner-cristiano, guias-oficios-bonus |
| | | | | | | |
