# Changelog

## 1.2.0
- Meldet ein Gerät (z. B. der ACE) länger als 4 Abfrageintervalle nichts, setzt das Add-on seinen Status auf offline: Die Entitäten in HA stehen dann auf „nicht verfügbar“ statt alte Werte weiter anzuzeigen. Mit dem nächsten Bericht ist das Gerät wieder online.
- Konfigurierte Geräte werden jetzt auch dann regelmäßig abgefragt, wenn sie beim Start des Add-ons noch nicht geantwortet hatten.

## 1.1.0
- Keine doppelten Entitäten mehr: Werte, die der ACE vom Hub spiegelt (Akku, SOC-Grenzen, Restzeiten), erscheinen nur noch beim Hub; AC-Modus und Input Limit nur noch beim ACE. Solar-Eingang des ACE heißt jetzt „ACE Solar …“. Batterien nur noch beim ACE (vorher doppelt mit `_2`). Bereits angelegte Duplikate werden beim Start entfernt.

## 1.0.0
- Erste Version: Hub 2000 und ACE 1500 als zwei Geräte über lokales MQTT, gleiches Skript wie das Hyper-Add-on.
