BauManager Rüeggisberg – Version 0.6

Diese erste Version ist ein lokaler Offline-Prototyp, KEINE Cloud-Anwendung.

Schnelltest: index.html in einem Desktop-Browser öffnen. Browser-Speicher kann bei file:// eingeschränkt sein.
Empfohlen: Ordner mit einem lokalen Webserver bereitstellen, z.B. im Ordner: python -m http.server 8000
Dann http://localhost:8000 öffnen. Für PWA-Installation und Service Worker ist localhost oder HTTPS nötig.

Daten werden lokal im Browser (localStorage) gespeichert. JSON-Export regelmässig als Sicherung herunterladen.
Import ersetzt alle lokalen Daten. Nicht mehrere Geräte parallel nutzen: keine Synchronisation.

Noch nicht implementiert: Cloud-Login, Benutzerfreigaben, geräteübergreifende Synchronisation, Konfliktlösung, tatsächliche Datei-Uploads, automatische Backups, erweiterte Bauzeitplanung.
Dokumentenregister enthält derzeit nur Verweise, keine gespeicherten Dateien.

Keine realen Verträge oder sensiblen Dokumente in dieser Testversion speichern.

Version 0.2: Bauzeitenplan, Gewerke, Handwerker und Mängel aus der Benutzeroberfläche entfernt. Alte Datensätze bleiben in bestehenden Sicherungen erhalten.

Version 0.3: Die sechs sichtbaren Rubriken sind farblich unterschieden (Navigation, Überschriften, Karten und Tabellen). Datenformat und Speicherkennung unverändert.

VERSION 0.5 – Finanzverwaltung vereinfacht
Die Finanzmaske enthält Kostenposition, Unternehmen, Budget CHF, Effektive Kosten CHF und Bezahlt CHF.
Die Finanzübersicht zeigt Budgetabweichung und noch offene Beträge.
Bisherige Einträge werden automatisch übernommen: Effektive Kosten = bisher Vergeben + Nachträge.
Die alten Werte bleiben in der Datensicherung erhalten.
WICHTIG: Vor dem Versionswechsel eine JSON-Sicherung aus der bisherigen App exportieren.
Falls die neue Version unter einer anderen Adresse oder als andere lokale Datei geöffnet wird,
die Sicherung in der neuen Version importieren. Browserdaten werden nicht automatisch übertragen.

NEU in Version 0.6: Finanzpositionen unterstützen beliebig viele Unterpositionen.
Bei einer Hauptposition auf «Unterpositionen» klicken, Details eingeben und speichern.
Sobald Unterpositionen erfasst sind, berechnen sich Budget, effektive Kosten und Zahlungen
für die Hauptposition und das Dashboard aus der Summe ihrer Unterpositionen.
Die früheren Hauptbeträge bleiben gespeichert und werden wieder berücksichtigt, wenn
alle Unterpositionen gelöscht sind. Vor dem Wechsel bitte JSON-Datensicherung exportieren.

VERSION 0.8 – UNTERPOSITIONEN
Bei jeder Unterposition können neu mehrzeilige Bemerkungen und ein Produktlink (http/https) hinterlegt werden. Links erscheinen unter der Unterposition und öffnen sich in einem neuen Tab. Beide Felder werden lokal und in JSON-Exporten gespeichert. Vor dem Wechsel auf Version 0.8 Daten in der bisherigen Version als JSON exportieren. Danach in der neuen Version importieren, falls Browser/Dateipfad den bisherigen Speicher nicht wiederverwendet.

Version 0.8: Loeschen ueber zwei Klicks bestaetigen (auch auf iOS).

VERSION 0.9 – FINANZEN NACH GEBÄUDEBEREICH
Jede Hauptkostenposition kann einem Gebäudebereich (Untergeschoss, Erdgeschoss,
Obergeschoss, Galerie usw.) zugeordnet werden. Eigene Bereiche sind möglich.
Die Finanzübersicht gruppiert Positionen nach Bereichen und zeigt Bereichssummen.
Über den Filter können einzelne Bereiche angezeigt werden. Unterpositionen,
Bemerkungen und Produktlinks bleiben erhalten. Alte Einträge erscheinen unter
„Nicht zugeordnet“ und lassen sich nachträglich zuweisen.
Bitte vor dem Wechsel eine JSON-Sicherung der bisherigen Version exportieren.

Version 1.0: Bis zu fünf Bilder je Unterposition bei den Bemerkungen. Bilder werden verkleinert, lokal gespeichert und in der JSON-Datensicherung mitgesichert. Speicherplatz im Browser ist begrenzt.

Version 1.1: In Offerten kann pro Eintrag eine PDF (max. 2 MB) angehängt, ersetzt, entfernt und heruntergeladen werden. Die PDF wird in der lokalen JSON-Datensicherung gespeichert. Browser-Limits können bei vielen PDFs erreicht werden.

VERSION 1.2 – PDF-Vorschau für iPad HTML-Viewer
PDF-Button verwendet keine Blob-URL und keinen externen Download mehr, sondern eine eingebettete PDF-Vorschau (iframe mit Data-URI).
Hinweis: Manche iOS-HTML-Viewer sperren auch eingebettete Data-URIs. In diesem Fall die App in Safari auf einem HTTPS-Server öffnen. Die Sperre ist eine Sicherheitsfunktion des Viewers, nicht der App.

VERSION 1.3 – HTTPS/PWA-Paket für GitHub Pages. PDF-Öffnung als Blob-URL über anklickbare Links und Download-Fallback; Manifest-Icons und Offline-Cache aktualisiert. Siehe ANLEITUNG_GITHUB_PAGES.txt.
