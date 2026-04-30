# Plataforma Multi-Canal con Agentes IA

Sistema inteligente con avatar en video, canales multiples y modulos de negocio.

## Modulos
- Avatar Video Agent (interfaz principal web)
- PSTN - Llamadas telefonicas
- Canales: WhatsApp, Telegram, Slack, Teams, Email
- Facturacion CFDI / SAT
- Cotizaciones
- Knowledge RAG (SharePoint, Drive, OneDrive)
- Recibos Email -> Factura
- Agenda y Calendario
- Sumarizacion de Correos
- Web Data / APIs Financieras

## Setup rapido

```
# Windows
.venv\Scripts\Activate.ps1
pip install -r backend/requirements.txt
cp .env.example .env
docker-compose up -d
cd backend && alembic upgrade head
uvicorn backend.app.main:app --reload
```

## Documentacion
- docs/architecture/README.md
- docs/adr/
- docs/runbooks/
- CONTRIBUTING.md
