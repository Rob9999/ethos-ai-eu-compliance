<!-- SPDX-License-Identifier: CC-BY-4.0 -->
<!-- Copyright (c) 2024-2026 Robert Alexander Massinger -->

# EU-konforme LLM-Provider-Analyse

> Anonymisierte Bewertungsmatrix für die Auswahl von LLM-Providern
> gemäß EU AI Act und DSGVO — als öffentlicher Leitfaden für
> Unternehmen, die KI-Dienste EU-konform einsetzen möchten.

| Feld     | Wert                 |
|----------|----------------------|
| Version  | 1.0                  |
| Stand    | 2026-03              |
| Lizenz   | CC-BY 4.0            |
| Autor    | EthosAI Architecture |

---

## 1  Zweck

Dieses Dokument definiert **objektive Bewertungskriterien** für
die Auswahl von LLM-Providern unter EU-Compliance-Gesichtspunkten.
Es enthält keine Empfehlung für einen bestimmten Provider, sondern
ein Framework zur eigenen Bewertung.

---

## 2  Bewertungskategorien

### 2.1  Datenschutz & DSGVO

| Nr. | Kriterium | Gewicht | Beschreibung |
|-----|-----------|---------|--------------|
| D1 | EU-Datenstandort | Hoch | Verarbeitung in EU/EWR möglich |
| D2 | Auftragsverarbeitungsvertrag | Hoch | DPA/AVV gemäß Art. 28 DSGVO |
| D3 | Kein Modell-Training | Hoch | Kundendaten nicht für Training genutzt |
| D4 | Datenlöschung | Mittel | Prompt-Daten nach Verarbeitung gelöscht |
| D5 | Sub-Processor-Transparenz | Mittel | Aktuelle Sub-Processor-Liste öffentlich |
| D6 | Angemessenheitsbeschluss | Hoch | Land des Providers hat Angemessenheitsbeschluss |

### 2.2  Sicherheit

| Nr. | Kriterium | Gewicht | Beschreibung |
|-----|-----------|---------|--------------|
| S1 | Verschlüsselung | Hoch | TLS 1.3, at-rest Encryption |
| S2 | Zertifizierungen | Hoch | SOC 2 Type II und/oder ISO 27001 |
| S3 | Mandantentrennung | Hoch | Isolierung der Kundendaten |
| S4 | Zugriffskontrolle | Mittel | API-Key, OAuth 2.0, mTLS |
| S5 | Incident Response | Mittel | Breach-Notification < 72h |
| S6 | Penetration Tests | Mittel | Regelmäßige externe Pentests |

### 2.3  EU AI Act Konformität

| Nr. | Kriterium | Gewicht | Beschreibung |
|-----|-----------|---------|--------------|
| A1 | Transparenz | Hoch | Modell-Dokumentation verfügbar |
| A2 | Risikomanagement | Hoch | Art. 9 — dokumentiertes Risk Management |
| A3 | Technische Docs | Mittel | Art. 11 — technische Dokumentation |
| A4 | Logging-Fähigkeit | Mittel | Art. 12 — automatische Aufzeichnung |
| A5 | Human Oversight | Mittel | Art. 14 — menschliche Aufsicht möglich |
| A6 | Genauigkeit & Robustheit | Mittel | Art. 15 — dokumentierte Performanz |

### 2.4  Betriebliche Kriterien

| Nr. | Kriterium | Gewicht | Beschreibung |
|-----|-----------|---------|--------------|
| B1 | SLA / Verfügbarkeit | Mittel | Garantierte Uptime ≥ 99.9% |
| B2 | EU-Support | Niedrig | Support-Team in EU/EWR |
| B3 | Exit-Strategie | Mittel | Datenexport, Vertragskündigung klar |
| B4 | Preistransparenz | Niedrig | Kosten pro Token / Request transparent |
| B5 | Self-Hosting-Option | Mittel | On-Premise oder VPC-Deployment möglich |
| B6 | Open-Source-Basis | Niedrig | Modell-Gewichte offen verfügbar |

---

## 3  Bewertungsskala

| Stufe | Punkte | Bedeutung |
|-------|--------|-----------|
| ✅ Erfüllt | 3 | Kriterium vollständig erfüllt |
| ⚠️ Teilweise | 2 | Kriterium mit Einschränkungen erfüllt |
| 🔶 Unklar | 1 | Nicht dokumentiert oder in Klärung |
| ❌ Nicht erfüllt | 0 | Kriterium nicht erfüllt |

