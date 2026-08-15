# Technisch-organisatorische Massnahmen (TOMs)
### Gesetzliche Grundlage: Art. 32 Abs. 1 DSGVO & NIS2-Baseline

---

## 1. Vertraulichkeit (Art. 32 Abs. 1 lit. b DSGVO)

### 1.1 Zutrittskontrolle (Physische Sicherheit)
- [x] Abgeschlossene Server- und Bueroraeume mit elektronischem Schliesssystem / Schluesselprotokoll.
- [x] Besucherprotokollierung und Begleitung in sensiblen Unternehmensbereichen.
- [x] Alarmanlage und Aufschaltung auf Sicherheitsdienst ausserhalb der Geschaeftszeiten.

### 1.2 Zugangskontrolle (Systemebene)
- [x] Personalisierte Benutzerkonten fuer alle Mitarbeiter (Verbot von Shared Accounts).
- [x] Passwort-Richtlinie (Mindestens 14 Zeichen, Komplexitaetsanforderungen, Password Manager Pflicht).
- [x] **Multi-Faktor-Authentifizierung (MFA / 2FA)** fuer saemtliche Cloud-Dienste, E-Mail-Zugaenge und VPNs.
- [x] Automatische Bildschirmsperre nach 5 Minuten Inaktivitaet.

### 1.3 Zugriffskontrolle (Berechtigungsmanagement)
- [x] Rollen- und Rechtekonzept nach dem **Need-to-Know- / Least-Privilege-Prinzip**.
- [x] Regelmaessige halbjaehrliche Re-Zertifizierung von Administratorrechten.
- [x] Sofortiger De-Provisioning-Prozess beim Austritt von Mitarbeitern.

### 1.4 Trennungskontrolle (Mandantentrennung)
- [x] Getrennte Datenbanken und Umgebungen fuer Entwicklung (DEV), Test (STAGING) und Produktion (PROD).
- [x] Keine Verwendung von echten Produktivdaten in Testsystemen (Synthetische Testdaten).

### 1.5 Pseudonymisierung & Verschluesselung (Art. 32 Abs. 1 lit. a DSGVO)
- [x] **Verschluesselung im Ruhezustand (Data at Rest):** AES-256 Bit Verschluesselung aller Festplatten (BitLocker / LUKS) und Cloud-Speicher.
- [x] **Verschluesselung bei Uebertragung (Data in Transit):** TLS 1.3 / TLS 1.2 fuer alle Webseiten, APIs und VPNs; HSTS mit Preload aktiviert.
- [x] **Lokale Schriftarten:** Google Fonts werden ausschliesslich lokal auf eigenen Servern gehostet (Vermeidung von Drittlanduebertragungen).

---

## 2. Integritaet (Art. 32 Abs. 1 lit. b DSGVO)

### 2.1 Weitergabekontrolle
- [x] Verschluesselter E-Mail-Versand (TLS) sowie Ende-zu-Ende-Verschluesselung bei sensiblen Anhaengen.
- [x] Verbot unverschluesselter USB-Sticks und externer Wechselmedien.

### 2.2 Eingabekontrolle
- [x] Revisionssichere Protokollierung aller Aenderungen an personenbezogenen Stammdaten.
- [x] Zentrales Log-Management (SIEM) mit Manipulationsschutz und getrennten Audit-Logs.

---

## 3. Verfuegbarkeit und Belastbarkeit (Art. 32 Abs. 1 lit. b, c DSGVO)

- [x] **3-2-1 Backup-Strategie:** 3 Kopien, 2 verschiedene Medien, 1 getrennte Offsite/Cloud-Kopie (Immutable / WORM-Storage gegen Ransomware).
- [x] **Wiederherstellungstests (Disaster Recovery):** Quartalsweise Durchfuehrung von Restore-Tests mit Dokumentation der RTO (Recovery Time Objective) und RPO (Recovery Point Objective).
- [x] USV (Unterbrechungsfreie Stromversorgung) fuer lokale Netzwerkinfrastruktur.
- [x] DDoS-Schutz und redundante Webserver-Architektur.

---

## 4. Verfahren zur regelmaessigen Ueberpruefung und Bewertung (Art. 32 Abs. 1 lit. d DSGVO)

- [x] Regelmaessige automatisierte Website-Scans mit **[dsgvo-checker](https://github.com/AirFun1311/dsgvo-checker)**.
- [x] Jaehrliche externe Vulnerability Scans / Penetration Tests.
- [x] Datenschutz- und Informationssicherheitsschulungen fuer alle Mitarbeiter bei Eintritt sowie jaehrlich wiederkehrend.
- [x] Etablierter **Data Breach Response Plan** mit 72-Stunden-Meldeprozess an die zustaendige Aufsichtsbehoerde (Art. 33 DSGVO).
