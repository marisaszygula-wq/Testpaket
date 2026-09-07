# HS Milano: Alle 3 Einstiege in die Kundenakquisition
## Mit Workflows, Automatisierungspotential & erforderliche E-Mail-Vorlagen

---

## 🎯 ÜBERBLICK: DIE 3 EINSTIEGE

```
┌─────────────────────────────────────────────────────────────────┐
│                  FRISEUR KOMMT ZU HS MILANO                     │
├─────────────────────────────────────────────────────────────────┤
│                                                                   │
│  EINSTIEG 1:          EINSTIEG 2:          EINSTIEG 3:          │
│  Testpaket-Formular   Website-Registrierung  Telefon/Empfehlung │
│  ↓                    ↓                      ↓                   │
│  Online ausfüllen     Online registrieren   Anruf oder          │
│  → HubSpot Contact    → Prüfung erforderlich  Kontaktweiterleitung
│  (auto)               → Marisa Qual.Call    → Marisa Qual.Call   │
│                       → HubSpot + Shopware  → HubSpot + Shopware │
│                       (manuell)             (manuell)            │
│                                                                   │
└─────────────────────────────────────────────────────────────────┘
```

---

# EINSTIEG 1: TESTPAKET-FORMULAR

## Phase 1: FORMULAREINGABE & KONTAKT-ERSTELLUNG

**Was passiert:** Friseur füllt Testpaket-Formular auf Website aus

**Datenfluss:**
```
Formular ausfüllen
    ↓
Daten an HubSpot
    ↓
Kontakt wird automatisch angelegt
    ↓
Deal wird angelegt
    ↓
Stage: "Testpaket angefragt"
```

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Formular-Daten → HubSpot Contact (automatisch)
- ✅ Deal automatisch erstellen mit Namen aus Formular
- ✅ Dealstage automatisch setzen auf "Testpaket angefragt"
- ✅ Tom automatisch als Deal Owner zuweisen (oder Marisa?)
- ✅ Reminder an Tom/Marisa: "Neue Testpaket-Anfrage"

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 1: Bestätigungsmail (automatisch nach Formular-Eintrag)**
- [ ] Titel: "Dankeschön für deine Anmeldung"
- Inhalt: Dankeschön, Referenznummer, nächste Schritte
- Trigger: Kontakt in HubSpot angelegt
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 2: QUALIFIZIERUNG - KONTAKTAUFNAHME

**Verantwortlicher:** Zuständiger Verkäufer (meist Tom)
**Aufgabe:** Anrufen und qualifizieren

**Ablauf:**
```
Kontaktaufnahmeversuche (3x Anrufe)
    ↓
JA - Erreichbar? → Qualianruf führen (Leitfaden verwenden)
    ↓
Zum Ende hin: Termin für Erstberatung vereinbaren
    ↓
Deal Stage: "Tom - Testpaket erfassen"
    ↓
Neukundenmail versenden

NEIN - Nicht erreichbar?
    ↓
Versuch 3-6: WhatsApp (wenn Mobil vorhanden) oder E-Mail
    ↓
Nach 6 Versuchen: Deal Stage "Verloren"
```

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Reminder an Tom: "Qualianruf erforderlich" (1-2 Tage nach Formular)
- ✅ Nach 3 Tagen ohne Kontakt: Erinnerung für WhatsApp/E-Mail versenden
- ✅ Zähler für Kontaktversuche (tracken wie viele Versuche)
- ✅ Nach 6 Versuchen automatisch Stage auf "Verloren" setzen
- ✅ Automatische Benachrichtigung wenn Termin vereinbart (an Tom & Marisa)

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 2: Kontaktversuch nach 3 Tagen (wenn nicht erreichbar)**
- [ ] Titel: "Wir versuchen dich zu erreichen"
- Inhalt: Kurze Nachricht, Rückruf-Bitte, Kontaktnummern
- Trigger: 3 Tage nach Formular + kein Kontakt hergestellt
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 3: NACH QUALIANRUF - NEUKUNDENMAIL

**Zeitpunkt:** Direkt nach Qualianruf (wenn positiv)

