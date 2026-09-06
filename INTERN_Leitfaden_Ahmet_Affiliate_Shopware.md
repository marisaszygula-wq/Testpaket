# Interner Leitfaden: Ahmet Affiliate-Management in Shopware
## Für: Marisa & Tom

---

## 📋 ÜBERSICHT DER SZENARIEN

Es gibt 3 Hauptszenarien, in denen wir die Affiliate-Zuordnung in Shopware verwalten müssen:

1. **Kunde über Ahmet's Link + kauft direkt** → Keine Änderungen
2. **Kunde über Ahmet's Link + will Testpaket** → Entfernen → Wieder hinzufügen
3. **Kunde auf Ahmet's Empfehlung + will Testpaket** → Erst nach Test hinzufügen

---

## SZENARIO 1: Kunde über Link + kauft direkt

**Aktion:** KEINE – der Kunde bleibt automatisch Ahmet zugeordnet

**Ablauf:**
1. Kunde kommt über Ahmet's Affiliate-Link
2. Kunde ist automatisch in Shopware Ahmet zugeordnet
3. Kunde kauft direkt (kein Testpaket)
4. ✅ Ahmet bekommt 20% Provision

**Deine Aufgabe:** Nichts – Automation läuft!

---

## SZENARIO 2: Kunde über Link + will kostenloses Testpaket

**⚠️ WICHTIG: AFFILIATE-ZUORDNUNG MUSS ENTFERNT & SPÄTER WIEDER HINZUGEFÜGT WERDEN**

### Phase 1: Kunde klickt Link & will Testpaket

**Zeitpunkt:** Wenn Kunde sagt "Ich möchte Testpaket"

**Aktion in Shopware:**
1. Öffne Shopware Admin
2. Gehe zu: Kunden → [Kundenname suchen]
3. Im Kundenprofil: Affiliate-Zuordnung anschauen
4. ❌ **Entferne Ahmet als Affiliate** (setze auf "Kein Affiliate" oder leer)
5. **Speichern!**

**Grund:** Damit Ahmet nicht 20% von 0€ verdient, wenn das Testpaket kostenlos ist.

### Phase 2: Tom erfasst kostenloses Testpaket

**Zeitpunkt:** Wenn Tom das Testpaket in Shopware anlegt

**Aktion in Shopware (durch Tom):**
- Testpaket wird ohne Ahmet als Affiliate angelegt
- Dealstage in HubSpot: "Testpaket erfasst"
- ✅ Weiter zu Phase 3

### Phase 3: Nach Testpaket-Erfassung - Ahmet wieder hinzufügen

**Zeitpunkt:** Direkt nach erfolgreicher Testpaket-Erfassung durch Tom

**Aktion in Shopware:**
1. Öffne Shopware Admin
2. Gehe zu: Kunden → [Kundenname suchen]
3. Im Kundenprofil: Affiliate-Felder
4. ✅ **Ordne Ahmet wieder als Affiliate zu**
5. **Speichern!**

**Ergebnis:** Wenn Kunde später kauft, bekommt Ahmet 20% Provision ✅

---

## SZENARIO 3: Kunde auf Ahmet's Empfehlung + will Testpaket

**Aktion:** ERST NACH TESTPAKET-ERFASSUNG HINZUFÜGEN

### Phase 1: Kunde meldet sich an (mit Ahmet-Empfehlung)

**Zeitpunkt:** Kunde füllt Formular/Website/Telefon aus

**Aktion:**
- Ahmet kontaktiert dich/Tom: "Dieser Kunde kommt von mir!"
- ❌ **Du fügst Ahmet NOCH NICHT als Affiliate hinzu!**
- Kunde wird normal angelegt (ohne Ahmet)

### Phase 2: Tom erfasst kostenloses Testpaket

**Zeitpunkt:** Wenn Tom das Testpaket in Shopware anlegt

**Aktion in Shopware (durch Tom):**
- Testpaket wird ohne Ahmet als Affiliate angelegt
- Dealstage in HubSpot: "Testpaket erfasst"
- ✅ Weiter zu Phase 3

### Phase 3: Nach Testpaket-Erfassung - Ahmet hinzufügen

**Zeitpunkt:** Direkt nach erfolgreicher Testpaket-Erfassung durch Tom

**Aktion in Shopware:**
1. Öffne Shopware Admin
2. Gehe zu: Kunden → [Kundenname suchen]
3. Im Kundenprofil: Affiliate-Felder
4. ✅ **Ordne Ahmet als Affiliate zu**
5. **Speichern!**

**Ergebnis:** Wenn Kunde später kauft, bekommt Ahmet 20% Provision ✅

---

## SZENARIO 4: Kunde auf Ahmet's Empfehlung + kauft direkt (KEIN Testpaket)

**Aktion:** SOFORT HINZUFÜGEN

**Ablauf:**
1. Ahmet sagt: "Dieser Kunde will direkt kaufen, kommt von mir"
2. ✅ **Füge Ahmet sofort als Affiliate ein** in Shopware
3. Kunde legt Bestellung auf
4. ✅ Ahmet bekommt 20% Provision

---

## 🔧 SHOPWARE TECHNICAL GUIDE

### Wie man Affiliate in Shopware verwaltet:

