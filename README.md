# Newtron Bestell-Assistent (Demo)

KI-gestützter Bestell-Chat als einzelne HTML-Datei – gebaut per Vibe Coding als Demo für einen Management-Termin.
Bestellungen werden in natürlicher Sprache aufgegeben; die Bestellübersicht rechts aktualisiert sich live.

## Starten

`index.html` im Browser öffnen (Doppelklick genügt). Kein Build, kein Backend.

- **Demo-Modus (Standard):** läuft sofort, auch offline, mit eingebauter regelbasierter Spracherkennung.
- **KI-Modus:** Zahnrad oben rechts → Claude-API-Schlüssel eintragen. Dann versteht der Assistent beliebige
  Formulierungen (auch Englisch). Der Schlüssel liegt nur im `localStorage` dieses Browsers.
  Fällt die API aus, übernimmt automatisch der Demo-Modus.

## Funktionen

- Freitext-Bestellungen: Mengen, Artikel, Termine („bis nächsten Freitag“, „in 2 Wochen“) und Standorte
- Rückfragen bei mehrdeutigen oder unbekannten Artikeln mit klickbaren Alternativen
- Änderungen per Chat („Mach aus den 50 lieber 80“, „Entferne die Netzteile“)
- Lagerprüfung mit Hinweis auf Teillieferung
- Zusammenfassung → Bestätigung → Bestellnummer `NT-<Jahr>-XXXX`
- Bestellhistorie mit Status-Badges und Kennzahlen

## Sicherer Demo-Pfad

1. Chip „Ich brauche 50 M12-Stecker …“ klicken → zwei Positionen, Termin und Adresse werden erkannt.
2. `Mach aus den 50 lieber 80` → Menge ändert sich live.
3. `Wir brauchen Netzteile, so 15 Stück` → Rückfrage, dann „Hutschienen-Netzteil 24 V / 10 A“ wählen → **Lagerwarnung** (nur 8 auf Lager).
4. „Bestellung abschließen“ → Zusammenfassung → „Bestellung bestätigen“ → Bestellnummer, Eintrag in der Historie.

## Anpassen

Produktkatalog, Lieferadressen und Beispiel-Anfragen stehen oben im `<script>` von `index.html`
(`CATALOG`, `ADDRESSES`, `EXAMPLES`). Die Primärfarbe steht in `--primary` im CSS.

> Prototyp mit fiktiven Beispieldaten – kein produktionsreifes System. Nächste Schritte wären ERP-Anbindung,
> Rechte/Rollen, Datenschutz, serverseitige API-Anbindung und Tests.
