# Datenschutz-Folgenabschaetzung (DSFA / DPIA)
### Gesetzliche Grundlage: Art. 35 DSGVO

---

## 1. Schwellwertanalyse (Pruefung der DSFA-Pflicht)

Eine DSFA ist obligatorisch, wenn eine Datenverarbeitung voraussichtlich ein **hohes Risiko** fuer die Rechte und Freiheiten natuerlicher Personen zur Folge hat (Art. 35 Abs. 1 DSGVO, DSK-Muss-Liste / EDPB Guidelines).

| Kriterium | Zutreffend? | Anmerkung |
| :--- | :---: | :--- |
| Systematische & umfassende Bewertung persoenlicher Aspekte (Profiling) | [ ] Ja / [x] Nein | Keine automatisierte Bonitaetsentscheidung |
| Umfangreiche Verarbeitung besonderer Kategorien (Art. 9 / 10 DSGVO) | [ ] Ja / [x] Nein | Gesundheitsdaten, biometrische Daten |
| Systematische, weitraeumige Ueberwachung oeffentlich zugaenglicher Bereiche | [ ] Ja / [x] Nein | Videoüberwachung etc. |
| Einsatz neuartiger Technologien / KI-Modelle | [x] Ja / [ ] Nein | Integration von LLM-Workflows zur Textanalyse |

---

## 2. Beschreibung der geplanten Verarbeitung

* **Projekt / System:** [Name des Systems, z.B. Interner KI-Copilot fuer Support]
* **Verarbeitungszweck:** Schnellere Beantwortung standardisierter Supportanfragen unter Beruecksichtigung von Geschaeftsgeheimnissen.
* **Betroffene Personen:** Kunden, Supportmitarbeiter.
* **Datenfluesse:**
  1. Kunde sendet Ticket ueber Supportportal (TLS 1.3).
  2. PII-Anonymisierungs-Engine maskiert Namen, E-Mail-Adressen und Zahlungsinformationen vor Weiterleitung.
  3. LLM verarbeitet Anfrage in einer isolierten VPC (Azure EU / AWS Frankfurt).
  4. Antwort wird generiert und von einem Mitarbeiter vor Versand geprueft (Human-in-the-Loop).

---

## 3. Notwendigkeit & Verhaeltnismaessigkeit (Art. 35 Abs. 7 lit. b DSGVO)

* **Zweckbindung:** Daten werden ausschliesslich fuer den Ticket-Kontext verwendet und nicht zum Training oeffentlicher Modelle genutzt (Zero Data Retention SLA).
* **Datenminimierung:** Anonymisierungs-Filter entfernt 100% identifizierender Daten vor API-Aufruf.
* **Transparenz:** Datenschutzhinweis im Ticketportal gem. Art. 13 DSGVO.

---

## 4. Risikobewertung & Abhilfemassnahmen (Art. 35 Abs. 7 lit. c, d DSGVO)

| Identifiziertes Risiko | Eintrittswahrscheinlichkeit | Schadensschwere | Risikograd | Geplante Abhilfemassnahme (TOM) | Restrisiko |
| :--- | :---: | :---: | :---: | :--- | :---: |
| Unbeabsichtigte PII-Uebertragung an LLM-Provider | Gering | Mittel | **Mittel** | Regex- & NLP-basierte automatische PII-Maskierung vor Uebertragung | **Gering** |
| Fehlende Zweckbindung beim Modellbetreiber | Sehr gering | Hoch | **Mittel** | Enterprise DPA mit Zero-Data-Retention & Auftragsverarbeitung gem. Art. 28 DSGVO | **Sehr gering** |
| Falschauskunft an den Betroffenen | Mittel | Gering | **Gering** | Human-in-the-Loop-Freigabe vor Absenden an den Kunden | **Sehr gering** |

---

## 5. Stellungnahme des Datenschutzbeauftragten & Freigabe

* **Empfehlung des DSB:** Die Durchfuehrung der Verarbeitung ist mit den dokumentierten Abhilfemassnahmen zulaessig.
* **Datum / Unterschrift Geschaeftsfuehrung:** `____________________`
