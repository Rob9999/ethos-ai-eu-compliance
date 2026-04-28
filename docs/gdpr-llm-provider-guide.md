<!-- SPDX-License-Identifier: CC-BY-4.0 -->
<!-- Copyright (c) 2024-2026 Robert Alexander Massinger -->

# DSGVO Art. 44–49 — Leitfaden für LLM-Provider-Auswahl

> Praxis-Leitfaden zur DSGVO-konformen Nutzung von Large Language
> Models (LLMs), mit Fokus auf Datenübertragung in Drittländer
> (Art. 44–49 DSGVO).

| Feld     | Wert                 |
|----------|----------------------|
| Version  | 1.0                  |
| Stand    | 2026-03              |
| Lizenz   | CC-BY 4.0            |
| Autor    | EthosAI Architecture |

---

## 1  Hintergrund: Warum Art. 44–49 für LLMs relevant sind

Die Nutzung von LLM-APIs (z.B. GPT, Claude, Llama-Hosting) bedeutet
in der Regel:

- **Datenübertragung:** Prompts enthalten personenbezogene Daten
  (Namen, E-Mails, IP-Adressen, Kontext)
- **Verarbeitung im Drittland:** Viele Provider verarbeiten Daten
  in den USA, Großbritannien oder Asien
- **Sub-Auftragsverarbeiter:** Cloud-Hoster (AWS, Azure, GCP) können
  Daten an weitere Standorte weiterleiten

Art. 44 DSGVO verbietet die Übertragung personenbezogener Daten in
Drittländer **ohne geeignete Schutzmaßnahmen**.

---

## 2  Angemessenheitsbeschlüsse (Art. 45)

Datenübertragung kann auf einen Angemessenheitsbeschluss gestützt werden,
wenn der konkrete Empfänger und der konkrete Verarbeitungskontext vom
Beschluss erfasst sind. Vor jedem produktiven Transfer ist die aktuelle
EU-Kommissions-/EDPB-Lage zu prüfen (Stand dieses Dokuments: 2026-04):

| Land/Region | Beschluss | Aktuell gültig? |
|-------------|-----------|-----------------|
| Andorra | 2010/625/EU | ✅ Ja |
| Argentinien | 2003/490/EC | ✅ Ja |
| Kanada | 2002/2/EC (Privatsektor) | ✅ Ja |
| Färöer-Inseln | 2010/146/EU | ✅ Ja |
| Guernsey | 2003/821/EC | ✅ Ja |
| Israel | 2011/61/EU | ✅ Ja |
| Isle of Man | 2004/411/EC | ✅ Ja |
| Japan | 2019/419 | ✅ Ja |
| Jersey | 2008/393/EC | ✅ Ja |
| Neuseeland | 2012/484/EU | ✅ Ja |
| Südkorea | 2022/254 | ✅ Ja |
| Schweiz | 2000/518/EC | ✅ Ja |
| Brasilien | 2026 | ✅ Ja |
| Großbritannien | 2021/1772 | ✅ Ja (bis 2028) |
| Uruguay | 2012/484/EU | ✅ Ja |
| **USA** | **EU-US Data Privacy Framework** | ✅ Ja (2023, nur zertifizierte Organisationen) |

