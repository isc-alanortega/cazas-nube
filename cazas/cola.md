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
| mapas-mentales-idiomas | — | EU | virgen | 2026-11-25 EU: Lingua Chiara 32/103 (copy IT en DE) | medir en IT con page_ids; apareció por huella el 2026-11-25 |
| plantillas-negocio-word-excel | — | EU/EN | virgen | Dragon Fire Method cohorte 23+ (copy EN) | verificar si el producto es real o marca genérica |
| patrones-crochet-pdf | — | EU | virgen | Stitchy 17/31, Crochet school 10/20 DE | abrir snapshot: ¿PDF o kit? |
| haccp-restauracion | — | EU (PT) | virgen | Clear Guides, Makers Bench PT (cohorte 0, lanzamientos) | re-medir en 7 días |
| fichas-ilustradas-oficios-br | — | BR (fuente→EU) | virgen | 2026-11-25 BR: Ideias que Inspiram 8 ads/cohorte 2 (anatomía/impermeabilización/fono), O Eletricista Ilustrado 11 ads de 1 d, Magna Forja, Escala 47 | re-medir en 7 días (mismo molde «fichas visuales» de EU); apareció por huella el 2026-11-25 |
| planillas-listas-br | — | BR (fuente→EU/EN) | virgen | 2026-11-25 BR: Escala Nova «escala 5x2 R$17,90» 13 ads/cohorte 2; Tera Studio (R$27 planillas, mezcla con servicio web) 12 ads de 1 d; Patrick James 3 ads | re-medir Escala Nova ~2026-12-02 |
| mapas-visuales-concursos-br | — | BR | virgen | 2026-11-25 BR: Escrevente em Mapas, João Silva (+100 mapas guarda municipal), Edital Organizado 9 ads/cohorte 2 (kits R$27-49) | contar con page_ids a los 7 días; apareció por huella el 2026-11-25 |
| kits-profesores-br | material-docentes-pdf | BR (fuente→EU FR/DE) | virgen | 2026-11-25 tarde BR: Explora Ciencias 22/38 (tarjeta); Pequenos Gênios 6/6; Mapas Visuais & ilustrados 6 verificados de 184 | abrir snapshots en la PC; re-medir Mapas Visuais con page_ids ~2026-12-02; apareció por huella |
| mapas-ingles-br | — | BR (fuente→EU) | virgen | 2026-11-25 BR: Mapinhas de Inglês 15 ads, todos <1 d (+500 mapinhas) | re-medir ~2026-12-02 |
| adhd-planners | — | EN | superficial | 2026-11-25 EN tarde: 5 keywords; red física `Brain Dump Planner Pad` (ignorar); EaseUp Planners US 50/50 piso | verificar si EaseUp es digital; re-medir Hustle Ledger/vireondigital ~2026-12-02 |
| fichas-psicopatologia-pdf | fichas-visuales-pdf | EN (fuente→EU) | virgen | 2026-11-25 EN: Zentra Digital US 29/45, GB 25/36 (tarjeta) | verificar landing en PC; buscar clones y copias en DE/FR/IT/PT |
| enfermeria-farmacologia-pdf | — | ES (fuente→EU) | superficial | 2026-11-25 ES: Medical System Global AR 12/39 (atlas farmacología, ECG); Doctor PDF MX 7 | medir en IT/PT/FR/DE con page_ids; perforar subnichos (ECG, fichas guardias, mapas); apareció por huella el 2026-11-25 |
| mapas-fiscales-mx | — | ES | superficial | 2026-11-25 tarde ES: red «100 páginas del DOF… o un mapa» (3 páginas) cohorte 0 (<2 d; Reforma tributaria ~5 d); Formación Práctica kit contable ≤4 | re-medir red ~2026-12-02; perforar RESICO/nómina/aguinaldo |
| contabilidad-kit-pais-es | mapas-fiscales-mx | ES (fuente→EU) | virgen | 2026-11-25 tarde ES: Ebookify GT 18/23, MX 5/10 (tarjeta); 70 casos PDF+Excel por país | verificar landing en PC; buscar clones en CO/AR/PE/CL y moldes por país en DE/FR/IT/PT |

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
| `ad_creation_time` viejo sin impresiones | ads zombis | abrir el snapshot: «isn't in the Ad Library / no impressions» no cuenta |
| follow ads («Visit Instagram profile») | infl an la longevidad | la longevidad se lee **sobre el ad que vende** |
| `limit: 50` que devuelve 50 ads de hoy | cohorte truncada | reportar como piso, repetir con `page_ids` + `countries` |
| snapshot sin espera | `get_page_text` devuelve solo el encabezado | `wait` 4 s antes de leer |
| landing de operador 🇧🇷 | geo-redirige por idioma | el precio del mercado cazado se mira desde el checkout |
| página que devuelve **0 con `ALL`** | no está pausada: ya no existe | anotarla como desaparecida |
| `ADHD planner` / `ADHD Brain Dump Planner Pad` (EN, nov-2026) | red de >25 páginas clon de dropshipping físico, todo <2 d | usar `ADHD workbook pdf`, `ADHD digital planner` + page_ids; `ADHD printable` desborda a otros nichos (rindió Zentra) |
| `printable planner`, `spreadsheet template`, `digital guide pdf` (EN, nov-2026) | solo devuelven ads de las últimas 24-48 h (Black Friday); Linework Books clona 50+ ads/país en un día | re-medir con `page_ids`+`countries` a los 7 días |
| `digital download pdf` GB (nov-2026) | solo churn <48 h: patrones de crochet PDF y planners ADHD | page_ids + `countries` a los 7 días |
| un whale migra de página sin apagar el negocio | contar solo la página madre lo da por muerto | contar también las páginas hermanas de su ficha |
| precios (`nur 9,99`, `seulement 19,90`, `a soli 9,99`, `apenas 19,90`) y `E-Book` en DE/FR/IT/PT | 100 % retail, Black Friday, novelas | no usar; sí `Planer PDF`, `guide PDF`, `passo dopo passo PDF`, `checklist PDF`, `download imediato` |
| `passo a passo PDF` (PT) y `mini curso` | matchean `passo a passo` suelto: clínicas, stands, dramas, coaches | `download imediato`, `planeador PDF` |
| `digistore24` (DE) | coaches, lead magnets, agencias | no usar |
| copy en otro idioma dentro de un país (Lingua Chiara IT en DE, Dragon Fire EN) | infla el país | leer el idioma de cada título y contar en el país del copy |
| `kit imprimível` (BR, nov-2026) | solo 85 resultados: rinde para ver ads de 5-15 d (no churn) | usar como huella de cola en BR; `checklist pdf`/`download imediato`/`planner pdf` devuelven churn <1 d |
| `ebook completo`, `material digital`, `acesso vitalício` (BR, nov-2026) | 5.000-54.000 resultados; los 50 primeros son de las últimas 24 h (Black Friday, Natal) y mezclan receitas, mentores y concursos | barrer para leer nombres de página y contar cada una con `page_ids` + `countries`; en BR la mayoría de las páginas de infoproducto tiene 3-15 ads y <2 d de vida |
| `Unterrichtsmaterial Download`, `programações anuais`, `materiale didattico maestre`, `fichas de trabalho` (nov-2026) | DE devuelve instituciones (Carlsen, Aktion Tagwerk); PT/IT dan 0 o dramas | en FR y DE rinde el título del ad: `cours de maths prêts`, `Mathestunden vorbereitet`, `prête dès lundi` |

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