**Aktion:**
1. Neukundenmail automatisch versenden
2. Deal Stage: "Tom - Testpaket erfassen"
3. Tom benachrichtigen (Testpaket erfassen jetzt möglich)

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Trigger: Deal Stage = "Tom - Testpaket erfassen"
- ✅ Neukundenmail automatisch versenden
- ✅ Erinnerung an Tom: "Testpaket jetzt erfassen"

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 3: Neukundenmail (nach Qualianruf)**
- [ ] Titel: "Herzlich willkommen! Hier geht's los"
- Inhalt: Danke für Anruf, nächste Schritte, Erwartungshaltung setzen
- Trigger: Deal Stage = "Tom - Testpaket erfassen"
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 4: TESTPAKET-ERFASSUNG (TOM)

**Verantwortlicher:** Tom

**Aktion in Shopware:**
1. Friseur in Shopware anlegen
2. Kostenloses Testpaket erfassen
3. ⚠️ **WICHTIG - Ahmet-Check:**
   - Hat Kunde Ahmet-Link verwendet? → NEIN (kommt vom Formular)
   - Wurde Ahmet in Qualianruf erwähnt? → Falls JA: Wie Affiliate-Link behandeln
4. Deal Stage: "Testpaket erfasst"

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Reminder an Tom: "Testpaket-Erfassung erforderlich"
- ✅ Nach Erfassung automatisch: Stage auf "Testpaket erfasst" updaten
- ✅ Automatische Benachrichtigung an Marisa: "Testpaket vergeben"

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 4: Willkommenscode 20% (nach Testpaket-Erfassung)**
- [ ] Titel: "Dein 20% Willkommenscode ist bereit!"
- Inhalt: Gutscheincode, wie einlösen, Hinweis auf Erstberatung
- Trigger: Deal Stage = "Testpaket erfasst"
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 5: ERSTBERATUNGSGESPRÄCH & FEEDBACK-GESPRÄCH

**Bereits dokumentiert in HS_Milano_Testpaket_Prozess.md**
- Siehe Phasen 5-8

---

# EINSTIEG 2: WEBSITE-REGISTRIERUNG

## Phase 1: REGISTRIERUNG & PRÜFUNG

**Was passiert:** Friseur registriert sich auf Website mit E-Mail

**Datenfluss:**
```
Website-Registrierung
    ↓
E-Mail bestätigt
    ↓
In Shopware angelegt (Status: "zu prüfen")
    ↓
Marisa erhält Benachrichtigung
    ↓
Marisa prüft: Ist das wirklich ein Friseur?
```

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Website-Registrierung → HubSpot Contact (automatisch)
- ✅ Contact wird in HubSpot angelegt mit Status "zu qualifizieren"
- ✅ Automatische E-Mail an Friseur: "Registrierung erhalten, wir prüfen"
- ✅ Benachrichtigung an Marisa: "Neue Website-Registrierung zu prüfen"
- ✅ Tag in HubSpot: "Website-Registrierung"

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 1: Registrierungs-Bestätigung (automatisch)**
- [ ] Titel: "Deine Registrierung bei HS Milano"
- Inhalt: Bestätigung erhalten, Prüfung läuft, bald geht's los
- Trigger: Website-Registrierung abgeschlossen
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 2: MARISA'S PRÜFUNG

**Verantwortliche:** Marisa

**Ablauf:**
```
Marisa prüft Registrierungsdaten
    ↓
Frage: Ist das wirklich ein Friseur?
    ↓
JA - Qualifizierungscall vereinbaren
    → Marisa setzt Termin ein
    
NEIN - Ablehnung
    → Automatische Ablehnungs-Mail versenden
    → Contact wird als "ungeeignet" getagged
```

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Erinnerung an Marisa: "Prüfung erforderlich" (falls > 1 Tag pending)
- ✅ Kalender-Integration: Marisa kann direkt Qualianruf-Termin buchen
- ✅ Automatische Terminbestätigung an Friseur versenden

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 2: Qualianruf-Termin Bestätigung (manuell durch Marisa)**
- [ ] Titel: "Dein Beratungsgespräch mit Marisa"
- Inhalt: Termin bestätigt, Uhrzeit, Join-Link (Google Meet), Vorbereitung
- Trigger: Manuell durch Marisa (oder automatisch wenn Termin gebucht)
- Status: ⏳ MUSS ERSTELLT WERDEN

