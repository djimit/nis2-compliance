# Copilot Instructions — nis2-compliance

> See root `.github/copilot-instructions.md` for global conventions.

Claude Code plugin voor **NIS2 / Cyberbeveiligingswet compliance**. Toetst organisaties op NIS2-zorgplicht, meldplicht (24u/72u/1maand), bestuurlijke verantwoordelijkheid, supply chain security, en risicomanagement.

## Structure

```
.claude-plugin/plugin.json    # Plugin metadata (name, description, version, keywords)
skills/nis2-compliance/
  SKILL.md                    # Skill definition — triggers, model config, scope
```

## Installation

```bash
claude install djimit/nis2-compliance
```

## Typical Usage

- **Sectorale classificatie** — Bepaal of organisatie essentiële of belangrijke entiteit is
- **Zorgplicht-analyse** — Toets op 10 NIS2-zorgplichtgebieden (risicomanagement, incidentmanagement, business continuity, supply chain security, etc.)
- **Meldplicht-procedure** — Genereer meldprotocol: 24u → NCTV/CERT-NL, 72u → aanvullende info, 1m → impactanalyse
- **Bestuurlijke verantwoordelijkheid** — Adviseer management over verantwoordelijkheden en aansprakelijkheid
- **Supply chain security** — Toets leveranciers en ICT-dienstverleners op NIS2-eisen
- **BIO2-koppeling** — Koppel NIS2-zorgplicht aan BIO2-maatregelen

## Domain Context

- NIS2-richtlijn (2022/2555) — Europese implementatie van netwerk- en informatiebeveiliging
- Cyberbeveiligingswet (Cbw) — Nederlandse implementatie, vervangt Wbni, naar verwachting Q2 2026 in werking
- NCTV — Nationaal Coördinator Terrorismebestrijding en Veiligheid (toezichthouder)

## License

MIT (see `plugin.json`)
