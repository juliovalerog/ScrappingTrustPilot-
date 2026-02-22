# ScrappingTrustPilot

Notebook para hacer scraping de reseñas de Trustpilot de Trade Republic y exportarlas a CSV.

## Contenido

- `trustpilot_scraping_traderepublic.ipynb`: notebook principal de scraping.
- `traderepublic_reviews_p1_p10.csv`: salida de ejemplo (paginas 1 a 10).
- `requirements.txt`: dependencias minimas.

## Requisitos

- Python 3.10+
- Dependencias:
  - `requests`
  - `beautifulsoup4`
  - `pandas`
  - `lxml`

Instalacion:

```bash
pip install -r requirements.txt
```

## Uso

1. Abre `trustpilot_scraping_traderepublic.ipynb` en Jupyter/VS Code.
2. Ajusta los parametros:
   - `BASE_URL`
   - `START_PAGE`
   - `END_PAGE`
   - `OUTPUT_CSV`
3. Ejecuta el notebook completo.
4. Revisa el CSV generado.

## Nota tecnica

Trustpilot cambia con frecuencia la estructura del HTML. El parser actual usa selectores robustos para detectar tarjetas de reseñas:

- `div[data-testid='service-review-card-v2']`
- fallback: `article[data-service-review-card-paper]`

y extrae:

- Texto: `p[data-service-review-text-typography]`
- Fecha: `time[data-service-review-date-time-ago]` (con fallback a `time`).

## Aviso

Usa este proyecto respetando los terminos de uso de Trustpilot y la normativa aplicable de tratamiento de datos.
