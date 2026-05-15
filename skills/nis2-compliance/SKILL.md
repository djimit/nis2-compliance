---
name: nis2-compliance
description: >-
  Toetst organisaties op naleving van de NIS2-richtlijn (2022/2555) en de
  Nederlandse Cyberbeveiligingswet (Cbw). Bevat sectorale classificatie,
  zorgplicht-eisen, meldplicht-procedures (24u/72u/1m), bestuurlijke
  verantwoordelijkheid, supply chain security, en sanctie-informatie.
  Afgestemd op BIO2 voor de overheidscontext.
  Gebruik deze skill wanneer de gebruiker vraagt over 'NIS2', 'Cyberbeveiligingswet',
  'Cbw', 'netwerk- en informatiebeveiliging', 'zorgplicht cyberbeveiliging',
  'meldplicht incident', 'NIS2 compliance', 'bestuurlijke verantwoordelijkheid',
  'supply chain security', 'NIS2 sector', 'essentiële entiteit',
  'belangrijke entiteit', 'NCTV toezicht', 'NIS2 audit', 'NIS2 certificering',
  'NIS2 boete', 'ICT supply chain', 'vendor risk management NIS2',
  of wanneer de gebruiker NIS2-compliance wil beoordelen.
model: sonnet
allowed-tools:
  - WebFetch(*)
---

# NIS2 / Cyberbeveiligingswet Compliance Checker

Toets organisaties aan de NIS2-richtlijn (2022/2555) en de Nederlandse implementatie: de **Cyberbeveiligingswet (Cbw)**. De Cbw vervangt de Wet beveiliging netwerk- en informatiesystemen (Wbni) en treedt naar verwachting in Q2 2026 in werking.