**Affiliate HINZUFÜGEN:**
```
1. Admin Dashboard öffnen
2. Menü: Kunden
3. Kundenname suchen & öffnen
4. Scrolle zum Feld "Affiliate" oder "Partner"
5. Wähle aus: "Ahmet" (oder wie der Account heißt)
6. SPEICHERN (Button oben rechts)
```

**Affiliate ENTFERNEN:**
```
1. Admin Dashboard öffnen
2. Menü: Kunden
3. Kundenname suchen & öffnen
4. Scrolle zum Feld "Affiliate" oder "Partner"
5. Wähle: "Kein Affiliate" oder leer
6. SPEICHERN (Button oben rechts)
```

**Status überprüfen:**
```
1. Admin Dashboard öffnen
2. Menü: Kunden
3. Kundenname suchen & öffnen
4. Scrolle zum Feld "Affiliate"
5. Angezeigt wird: Wer ist aktuell zugeordnet
```

---

## 📊 CHECKLIST FÜR TESTPAKET-PROZESS

### Wenn Kunde Testpaket will (egal ob über Link oder Empfehlung):

**SCHRITT 1 - QUALIANRUF (Verkäufer):**
- [ ] Kunde angerufen & qualifiziert
- [ ] Termin für Erstgespräch vereinbart
- [ ] Dealstage: "Tom - Testpaket erfassen"

**SCHRITT 2 - VOR TESTPAKET-ERFASSUNG (Marisa/Tom):**
- [ ] Hat Kunde Ahmet-Link verwendet?
  - [ ] JA → Ahmet-Zuordnung in Shopware **ENTFERNEN**
  - [ ] NEIN → Nichts tun
- [ ] Kunde ist vorbereitet für Testpaket

**SCHRITT 3 - TESTPAKET ERFASSEN (Tom):**
- [ ] Kunde in Shopware angelegt (ohne Ahmet!)
- [ ] Kostenloses Testpaket erfasst
- [ ] Dealstage: "Testpaket erfasst"

**SCHRITT 4 - NACH TESTPAKET-ERFASSUNG (Marisa/Tom):**
- [ ] ✅ Ahmet als Affiliate **HINZUFÜGEN** in Shopware
- [ ] Willkommenscode-Mail mit 20% versendet
- [ ] Erstberatungsgespräch-Termin notiert

**SCHRITT 5 - FEEDBACK-GESPRÄCH:**
- [ ] Kunde hat getestet
- [ ] Entscheidung getroffen

**SCHRITT 6 - WENN KUNDE KAUFT:**
- [ ] Bestellung angelegt
- [ ] ✅ Ahmet bekommt automatisch 20% Provision
- [ ] Dealstage: "Kaufvertrag geschlossen"

---

## ⚠️ HÄUFIGE FEHLER - VERMEIDEN!

❌ **FEHLER 1: Ahmet-Zuordnung nicht entfernen**
- Problem: Ahmet verdient 20% von 0€ beim kostenlosen Test
- Lösung: Immer entfernen, bevor Test erfasst wird!

❌ **FEHLER 2: Ahmet-Zuordnung vergessen wieder hinzuzufügen**
- Problem: Ahmet bekommt keine 20% auf erste Bestellung
- Lösung: Direkt nach Testpaket-Erfassung hinzufügen!

❌ **FEHLER 3: Kunde über Empfehlung + Ahmet sofort eintragen (bei Testpaket)**
- Problem: Ahmet verdient 20% von 0€ beim kostenlosen Test
- Lösung: Nur NACH Testpaket-Erfassung hinzufügen!

---

## 📞 KOMMUNIKATION MIT AHMET

### Ahmet sollte wissen:
- ✅ Er kann live sein Dashboard checken (Shopware Partnerprogramm)
- ✅ Wenn sein Name verschwindet & wieder auftaucht = normal (wegen Testpaket)
- ✅ Er bekommt Bescheid, wenn ein Kunde kauft

### Ahmet muss NICHT wissen:
- ❌ Die technischen Shopware-Details
- ❌ Dass wir seine Zuordnung entfernen & wieder hinzufügen
- ❌ Interne Prozesse

### Was du Ahmet mitteilst:
"Dein Name ist kurzzeitig aus dem System raus, weil der Kunde Testpaket machen will. Nach dem Test ordnen wir dich wieder zu. Im Partnerprogramm-Dashboard siehst du den aktuellen Status jederzeit!"

---

## 🎯 ZUSAMMENFASSUNG DER ACTIONS

| Szenario | Vor Testpaket | Nach Testpaket |
|----------|---------------|----------------|
| Link + Testpaket | ❌ Entfernen | ✅ Hinzufügen |
| Link + direkt kaufen | ✅ Bleibt | ✅ Bleibt |
| Empfehlung + Testpaket | ❌ Nicht hinzufügen | ✅ Hinzufügen |
| Empfehlung + direkt kaufen | ✅ Hinzufügen | ✅ Bleibt |

---

## 📧 SCHNELL-REFERENZ

**Problem: Kunde will Testpaket, kommt über Ahmet's Link**
→ Sofort: Ahmet-Zuordnung entfernen in Shopware
→ Nach Test: Ahmet-Zuordnung wieder hinzufügen

**Problem: Kunde will Testpaket, Ahmet empfohlen ihn**
→ Vor Test: Ahmet NICHT hinzufügen
→ Nach Test: Ahmet hinzufügen

**Problem: Kunde kauft direkt, kommt über Ahmet**
→ Sofort: Ahmet hinzufügen
→ Nichts mehr tun

