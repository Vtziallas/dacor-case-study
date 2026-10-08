# Dacor — Maritime Threat Intelligence Platform

**Case study — no source code.** This was built while employed at [Sea
Guardian](https://sguardian.com); the codebase is proprietary and not
published. This repository documents what I built and how, for a
portfolio/CV audience.

Sea Guardian publicly markets this system as the "DaCoR system" / "Maritime
Risk & Threat Intelligence (MRTI) Dashboard" — see their
[AI Services page](https://sguardian.com/ai-services/) and
[public press coverage](https://allaboutshipping.co.uk/2026/08/09/the-dacor-system-sea-guardian-sg-ltd/).

## What it does

Dacor aggregates, scores, and distributes maritime security risk assessments
to fleet operators, shipping companies, and maritime security analysts:

- Live interactive map (Leaflet) with geo-polygon region overlays across
  30+ monitored maritime regions (e.g. Gulf of Guinea, Red Sea/Yemen)
- Scores four threat categories per region — Military/Terrorism,
  Piracy/Brigandage, Hijacking/Kidnapping/Life Losses, GNSS/GPS
  Interference — on a 0–25 scale, rolling up into the platform's public
  five-tier regional risk rating (Very High → Very Low)
- AI-assisted threat extraction: a GPT-4o pipeline reads analyst-authored
  Excel assessments and populates structured threat scores automatically
- Live AIS vessel tracking (ShipFinder integration) with custom point
  tracking for vessels, incidents, and assets
- Incident logging across five categories (piracy, military,
  cyber/environmental, etc.)
- Generates PDF risk reports and per-vessel, per-voyage risk registers
- Role-based access control across five granular roles (admin, editor,
  editor-external, viewer, viewer-with-documents), rolling up to the three
  broad tiers (Admin/Editor/Viewer) described publicly

## My role

Sole developer, end-to-end: data model, backend API, frontend, AI
integration, and third-party integrations.

## Stack

- **Frontend:** React 18, TypeScript, Vite, Tailwind CSS, Leaflet (maps +
  drawing), React Query, Recharts, jsPDF, Zod + React Hook Form
- **Backend:** PHP (WordPress REST API), MySQL (custom tables: regions,
  threats, vessels, incidents, infrastructure, audit log)
- **AI:** OpenAI GPT-4o via the OpenAI PHP client, structured extraction
  prompting
- **Integrations:** ShipFinder API (AIS vessel positions)
- **Delivery:** packaged as a WordPress plugin — installs without separate
  hosting or database setup

## Links

- Product page: https://sguardian.com/ai-services/
- Public press coverage: https://allaboutshipping.co.uk/2026/08/09/the-dacor-system-sea-guardian-sg-ltd/
- Live platform: https://3dguardian-psc.com/arkadoai-threat/
