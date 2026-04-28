<!-- SPDX-License-Identifier: CC-BY-4.0 -->
<!-- Copyright (c) 2024-2026 Robert Alexander Massinger -->

# EthosAI EU Compliance Documentation

> Praxisorientierte Compliance-Dokumentation für KI-Systeme
> gemäß EU AI Act und DSGVO — Open Source unter CC-BY 4.0.

---

## Dokumente

### EU AI Act

| Dokument | Beschreibung |
|----------|--------------|
| [Compliance Checklist](eu-ai-act-compliance-checklist.md) | Risikoklassifikation, Art. 5–15 Anforderungen, Self-Assessment |

### DSGVO / GDPR

| Dokument | Beschreibung |
|----------|--------------|
| [Art. 44–49 LLM-Provider Guide](gdpr-llm-provider-guide.md) | Drittland-Transfer, SCCs, 10-Punkte-Checkliste |
| [LLM-Provider-Analyse](llm-provider-analysis.md) | Bewertungskriterien, Provider-Kategorien, Entscheidungsmatrix |

### Sicherheit

| Dokument | Beschreibung |
|----------|--------------|
| [Security Tier Model](security-tier-model.md) | SEC-Tier 0–3, Maßnahmenmatrix, Tier-Zuordnung |

---

## Feature-Matrix: EthosAI Compliance

| Feature | Community (MPL-2.0) | Commercial |
|---------|---------------------|------------|
| EU AI Act Risk Classification | ✅ | ✅ |
| 4-Tier Security Model | ✅ (Konzept) | ✅ (Enforcement) |
| DSGVO Provider Checks | ✅ (Checkliste) | ✅ (Automatisiert) |
| Datenklassifikation | ✅ (4 Stufen) | ✅ (Automatisch) |
| SEC-Tier Enforcement | — | ✅ |
| EU-Region-Only Mode | — | ✅ |
| Compliance Dashboard | — | ✅ |
| Audit-Log (unveränderlich) | — | ✅ |
| DSFA/DPIA Template | ✅ | ✅ (Assistent) |
| Bereinigung Pipeline | ✅ | ✅ |

---

## Schnellstart

### 1. Compliance-Selbstbewertung

Nutzen Sie die [EU AI Act Compliance Checklist](eu-ai-act-compliance-checklist.md),
um Ihr KI-System einzuordnen:

1. **Risikoklasse bestimmen** — Minimal, Limited, High-Risk oder Unacceptable?
2. **Anforderungen prüfen** — Welche Artikel gelten?
3. **Maßnahmen ableiten** — Was muss implementiert werden?

### 2. LLM-Provider prüfen

Verwenden Sie den [DSGVO Art. 44–49 Guide](gdpr-llm-provider-guide.md)
und die [LLM-Provider-Analyse](llm-provider-analysis.md):

1. **Datenstandort prüfen** — EU/EWR oder Drittland?
2. **DPA verifizieren** — Auftragsverarbeitungsvertrag vorhanden?
3. **10-Punkte-Checkliste** durcharbeiten

### 3. Sicherheitsstufe festlegen

Das [Security Tier Model](security-tier-model.md) hilft bei der Zuordnung:

- **Development** → Tier 0
- **Staging/CI** → Tier 1
- **Production** → Tier 2
- **Reguliert** → Tier 3

---

## Über EthosAI

**EthosAI®** ist eine EU-AI-Act-konforme KI-Plattform, die
Compliance, Sicherheit und Ethik als integrierten Bestandteil
implementiert — nicht als nachträgliche Prüfung.

### Warum EthosAI?

- **EU-nativ** — Entwickelt für den europäischen Rechtsrahmen
- **Security-by-Design** — 4-Stufen-Sicherheitsmodell von Anfang an
- **Open Core** — Kernkonzepte offen, Enterprise-Features kommerziell
- **World Packs** — Modulare KI-Erweiterungen über SDK

### Links

- [EthosAI Website](https://ethos-ai.eu)
- [World SDK für Entwickler](https://github.com/Rob9999/ethos-ai-world-sdk)
- [Core Concepts](https://github.com/Rob9999/ethos-ai-core)

### Kontakt

Interesse an der Commercial License oder Enterprise-Support?

→ **[Kontakt aufnehmen](https://ethos-ai.eu/contact)**

---

## Lizenz

Alle Dokumente in diesem Repository stehen unter
[CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).

EthosAI® ist eine eingetragene Marke. Siehe [Trademark Policy](../../TRADEMARK.md).

---

*Letzte Aktualisierung: 2026-03*
