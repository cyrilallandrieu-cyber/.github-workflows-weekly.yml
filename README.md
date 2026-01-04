
# Agente semanal – Publicidad Automoción (España)

Genera un informe `.pptx` + `.log` + `.json` analizando campañas en la **semana natural anterior (lunes–domingo)**:
- Sitios oficiales de marcas (.es)
- **Meta Ads Library** (UI, best-effort)
- **Google Ads Transparency Center** (UI)
- **YouTube (Data API v3)** para “online video”

## Requisitos
- Python 3.10+  
- `pip install requests beautifulsoup4 python-pptx`  
- Opcional:
  - `pip install playwright` y `python -m playwright install --with-deps` (fuentes dinámicas)  
  - `pip install google-api-python-client` (YouTube API)

## Variables de entorno (opcionales)
| Variable | Descripción |
|---|---|
| `USE_PLAYWRIGHT` | `1` habilita scraping de SPA (Meta / GATC) |
| `PLAYWRIGHT_HEADLESS` | `1` navegación sin UI |
| `YOUTUBE_API_KEY` | clave de proyecto para YouTube Data API v3 |
| `COUNTRY_CODE` | código país para filtros (por defecto `ES`) |
| `BRANDS_CSV` | lista de marcas a considerar (override) |
| `BRAND_SITE_TIMEOUT` | timeout HTTP en sitios oficiales (segundos) |

## Ejecución local
```bash
export USE_PLAYWRIGHT=1
export COUNTRY_CODE=ES
# export YOUTUBE_API_KEY=tu_clave   # si deseas YouTube
python agent_auto_es.py
