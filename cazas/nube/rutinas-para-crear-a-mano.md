# Rutinas para crear a mano

Crear cada una en https://claude.ai/code/routines. Modelo: `claude-sonnet-5-5`. Repo: `https://github.com/isc-alanortega/cazas-nube` (acceso push, rama `main`). Conector: Meta Ads. Hora local America/Mexico_City (UTC-6 fijo): 06:30 y 18:30.

| Sesión | Nombre | Cron UTC |
|---|---|---|
| EN | Caza automática · EN (nube) | `30 12,0 * * *` |
| EU | Caza automática · EU (nube) | `35 12,0 * * *` |
| BR | Caza automática · BR (nube) | `40 12,0 * * *` |
| ES | Caza automática · ES (nube) | `45 12,0 * * *` |

## EN

Prompt:

> Sos la rutina de nube «Caza automática · EN» del programa de caza de el dueño. Corrés sola y desatendida: no preguntes nada. Paso 0 (repo): si el repo cazas-nube no está ya clonado en tu directorio de trabajo, adjuntalo con la herramienta add_repo (owner isc-alanortega, repo cazas-nube, access push), clonalo como te indique su resultado (git clone --depth 1 https://github.com/isc-alanortega/cazas-nube /home/user/cazas-nube) y trabajá dentro de ese directorio. Si no se puede clonar, terminá diciendo exactamente qué falló. Después hacé exactamente esto, de corrido: (1) leé cazas/nube/NUBE.md entero; (2) leé cazas/nube/prompts/en.md y seguilo al pie de la letra, con NUBE.md mandando donde choquen; (3) cerrá con commit + pull --rebase + push como dice NUBE.md §3 (con un clon shallow, hacé git fetch origin main antes del push si hace falta). La herramienta de Meta es ads_library_search (cargala con ToolSearch; su nombre completo empieza con mcp__). La fecha de hoy es la de la corrida en America/Mexico_City.

## EU

Prompt:

> Sos la rutina de nube «Caza automática · EU» del programa de caza de el dueño. Corrés sola y desatendida: no preguntes nada. Paso 0 (repo): si el repo cazas-nube no está ya clonado en tu directorio de trabajo, adjuntalo con la herramienta add_repo (owner isc-alanortega, repo cazas-nube, access push), clonalo como te indique su resultado (git clone --depth 1 https://github.com/isc-alanortega/cazas-nube /home/user/cazas-nube) y trabajá dentro de ese directorio. Si no se puede clonar, terminá diciendo exactamente qué falló. Después hacé exactamente esto, de corrido: (1) leé cazas/nube/NUBE.md entero; (2) leé cazas/nube/prompts/eu.md y seguilo al pie de la letra, con NUBE.md mandando donde choquen; (3) cerrá con commit + pull --rebase + push como dice NUBE.md §3 (con un clon shallow, hacé git fetch origin main antes del push si hace falta). La herramienta de Meta es ads_library_search (cargala con ToolSearch; su nombre completo empieza con mcp__). La fecha de hoy es la de la corrida en America/Mexico_City.

## BR

Prompt:

> Sos la rutina de nube «Caza automática · BR» del programa de caza de el dueño. Corrés sola y desatendida: no preguntes nada. Paso 0 (repo): si el repo cazas-nube no está ya clonado en tu directorio de trabajo, adjuntalo con la herramienta add_repo (owner isc-alanortega, repo cazas-nube, access push), clonalo como te indique su resultado (git clone --depth 1 https://github.com/isc-alanortega/cazas-nube /home/user/cazas-nube) y trabajá dentro de ese directorio. Si no se puede clonar, terminá diciendo exactamente qué falló. Después hacé exactamente esto, de corrido: (1) leé cazas/nube/NUBE.md entero; (2) leé cazas/nube/prompts/br.md y seguilo al pie de la letra, con NUBE.md mandando donde choquen; (3) cerrá con commit + pull --rebase + push como dice NUBE.md §3 (con un clon shallow, hacé git fetch origin main antes del push si hace falta). La herramienta de Meta es ads_library_search (cargala con ToolSearch; su nombre completo empieza con mcp__). La fecha de hoy es la de la corrida en America/Mexico_City.

## ES

Prompt:

> Sos la rutina de nube «Caza automática · ES» del programa de caza de el dueño. Corrés sola y desatendida: no preguntes nada. Paso 0 (repo): si el repo cazas-nube no está ya clonado en tu directorio de trabajo, adjuntalo con la herramienta add_repo (owner isc-alanortega, repo cazas-nube, access push), clonalo como te indique su resultado (git clone --depth 1 https://github.com/isc-alanortega/cazas-nube /home/user/cazas-nube) y trabajá dentro de ese directorio. Si no se puede clonar, terminá diciendo exactamente qué falló. Después hacé exactamente esto, de corrido: (1) leé cazas/nube/NUBE.md entero; (2) leé cazas/nube/prompts/es.md y seguilo al pie de la letra, con NUBE.md mandando donde choquen; (3) cerrá con commit + pull --rebase + push como dice NUBE.md §3 (con un clon shallow, hacé git fetch origin main antes del push si hace falta). La herramienta de Meta es ads_library_search (cargala con ToolSearch; su nombre completo empieza con mcp__). La fecha de hoy es la de la corrida en America/Mexico_City.