**E-Mail 3: Ablehnung (bei Nicht-Friseur)**
- [ ] Titel: "Danke für dein Interesse an HS Milano"
- Inhalt: Höfliche Ablehnung, Grund erklärt, Türe offen lassen
- Trigger: Marisa setzt Status auf "abgelehnt"
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 3: QUALIFIZIERUNGSCALL MIT MARISA

**Verantwortliche:** Marisa

**Aktion im Call:**
1. Kurzes Gespräch führen
2. Motivation abfragen: Warum interessiert sich Friseur?
3. **SPEZIALFALL - Ahmet-Mention:** 
   - "Bist du über einen Post / Empfehlung von Ahmet zu uns gekommen?"
   - Falls JA: Wie Affiliate-Link behandeln (siehe unten)
4. Bei positiv: Weiter zu Phase 4

**Im HubSpot Call-Notes:**
- [ ] Motivation dokumentieren
- [ ] Ahmet-Mention notieren (falls vorhanden)
- [ ] Deal anlegen

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Nach Call automatisch: Deal angelegt mit Stage "Qualifiziert"
- ✅ Tag in HubSpot: "Website-Registrierung-Qualifiziert"
- ✅ Wenn Ahmet erwähnt: Tag "Ahmet-Referral" hinzufügen
- ✅ Benachrichtigung an Tom: "Deal angelegt, nächste Schritte"

**Status:** ⏳ TODO für Tom (Zapier Setup)

---

## Phase 4: MANUELLE REGISTRIERUNG IN SHOPWARE & HUBSPOT

**Verantwortliche:** Tom oder Marisa