Bron: [NCTV — Cyberbeveiligingswet](https://www.nctv.nl/onderwerpen/c/cyberbeveiligingswet) | [Digitale Overheid — Cbw](https://www.digitaleoverheid.nl/overzicht-van-alle-onderwerpen/cyberbeveiligingswet/) | [NIS2 Richtlijn (EUR-Lex)](https://eur-lex.europa.eu/legal-content/NL/TXT/?uri=CELEX:32022L2555)

## Sectorale Classificatie

Bepaal eerst of en hoe je organisatie onder NIS2 valt:

### Essentiële entiteiten (hoogste eisen)

| Sector | Subsector | Voorbeelden NL |
|--------|-----------|----------------|
| **Energie** | Elektriciteit, stadsverwarming, olie, gas, waterstof | Tennet, Gasunie, Enexis, regionale netbeheerders |
| **Transport** | Lucht, spoor, water, weg | Schiphol, NS, ProRail, Rijkswaterstaat |
| **Bankwezen** | Kredietinstellingen | Grootbanken |
| **Financiële marktinfrastructuur** | Handelssystemen, centrale tegenpartijen | Euronext |
| **Gezondheidszorg** | Ziekenhuizen, laboratoria, EU-gezondheidsreferentie | UMC's, perifere ziekenhuizen |
| **Drinkwater** | Waterlevering en -kwaliteit | Drinkwaterbedrijven |
| **Afvalwater** | Afvalwaterinzameling en -behandeling | Waterschappen (waterzuivering) |
| **Digitale infrastructuur** | DNS, TLD, cloud, datacenter, CDN, trust | SIDN, grote datacenters, vertrouwensdiensten |
| **ICT-dienstbeheer** | Managed service providers (MSP/MSSP) | Grote MSP's met >~50 medewerkers |
| **Overheid** | Centrale overheid, regionaal, publiekrechtelijk | Ministeries, provincies, waterschappen |
| **Ruimtevaart** | Ruimteinfrastructuur | Satellietoperators |

### Belangrijke entiteiten (gemiddelde eisen)

| Sector | Voorbeelden NL |
|--------|----------------|
| **Post- en koeriersdiensten** | PostNL (pakketten) |
| **Afvalbeheer** | Regionale afvalverwerkers |
| **Chemie** | Chemische productie en distributie |
| **Voedsel** | Grootschalige voedselproductie en -distributie |
| **Industrie** | Medische hulpmiddelen, elektronica, machines, voertuigen |
| **Digitale aanbieders** | Online marktplaatsen, zoekmachines, sociale netwerken |
| **Onderzoek** | Onderzoeksorganisaties (NWO, TNO, universiteiten?) |

### Gemeenten

Gemeenten vallen NIET rechtstreeks onder NIS2 als 'overheidsentiteit' (dat is centraal + regionaal). MAAR: gemeenten die diensten aanbieden die onder een NIS2-sector vallen (drinkwater via gem. NV, havenbedrijf = transport) vallen WEL onder NIS2 voor dat onderdeel.

**Praktijk:** Ook gemeenten moeten zich voorbereiden — BIO2 is de sectorspecifieke invulling van NIS2 voor de gehele overheidssector.

## Drie Pijlers van NIS2

### Pijler 1 — Zorgplicht (Art. 21 NIS2 / Cbw)

Passende en proportionele technische, operationele en organisatorische maatregelen:

| Domein | Minimale maatregelen |
|--------|---------------------|
| **Risicomanagement** | ISMS (ISO 27001), risicoanalyses, risicoregister |
| **Security policies** | Informatiebeveiligingsbeleid, incident response plan, BCM |
| **Incident management** | Detectie, respons, forensisch onderzoek, lessons learned |
| **Business continuity** | BCM-plannen, backup, redundantie, crisisbeheer |
| **Supply chain** | Vendor risicobeoordeling, security eisen in contracten, auditrechten |
| **Netwerkbeveiliging** | Netwerksegmentatie, firewalls, IDS/IPS, monitoring |
| **Toegangsbeheer** | MFA, RBAC, privileged access management, zero trust |
| **Cryptografie** | Encryptiebeleid, sleutelbeheer, conform NCSC-richtlijnen |
| **HR security** | Screening, training, bewustwording, exit-procedures |
| **Fysieke beveiliging** | Datacenter security, toegangscontrole, CCTV |

**Check:** Zijn alle 10 domeinen afgedekt met concrete maatregelen?

### Pijler 2 — Meldplicht (Art. 23 NIS2 / Cbw)

Bij een significant incident — gelaagde meldplicht:

| Termijn | Actie | Inhoud |
|---------|-------|--------|
| **Binnen 24 uur** | Early warning | Eerste waarschuwing: wat is er gebeurd, welke systemen, vermoedelijke oorzaak, verwachte impact |
| **Binnen 72 uur** | Volledige melding | Update met incidentdetails: omvang, getroffen entiteiten, grensoverschrijdende impact |
| **Binnen 1 maand** | Eindrapport | Root cause, mitigatie, lessons learned, preventieve maatregelen |

Meldplicht geldt voor **significante incidenten** — criteria:
- Heeft ernstige operationele verstoring veroorzaakt of kan veroorzaken
- Heeft geleid tot of kan leiden tot aanzienlijke financiële schade
- Heeft of kan aanzienlijke schade toebrengen aan andere natuurlijke of rechtspersonen

**Praktijk:** Het onderscheid "significant/niet-significant" is subjectief. Bij twijfel: melden. De NCTV bepaalt achteraf of het significant was.

**Voor overheidsorganisaties:** De BIO2-meldplicht (5.24.07) is aanvullend — melden aan nationaal CSIRT EN via de eigen BIO2-lijn.

### Pijler 3 — Bestuurlijke verantwoordelijkheid (Art. 20 NIS2)

Bestuurders zijn PERSOONLIJK aansprakelijk:

- Bestuur moet risicobeheersmaatregelen **goedkeuren**
- Bestuur moet cybersecurity-**opleiding volgen** en kennis aantonen
- Bestuur is **hoofdelijk aansprakelijk** bij niet-naleving
- Bestuur kan tijdelijk worden **geschorst** als toezichthouder

**Checklist bestuur:**
- [ ] Heeft het bestuur de security-maatregelen formeel goedgekeurd?
- [ ] Heeft het bestuur cybersecurity-opleiding gevolgd?
- [ ] Is er een bestuursbesluit waarin risico-acceptatie is vastgelegd?
- [ ] Is de CISO's onafhankelijke adviesbevoegdheid geborgd? (BIO2 5.02.02)

## Supply Chain Security (Art. 21(2)(c))

NIS2 stelt expliciete eisen aan de toeleveringsketen:

- [ ] **Vendor inventory**: Volledige lijst van ICT-leveranciers en diensten
- [ ] **Risicoclassificatie**: Per vendor: welke NIS2-relevante diensten, welk risiconiveau?
- [ ] **Security eisen in contracten**: Beveiligingseisen en audits expliciet opgenomen (zie BIO2 5.20.01–06)
- [ ] **Sub-verwerkers**: In kaart gebracht en beoordeeld
- [ ] **Concentratierisico**: Zijn kritieke diensten te afhankelijk van één leverancier?
- [ ] **Exit strategie**: Voor elke kritieke leverancier een exit plan
- [ ] **Audit & monitoring**: Periodieke beoordeling van vendor security
- [ ] **Incidenten**: Verplichting voor vendors om incidenten direct te melden

## Toezicht en Sancties

### Toezichthouders NL

```
Ministerie van Justitie & Veiligheid (NCTV/DTC)
  ├── Toezicht op essentiële en belangrijke entiteiten
  ├── Afhandeling incidentmeldingen
  └── Sanctiebevoegdheid
Sectorale toezichthouders (artikel 11 Cbw)
  ├── AFM / DNB → financiële sector
  ├── RDI → telecom, digitale infrastructuur
  ├── ILT → transport
  ├── NZa → gezondheidszorg
  ├── ANVS → nucleair
  └── Staatstoezicht op de Mijnen → energie/mijnbouw
```

### Sancties

| Entiteit | Maximum boete |
|----------|---------------|
| **Essentiële entiteiten** | **€10 miljoen of 2%** van wereldwijde jaaromzet |
| **Belangrijke entiteiten** | **€7 miljoen of 1,4%** |
| **Bestuurders** | Persoonlijke sancties (schorsing, boetes) |

## NIS2 ↔ BIO2 Koppeling

NIS2 en BIO2 versterken elkaar. BIO2 dient als **sectorspecifieke invulling** van NIS2 voor de overheid:

| NIS2-eis | BIO2-maatregel |
|----------|----------------|
| Zorgplicht (Art. 21) | BIO2 Deel 2 — volledige overheidsmaatregelen |
| Supply chain (Art. 21(2)(c)) | BIO2 5.19–5.23 (inkoop & leveranciersbeheer) |
| Incident management | BIO2 5.24–5.28 |
| Toegangsbeheer | BIO2 5.15–5.18 |
| Kwetsbaarheden | BIO2 8.08 |
| Logging | BIO2 8.15–8.16 |
| Business continuity | BIO2 5.30, 5.33 |
| Cryptografie | BIO2 8.24 |
| Netwerkbeveiliging | BIO2 8.20–8.22 |
| Bestuurlijke verantwoordelijkheid | BIO2 5.02 — rollen en verantwoordelijkheden |

**Als de organisatie BIO2-compliant is, is ~80% van NIS2 al afgedekt.**

## Gap Analyse Checklist

- [ ] **Sectorclassificatie**: Is de organisatie essentieel, belangrijk, of niet-NIS2?
- [ ] **Wbni-check**: Valt de organisatie nog onder de oude Wbni? (overgangsrecht)
- [ ] **ISMS**: Is er een formeel ISMS? (ISO 27001, BIO2, NEN 7510)
- [ ] **Risicoregister**: Bestaat er een actueel risicoregister met cybersecurity-risico's?
- [ ] **Incidentproces**: Is het incidentproces ingericht met de 24u/72u/1m termijnen?
- [ ] **Supply chain**: Is de vendor-inventaris compleet en geriskeerd?
- [ ] **Bestuursgoedkeuring**: Heeft het bestuur de maatregelen formeel goedgekeurd?
- [ ] **CISO**: Is er een onafhankelijke CISO met adviesbevoegdheid aan bestuur?
- [ ] **Logging & monitoring**: Wordt de IT-omgeving actief gemonitord?
- [ ] **Pentest**: Worden er periodiek pentesten uitgevoerd?
- [ ] **Opleiding**: Hebben bestuurders cybersecurity-opleiding gevolgd?
- [ ] **Melding**: Is het meldproces voor NCTV ingericht?

## Meer informatie

- [NCTV — Cyberbeveiligingswet](https://www.nctv.nl/onderwerpen/c/cyberbeveiligingswet)
- [Digitale Overheid — Cbw](https://www.digitaleoverheid.nl/overzicht-van-alle-onderwerpen/cyberbeveiligingswet/)
- [NIS2 Richtlijn (EUR-Lex)](https://eur-lex.europa.eu/legal-content/NL/TXT/?uri=CELEX:32022L2555)
- [ENISA — NIS2 Implementation](https://www.enisa.europa.eu/topics/cybersecurity-policy/nis-directive-new)
- [Cybersecurityraad — NIS2 Advies](https://www.cybersecurityraad.nl/)
- [Rijksinspectie Digitale Infrastructuur (RDI)](https://www.rdi.nl/)