### Wichtig für LLM-Provider:
- **US-Provider** müssen im [DPF-Register](https://www.dataprivacyframework.gov/)
  gelistet sein
- Selbstzertifizierung allein reicht nicht — Prüfung erforderlich

---

## 3  Standardvertragsklauseln (Art. 46(2)(c))

Für Provider **ohne** Angemessenheitsbeschluss:

### 3.1  Wann erforderlich?

- Provider sitzt in einem Drittland ohne Angemessenheitsbeschluss
- Oder: Provider nutzt Sub-Auftragsverarbeiter in solchen Ländern

### 3.2  Anforderungen

- [ ] Neue SCCs (Standard Contractual Clauses) gemäß
      Durchführungsbeschluss 2021/914 verwenden
- [ ] Transfer Impact Assessment (TIA) durchführen
- [ ] Zusätzliche technische Maßnahmen dokumentieren:
  - Verschlüsselung der Daten in transit und at rest
  - Pseudonymisierung wo möglich
  - Zugangsbeschränkung (Need-to-know)
- [ ] Regelmäßige Überprüfung der Schutzmaßnahmen

---

## 4  Provider-Anforderungen für DSGVO-Konformität

Was ein LLM-Provider erfüllen muss:

### 4.1  Vertragliche Anforderungen

| Anforderung | Prüfpunkt |
|-------------|-----------|
| Auftragsverarbeitungsvertrag (AVV/DPA) | [ ] DPA vorhanden und unterzeichnet |
| Datenverarbeitungszweck | [ ] Nur zur Auftragserfüllung, kein Training |
| Sub-Auftragsverarbeiter | [ ] Liste der Sub-Processor öffentlich und aktuell |
| Datenlöschung | [ ] Prompt-Daten nicht dauerhaft gespeichert |
| Audit-Recht | [ ] Audit-Möglichkeit vertraglich gesichert |
| Datenstandort | [ ] Verarbeitungsstandort(e) dokumentiert |

### 4.2  Technische Anforderungen

| Anforderung | Prüfpunkt |
|-------------|-----------|
| Verschlüsselung | [ ] TLS 1.3 für API-Kommunikation |
| Datenisolation | [ ] Mandantentrennung nachgewiesen |
| Kein Modell-Training | [ ] Opt-Out für Training auf Kundendaten |
| Zugriffskontrolle | [ ] API-Keys, OAuth, oder mTLS |
| Logging | [ ] Zugriffslogs für Compliance-Nachweis |
| EU-Region | [ ] Verarbeitung in EU/EWR möglich (EU-Region-Option) |

---

## 5  Datenklassifikation für LLM-Nutzung

| Stufe | Label | LLM-Nutzung erlaubt? | Bedingungen |
|-------|-------|---------------------|-------------|
| 0 | PUBLIC | ✅ Ja | Keine Einschränkungen |
| 1 | INTERNAL | ✅ Ja | DPA erforderlich, EU-Region empfohlen |
| 2 | CONFIDENTIAL | ⚠️ Bedingt | DPA + EU-Region + Pseudonymisierung |
| 3 | STRICTLY_CONFIDENTIAL | ❌ Nein | Nur On-Premise / Self-Hosted LLM |

---

## 6  10-Punkte-Checkliste für LLM-Provider-Auswahl

1. [ ] **DPA/AVV** vorhanden und auf neuem Stand
2. [ ] **Datenstandort** in EU/EWR (oder Angemessenheitsbeschluss)
3. [ ] **Kein Modell-Training** auf Kundendaten (opt-out bestätigt)
4. [ ] **Sub-Processor-Liste** aktuell und akzeptabel
5. [ ] **Verschlüsselung** (TLS 1.3, at-rest encryption)
6. [ ] **Datenlöschung** — Prompts werden nach Verarbeitung gelöscht
7. [ ] **SOC 2 Type II** oder ISO 27001 Zertifizierung
8. [ ] **Transfer Impact Assessment** durchgeführt (bei Drittland)
9. [ ] **Incident Response** — Breach-Notification innerhalb 72h
10. [ ] **Exit-Strategie** — Datenexport und Vertragskündigung klar

---

## Über EthosAI

EthosAI® ist auf EU-konformen Betrieb ausgelegt und behandelt
EU AI Act Compliance und DSGVO-Konformität als integrierte
Release- und Deployment-Gates — nicht als nachträgliche Prüfung.

→ [Mehr erfahren](https://ethos-ai.eu)
→ [World-SDK für Entwickler](https://github.com/Rob9999/ethos-ai-world-sdk)
→ [EU AI Act Compliance Checklist](eu-ai-act-compliance-checklist.md)
→ [Security Tier Model](security-tier-model.md)
→ [LLM-Provider-Analyse](llm-provider-analysis.md)

---

*Dieses Dokument wird unter CC-BY 4.0 veröffentlicht und regelmäßig aktualisiert.*