### Gewichtungsfaktoren

| Gewicht | Faktor |
|---------|--------|
| Hoch | × 3 |
| Mittel | × 2 |
| Niedrig | × 1 |

**Max. Score:** 24 Kriterien × 3 Punkte × Gewichtung = **162 Punkte**

---

## 4  Provider-Kategorien (anonymisiert)

### Kategorie A — US Cloud Provider (DPF-zertifiziert)
- **Typisch:** Große API-Anbieter mit EU-Region-Option
- **Stärken:** Zertifizierungen, SLA, Skalierbarkeit
- **Risiken:** Schrems-III-Risiko, CLOUDS Act
- **Empfohlene Maßnahmen:** EU-Region aktivieren, DPF-Status prüfen

### Kategorie B — EU-native Provider
- **Typisch:** Europäische KI-Unternehmen, Forschungseinrichtungen
- **Stärken:** DSGVO-nativ, kein Drittland-Transfer
- **Risiken:** Geringere Modell-Vielfalt, kleinere Ökosysteme
- **Empfohlene Maßnahmen:** On-Premise oder EU-Cloud bevorzugen

### Kategorie C — Open-Source Self-Hosted
- **Typisch:** Llama, Mistral, Falcon auf eigener Infrastruktur
- **Stärken:** Volle Datenkontrolle, kein externer Transfer
- **Risiken:** Betriebsaufwand, GPU-Kosten, Update-Management
- **Empfohlene Maßnahmen:** SEC-Tier 2+ Infrastruktur sicherstellen

### Kategorie D — Asiatische Provider (kein Angemessenheitsbeschluss)
- **Typisch:** Provider ohne EU-Angemessenheitsbeschluss
- **Stärken:** Oft günstig, innovative Modelle
- **Risiken:** SCCs erforderlich, TIA-Aufwand, rechtliche Unsicherheit
- **Empfohlene Maßnahmen:** SCCs + TIA + zusätzliche technische Maßnahmen

---

## 5  Entscheidungsmatrix (Template)

```
| Kriterium    | Gewicht | Provider X | Provider Y | Provider Z |
|--------------|---------|------------|------------|------------|
| D1 EU-Region | Hoch    |    ?/3     |    ?/3     |    ?/3     |
| D2 DPA       | Hoch    |    ?/3     |    ?/3     |    ?/3     |
| D3 No-Train  | Hoch    |    ?/3     |    ?/3     |    ?/3     |
| ...          | ...     |    ...     |    ...     |    ...     |
| GESAMT       |         |   ?/162    |   ?/162    |   ?/162    |
```

Nutzen Sie die Kriterien aus Abschnitt 2 mit der Bewertungsskala
aus Abschnitt 3, um eine eigene Bewertung durchzuführen.

---

## 6  Mindestanforderungen nach EthosAI-Datenklassifikation

| Datenklassifikation | Mindest-Score | Pflichtkriterien |
|---------------------|---------------|-----------------|
| PUBLIC (Stufe 0) | 60 / 162 | S1, S2 |
| INTERNAL (Stufe 1) | 90 / 162 | D1, D2, S1, S2, S3 |
| CONFIDENTIAL (Stufe 2) | 120 / 162 | D1–D6, S1–S4, A1 |
| STRICTLY_CONFIDENTIAL (Stufe 3) | — | Nur Self-Hosted (Kat. C) |

---

## 7  Regelmäßige Überprüfung

| Intervall | Aktion |
|-----------|--------|
| Quartalsweise | Sub-Processor-Listen prüfen |
| Halbjährlich | DPF-Zertifizierungsstatus prüfen |
| Jährlich | Vollständige Neubewertung aller Provider |
| Bei Bedarf | Nach EuGH-Urteil, Gesetzesänderung, Datenpanne |

---

## Über EthosAI

EthosAI™ bietet integrierte Compliance-Prüfung für LLM-Provider-Anbindungen
und unterstützt automatische Datenklassifikation pro Request.

→ [Mehr erfahren](https://ethos-ai.eu)
→ [DSGVO LLM-Provider Guide](gdpr-llm-provider-guide.md)
→ [Security Tier Model](security-tier-model.md)
→ [EU AI Act Compliance Checklist](eu-ai-act-compliance-checklist.md)

---

*Dieses Dokument wird unter CC-BY 4.0 veröffentlicht und regelmäßig aktualisiert.*
