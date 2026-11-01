# Changelog

## 1.4.0
- Batterien automatisch vom Hub, wenn der ACE fehlt: Ist der ACE offline (oder gar nicht vorhanden), kommen die Batteriewerte aus den Daten des Hub 2000. Die Batterie-Entitäten bleiben dieselben (am ACE), nur die Quelle wechselt; ist der ACE zurück, liefert wieder er. Hub 2000 ohne ACE zeigt seine Batterien jetzt selbst an.
- Batterien gehen nicht mehr mit dem ACE auf „nicht verfügbar“, sondern erst, wenn 4 Abfrageintervalle lang weder Hub noch ACE Werte liefern (HA `expire_after`, greift auch nach Neustart).
- Ohne eingetragene `ace_device_id` übernimmt ein gefundener ACE die Batterien nur, wenn der Hub „mit ACE verbunden“ meldet.

## 1.3.0
- ACE 1500: „AC Modus“ zeigt jetzt den Netzstrom-Betriebsmodus aus der Zendure-App: „Normal (aus nach 10 min)“, „Niemals ausschalten“, „Automatisch abschalten (Zeit)“. Im Modus „Normal“ schaltet sich der ACE bei weniger als ca. 20 W AC-Last nach 10 Minuten komplett ab und ist danach offline. Mit „Niemals ausschalten“ bleibt er dauerhaft verbunden. Bisher standen dort die Hyper-Bezeichnungen (Aus / AC Laden / AC Entladen).

## 1.2.0
- Meldet ein Gerät (z. B. der ACE) länger als 4 Abfrageintervalle nichts, setzt das Add-on seinen Status auf offline: Die Entitäten in HA stehen dann auf „nicht verfügbar“ statt alte Werte weiter anzuzeigen. Mit dem nächsten Bericht ist das Gerät wieder online.
- Konfigurierte Geräte werden jetzt auch dann regelmäßig abgefragt, wenn sie beim Start des Add-ons noch nicht geantwortet hatten.

## 1.1.0
- Keine doppelten Entitäten mehr: Werte, die der ACE vom Hub spiegelt (Akku, SOC-Grenzen, Restzeiten), erscheinen nur noch beim Hub; AC-Modus und Input Limit nur noch beim ACE. Solar-Eingang des ACE heißt jetzt „ACE Solar …“. Batterien nur noch beim ACE (vorher doppelt mit `_2`). Bereits angelegte Duplikate werden beim Start entfernt.

## 1.0.0
- Erste Version: Hub 2000 und ACE 1500 als zwei Geräte über lokales MQTT, gleiches Skript wie das Hyper-Add-on.
