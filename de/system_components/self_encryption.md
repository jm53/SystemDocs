# Sicherheit - Selbstverschlüsselung

Sicherheit der Benutzerdaten ist essentieller Bestandteil des SAFE Netzwerkes und wird unter anderem durch den Selbstverschlüsselungsprozess gewährleistet. Das SAFE Netzwerk setzt voraus, dass Daten unkenntlich und widerstandsfähig gegenüber Entschlüsselung sind, auch im Falle einer Kompromittierung eines Verschlüsselungsalgorithmus.

Selbstverschlüsselung wird benutzt, um Daten durcheinander zu bringen und zu verschlüsseln bevor sie ins SAFE Netzwerk gesendet werden. Dieser Prozess ist automatisch und erfolgt unmittelbar.

In dem Moment, in dem Daten auf der virtuellen Festplatte gespeichert werden, kommt es zu einer Zerteilung der Daten in mindestens drei Datenteile, [hashed](http://de.wikipedia.org/wiki/Hashfunktion) die dann verschlüsselt werden. Um die Daten weiter zu verschleiern wird jedes Teil der Daten mit Hilfe der Hashes anderer Datenteile durch eine [XOR](http://de.wikipedia.org/wiki/Kontravalenz) Funktion geschleust. Jedes Datenteil wird dann in zweiunddreissig Teile aufgeteilt und Schlüsselpaare werden dann zu einer Tabelle auf dem Computer des Benutzers hinzugefügt, der sogenannten Datenkarte. Diese Datenkarte enthält die Positionen jedes Datenteils die zu einer Datei gehören. Die Datenkarte, mit Hashes vor und nach der Verschlüsselung, wird benutzt wenn die Daten geholt und entschlüsselt werden, da der Verschlüsselungsprozess nicht reversibel ist.

Dieser komplette Prozess findet auf dem Client statt, so dass die Daten im Netzwerk immer verschlüsselt sind und nur Benutzer mit den korrekten Anmeldedaten die Daten entschlüsseln können. Das bedeutet auch, dass Passwörter niemals aus dem Netzwerk gestohlen werden können, da sie den Computer des Benutzers niemals verlassen. Für zusätzliche Sicherheit sorgt die Verschlüsselung der Datenkarte, die ebenfalls die Selbstverschlüsselung durchläuft.

Das SAFE Netzwerk nutzt [Deduplikation](http://de.wikipedia.org/wiki/Deduplikation) um sicherzustellen das Platz effizient genutzt wird wenn mehrfache Kopien von Daten gespeichert werden, die mehrfach verschlüsselt wurden. Das Netzwerk ist in der Lage eindeutige Datenteile zu identifizieren in dem es die Hashes der einzelnen Datenteile miteinander vergleicht. Wie in [2.2.2](http://maidsafe.net/SystemDocs/system_components/guaranteed_vault_identification.html) beschrieben, benutzen Vaults ebenfalls Hashes um sich zu identifizieren.

[Klicke hier für ein Video das Selbstverschlüsselung erklärt (englisch) ](https://www.youtube.com/watch?v=Jnvwv4z17b4)

Hier ist ein Überblick über den Selbstverschlüsselungsprozess.

![Self encryption figure](./img/self-encryption.png)
