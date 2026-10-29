# Kampfinsel Flottensync

Rechner für das Browsergame [Kampfinsel](https://kampfinsel.com): Mehrere Flotten – von verschiedenen Inseln, mit
verschiedenen Schiffen – kommen zur selben Sekunde (oder mit festem Zeitabstand) am Ziel an.

**Live:** https://henges89.github.io/kampfinsel-flottensync/

## Benutzung
1. Zielkoordinaten eintragen (`Ozean:Gitter:Insel`).
2. Pro Flotte Startinsel und langsamstes Schiff wählen. Optional: Ankunft relativ zu den anderen in Sekunden (z. B. `-5` = 5 s früher).
3. Unter „Meine Schiffsgeschwindigkeiten“ deine eigenen Werte eintragen (Flottenseite im Spiel, Spalte „Geschwindigkeit“) – sie hängen von Hafen und Segel-Forschung ab.
4. Ankunft und Methode (Drosseln oder Startzeiten staffeln) wählen – der Startplan zeigt Absendezeit, Countdown und Drosselung.

Alles läuft lokal im Browser; es werden keine Daten gesendet. Einstellungen werden im Browser (localStorage) gespeichert.

## Entfernungsformel
Alle Ozeane liegen auf einer gemeinsamen Ebene (Ozeannummer = Reihe·10 + Spalte):
`X = 2·(Gitter + 10·Reihe)`, `Y = 0,4·(Insel + 50·Spalte)`, Entfernung = √(ΔX² + ΔY²); Reisezeit = Entfernung ÷ Geschwindigkeit.
Geprüft an über 680 Spiel-Entfernungen und Reisezeiten (max. Abweichung 0,05 sm). Die Drosselung (50–100 %) ist als umgekehrt proportionale Reisezeit angenommen.

Inoffizielles Fan-Tool, nicht mit Kampfinsel verbunden.