**Aktion:**
1. Shopware: Friseur-Account freischalten (Status: aktiv)
2. HubSpot: Deal manuell anlegen
3. Deal Stage: "Qualifiziert" (oder direkt "Erstberatung geplant"?)
4. **SPEZIALFALL - Ahmet-Mention:**
   - Falls Ahmet erwähnt wurde:
     - Shopware: Ahmet als Affiliate zuordnen
     - Behandlung wie "Affiliate-Link-Kunde" (20% auf Erstbestellung)

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Erinnerung an Tom/Marisa: "Shopware + HubSpot manuell anlegen"
- ✅ Checkbox-System: "Shopware: ☐ Angelegt", "HubSpot: ☐ Deal erstellt"
- ✅ Nach Completion: Automatische E-Mail an Friseur: "Du bist freigeschaltet!"

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 4: Freischaltungs-Bestätigung (nach Marisa's Qualianruf)**
- [ ] Titel: "Du bist freigeschaltet! 🎉"
- Inhalt: Willkommen, Shopware-Zugang erklärt, nächste Schritte, Kontaktperson
- Trigger: Deal angelegt + Shopware freigeschaltet
- Status: ⏳ MUSS ERSTELLT WERDEN

**E-Mail 5: Willkommenscode 20% (nach Freischaltung)**
- [ ] Titel: "Dein 20% Willkommenscode ist bereit!"
- Inhalt: Gutscheincode, wie einlösen, Limited Time
- Trigger: Shopware Account aktiv
- Status: ⏳ MUSS ERSTELLT WERDEN

---

# EINSTIEG 3: TELEFON / EMPFEHLUNG

## Phase 1: KONTAKTAUFNAHME

**Wie der Kontakt zu dir kommt:**
- Variante A: Friseur ruft dich direkt an
- Variante B: Bestandskunde schickt Kontakt weiter
- Variante C: Friseur meldet sich, weil er von anderem Friseur empfohlen wurde

**Datenfluss:**
```
Anruf oder E-Mail von Friseur / Bestandskunde
    ↓
Marisa oder Tom empfängt Kontakt
    ↓
Marisa ruft kurz an (falls nicht direkt angerufen)
    ↓
Motivation abfragen
    ↓
Wenn positiv: Erstberatungstermin vereinbaren
```

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Wenn Kontakt via Formular "Bestandskunde empfohlen mich":
  - Automatisch in HubSpot Contact angelegt
  - Tag: "Empfehlung" + "[Name des Empfehlers]"
  - Benachrichtigung an Marisa/Tom
- ✅ Erinnerung: "Qualianruf erforderlich" (1-2 Tage nach Empfehlung)

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 1: Danksagung an Bestandskunde (für Empfehlung)**
- [ ] Titel: "Danke dir für die Empfehlung!"
- Inhalt: Dank aussprechen, wir kümmern uns um deinen Kontakt, evtl. Bonus erwähnen
- Trigger: Neue Empfehlung von Bestandskunde
- Status: ⏳ MUSS ERSTELLT WERDEN

**E-Mail 2: Willkommen (an empfohlenen Friseur)**
- [ ] Titel: "[Name Bestandskunde] hat dich zu uns empfohlen"
- Inhalt: Persönliche Willkommens-Nachricht, dass Freund ihn empfohlen hat, nächste Schritte
- Trigger: Empfehlung eingetroffen
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 2: MARISA'S QUALIFIZIERUNGSCALL

**Verantwortliche:** Marisa (oder Tom)

**Ablauf:**
```
Kurzes Telefonat
    ↓
Fragen:
  - "Wie bin ich auf dich aufmerksam geworden?"
  - "Was ist deine aktuelle Situation?"
  - "Worum geht's dir bei HS Milano?"
    ↓
Wenn passt: "Wollen wir ein Erstberatungsgespräch machen?"
    ↓
Termin vereinbaren
    ↓
In HubSpot dokumentieren
```

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Nach Call automatisch: Deal angelegt
- ✅ Stage: "Qualifiziert" oder "Erstberatung geplant"
- ✅ Call-Notes in HubSpot eintragen (falls Marisa Zeit hat, Notizen zu schreiben)
- ✅ Automatische Terminbestätigung versenden

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 3: Terminerinnerung (vor Erstberatung)**
- [ ] Titel: "Dein Beratungstermin morgen!"
- Inhalt: Erinnerung, Uhrzeit, Join-Link, Agenda
- Trigger: 1 Tag vor Erstberatungstermin
- Status: ⏳ MUSS ERSTELLT WERDEN

---

## Phase 3: MANUELLE REGISTRIERUNG IN SHOPWARE & HUBSPOT

**Verantwortliche:** Tom oder Marisa

**Aktion:**
1. Shopware: Friseur-Account anlegen (evtl. mit Testpaket oder direkt?)
2. HubSpot: Deal anlegen
3. Deal Stage: "Erstberatung geplant"

### 🤖 AUTOMATISIERUNG (Tom - Zapier)

**Was sollte automatisiert werden:**
- ✅ Erinnerung an Tom/Marisa: "Shopware + HubSpot anlegen erforderlich"
- ✅ Nach Completion: Benachrichtigung an Friseur

**Status:** ⏳ TODO für Tom (Zapier Setup)

### 📧 E-MAIL-VORLAGEN ERFORDERLICH

**E-Mail 4: Willkommen (nach Erstberatung positiv)**
- [ ] Titel: "Schön, dich kennenzulernen!"
- Inhalt: Danke für Call, nächste Schritte, Login-Daten (falls sofort aktiv)
- Trigger: Nach Erstberatung positiv
- Status: ⏳ MUSS ERSTELLT WERDEN

---

# 🎯 ZUSAMMENFASSUNG: ALLE E-MAIL-VORLAGEN

## ERFORDERLICH - PRIORITÄT HOCH

| # | Name | Trigger | Einstieg(e) | Status |
|---|------|---------|-------------|--------|
| 1 | Testpaket-Bestätigung | Formular eingereicht | Einstieg 1 | ⏳ TODO |
| 2 | Kontaktversuch-Erinnerung | 3 Tage kein Kontakt | Einstieg 1 | ⏳ TODO |
| 3 | Neukundenmail | Nach Qualianruf positiv | Einstieg 1 | ⏳ TODO |
| 4 | Willkommenscode 20% | Testpaket erfasst | Einstieg 1 | ⏳ TODO |
| 5 | Registrierungs-Bestätigung | Website-Anmeldung | Einstieg 2 | ⏳ TODO |
| 6 | Qualianruf Termin | Nach Prüfung positiv | Einstieg 2 | ⏳ TODO |
| 7 | Ablehnungs-Mail | Keine echter Friseur | Einstieg 2 | ⏳ TODO |
| 8 | Freischaltungs-Bestätigung | Shopware aktiv + HubSpot | Einstieg 2 | ⏳ TODO |
| 9 | Willkommenscode 20% (2) | Nach Freischaltung | Einstieg 2 | ⏳ TODO |
| 10 | Danksagung Empfehlung | Bestandskunde empfiehlt | Einstieg 3 | ⏳ TODO |
| 11 | Willkommen Empfehlener | Empfehlung erhalten | Einstieg 3 | ⏳ TODO |
| 12 | Termin-Erinnerung | 1 Tag vor Erstberatung | Einstieg 3 | ⏳ TODO |
| 13 | Willkommen nach Call | Nach Erstberatung positiv | Einstieg 3 | ⏳ TODO |

---

# 🤖 ZUSAMMENFASSUNG: AUTOMATISIERUNGSPOTENTIALE

## PRIORITÄT: HOCH (Zeitersparnis für Tom)

| Task | Tool | Komplexität | Einstieg(e) | Owner |
|------|------|-------------|-------------|-------|
| Formular → HubSpot Contact | Zapier | Niedrig | 1 | Tom |
| Auto Deal-Erstellung | Zapier | Mittel | 1, 2, 3 | Tom |
| Stage Auto-Updates | Zapier | Mittel | 1, 2, 3 | Tom |
| Erinnerungen & Reminders | Zapier | Niedrig | 1, 2, 3 | Tom |
| Auto Email-Versand | Zapier/HubSpot | Niedrig | 1, 2, 3 | Tom |
| Website-Registrierung → HubSpot | Zapier | Niedrig | 2 | Tom |
| Kontaktversuch-Zähler | Zapier | Mittel | 1 | Tom |

## PRIORITÄT: MITTEL (Nice-to-have)

| Task | Tool | Komplexität | Einstieg(e) | Owner |
|------|------|-------------|-------------|-------|
| Kalender-Integration | Zapier | Mittel | 2, 3 | Tom |
| Ahmet-Tag Auto-Setzen | Zapier | Niedrig | 2, 3 | Tom |
| Call-Notes Auto-Dokumentation | Zapier/Voicemail | Hoch | 1, 3 | Tom |

---

# 📋 NÄCHSTE SCHRITTE

## Für TOM (Automatisierung):
- [ ] Zapier-Flows entwerfen für alle 3 Einstiege
- [ ] Dokumentieren welche Triggers & Actions
- [ ] Mit Marisa Prozesse absprechen
- [ ] Implementieren & testen

## Für MARISA (E-Mail-Vorlagen):
- [ ] Alle 13 E-Mail-Vorlagen entwerfen
- [ ] Mit Tom Templates in Zapier/HubSpot integrieren
- [ ] Testen & optimieren

## Für MARISA & TOM (Prozess-Dokumentation):
- [ ] Leitfaden "Qualianruf" (für Testpaket-Einstieg)
- [ ] Leitfaden "Erstberatung" (für alle Einstiege)
- [ ] Leitfaden "Shopware-Aufnahme" (für Tom)
- [ ] Ahmet-Affiliate-Regeln bei Website-Anmeldung & Empfehlung klären

---

# ⚠️ WICHTIGE REGELN ZU BEACHTEN

## Ahmet-Affiliate bei Website-Registrierung & Empfehlung

**REGEL: Nur wenn Ahmet erwähnt wird**

**Szenario A: Website-Registrierung + Ahmet-Mention**
1. Marisa merkt in Qualianruf: "Ich bin über Ahmets Post zu euch gekommen"
2. → Wie Affiliate-Link-Kunde behandeln
3. → Shopware: Ahmet sofort zuordnen (wenn kein Testpaket)
4. → Shopware: Ahmet entfernen (wenn Testpaket gewünscht)
5. → Nach Testpaket-Erfassung: Ahmet wieder zuordnen

**Szenario B: Empfehlung + anderer Friseur empfohlen**
1. Marisa hört: "Mich hat Friseur XY empfohlen"
2. → Das ist KEINE Ahmet-Affiliate-Situation
3. → Normaler Prozess ohne Ahmet

**Szenario C: Empfehlung + Bestandskunde, der Ahmet-Link nutzer ist**
1. Bestandskunde schickt Kontakt: "Das ist ein Freund von mir"
2. Frage: Nutzt Bestandskunde auch Ahmet-Link?
3. Falls JA: Neuer Friseur kann auch Ahmet-Link bekommen (separate Aktion)
4. Falls NEIN: Normaler Prozess

**REGEL:** Ahmet wird nur bei direktem Bezug zu Ahmet (Post, Empfehlung direkt von Ahmet, oder dessen Affiliate-Link) eingebunden.

