# Resourcennachweis

Ressourcennachweis erlaubt dem Netzwerk Aktionen oder Services mit Hilfe von mathematisch verfizierbaren Mechanismen zu validieren.

Dieser Prozess misst die Fähigkeit eines Vaults Datenteile zu empfangen und zu speichern. Folgende Computer Kriterien spielen dabei eine Rolle:


* CPU Geschwindigkeit
* Bandbreitenverfügbarkeit
* Festplattenplatz
* Online Zeit

Dies erlaubt dem Nachweis eine nützliche, messbare und sofort verifizierbare Instanz zu sein. Resourcennachweis ist ein sehr effizienter Mechanismus ohne jegliche Transaktionsgebühren.

Resourcennachweis im SAFE Netzwerk nutzt einen Mechanismus ähnlich dem [Zero-Knowledge-Beweis](http://de.wikipedia.org/wiki/Zero-Knowledge-Beweis). In diesem Fall braucht der Mechanismus zur Überprüfung nicht den Inhalt der Daten zu kennen, sondern verifiziert, dass Daten tatsächlich auf korrekte Art und Weise vorgehalten werden.

Resourcennachweis erfolgt nach einer Reihe von Schritten.

1. Eine Überprüfungsgruppe aus Vaults erstellt einen zufälligen Strang
2. Dieser zufällige Strang wird verschlüsselt an alle Halter der Daten gesendet
3. Der Datenhalter fügt diesen Strang den original Daten hinzu und hashed das Ergebnis
4. Das Ergebnis wird von der Überprüfungsgruppe gesammelt, entschlüsselt und verglichen
5. Wenn ein Vault ein abweichendes Ergebnis zurückliefert wird davon ausgegangen das dieser kompromitiert ist und wird abgewertet.

Dieser Mechanismus wird bei sog. "Get" Anfragen und während Kontentransfers ausgelöst. Er ist nichtdeterministisch und zufallsgesteuert, ausgelöst bei Nutzung durch den Benutzer. Er wird als sicher betrachtet und nutzt "Zero-Knowledge", nicht um Inhalte zu verbergen (da jeder nach allen Daten anfragen kann), sondern um sicherzustellen das jedwede Daten die kontaminiert sind nicht übertragen werden.

Hier ist eine Übersicht über den Ressourcennachweis Prozess.

![Proof of resource figure](./img/por-diagram.png)
