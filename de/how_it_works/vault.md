# Vaults
Vaults werden auf dem Computer des Benutzers erstellt wenn sie den SAFE client installieren und dem SAFE Netzwerk beitreten.

Der Vault auf dem Computer des Benutzers kann nicht vom Benutzer gesehen werden. Stattdessen sieht er ein virtuell eingebundes Laufwerk das ihm Zugang zu seinen verteilten Daten gibt.

Wenn ein Benutzer Dateien auf seinem virtuellen Laufwerk erstellt oder verändert, geht die Datei durch verschiedene Prozesse um sicherzustellen, dass das File sicher ist und eine bestmögliche Nutzung der SAFE Netzwerk Ressourcen erfolgt.



## Vault Rolle
Vaults können verschiedene Datenhandhabungsrollen annehmen. Jede Rolle hat eine bestimmte Funktion im SAFE Netzwerk.

* **Client managers**<br/>
Client Manager Vaults erhalten die chunks der selbst-verschlüsselten Daten vom Vault des Benutzers.
* **Data managers**<br/>
Diese Vaults verwalten die chunks vom Client Manager Vault. Sie überwachen ausserdem den Status des SAFE Netzwerkes.
* **Data holders**<br/>
Data holder Vaults halten die chunks bereit.
* **Data holder managers**<br/>
Data holder Managers überwachen die Data holder Vaults. Sie berichten dem Data Manager, wenn chunks korrupt oder verändert sind. Sie berichten ausserdem, wenn ein Data Holder offline geht.
* **Vault Managers**<br/>
Der Vault manager hält die Software auf dem neuesten stand und den Vault am Laufen und startet ihn im Fehlerfall neu.
* **Transaction Managers**<br/>
The Transaction Manager hilft die Safecoin Transfers zu verwalten.

## Daten im SAFE Network

Es werden 2 Mechanismen vom Netzwerk verwendet, die den Client des Benutzers dazu authorisieren, bestimmte Aktionen durchführen zu dürfen. Authorität wird immer dann durch Gruppen Konsens erreicht, wenn ein Client neue Daten speichert. Alternativ werden [Digitale Signaturen](https://de.wikipedia.org/wiki/Digitale_Signatur) verwendet, wenn der Client z.B. bereits bestehende Daten ergänzt (eine Version) oder Safecoins sendet.

** Gruppen Konsens**<br/>
Wenn ein Benutzer versucht, neue Daten zu speichern, wird die Datei im Rahmen des self-encryption Prozesses verschlüsselt, in chunks aufgesplittet und dann an eine Gruppe von Client Managern in der Nähe gesendet. Diese in der Nähe befindliche Gruppe besteht aus den vault IDs die am nächsten zur Vault ID des Benutzers sind, im Sinne von [Kontravalenz](https://de.wikipedia.org/wiki/Kontravalenz). Diese Distanz wird im mathematischen Sinne, nicht im geografischen, gemessen. Mindestens 28 der 32 Client Manager müssen zu einem Konsens kommen bevor eine Netzwerk Operation durchgeführt wird.

Der Client Manager sendet die chunks an 32 Data Manager, ausgewählt durch das Netzwerk da ihre IDs am nächsten zu den IDs der chunks sind. Demnach legt die chunk ID auch die Lage im Netzwerk fest.

Das Netzwerk nutzt einen scatter/gather Ansatz, basierend auf [Rabin’s Information Dispersal Algorithm](http://people.seas.harvard.edu/~salil/rabin2011-slides/rabin2011-mitzenmacher.pdf) der einen Datenverlust von bis zu 4 Teilen möglich macht, ohne dass Daten neu übertragen werden müssen.

Sobald es zu einem Konsens gekommen ist, gibt der Data Manager die Datenteile an 32 Data Holder Manager weiter. Diese wiederum geben die Datenteile zum Speichern an die Data Holder weiter. Wenn ein Data Holder Manager einen Data Holder als offline meldet, entscheidet der Data Manager, basierend auf dem Rang der dem Vault zugeordnet ist, in welchem Vault die chunks gespeichert werden sollen.

Auf diesem Weg werden die chunks der originalen Datei konstant überwacht und unterstützt, um sicherzustellen das der Benutzer die ursprünglichen Daten entschlüsseln und auf diese zugreifen kann.

Jede Bewegung von chunks kann nur mit einem Konsens von 28 der 32 umgebenden Vaults erfolgen. Die Vaults können nicht in Isolation handeln.

Jedwede Kommunikation im SAFE Netzwerk wird durch zusammenliegende Gruppen von 32 Nodes ausgeführt. Dies hindert feindselige Nodes daran, sich bösartig zu verhalten. Es ist für einen Benutzer nicht möglich sich eine eigene ID auszusuchen oder zu entscheiden wo seine Daten gespeichert werden - das wird vom Netzwerk berechnet. Jedes Mal wenn ein Node vom Netzwerk getrennt wird und sich wieder verbindet, bekommt es eine neue und zufälige ID.


[Klicke hier für ein kurzes Video wie Vaults funktionieren (english)](https://www.youtube.com/watch?v=txvKSeCaEP0)

** Kryptographische Signaturen**<br/>

Wenn Benutzer Änderungen an existierenden Daten vornehmen, z.B. den Inhalt einer Datei ändern oder einem anderen Benutzer Safecoin senden, so nutzt das Netzwerk nicht den Gruppen Konsens da dieser Layer an Komplexität und erhöhter Netzwerk Last nicht erforderlich ist.

Kryptographische Signaturen können ohne Zweifel den Besitzer von jeglichen Daten mathematisch validieren, vorausgesetzt der Benutzer hat seinen privaten Schlüssel sicher verwahrt. Wenn der Benutzer den Besitz von einer Datei nachweisen kann, indem er seine Anfrage mit seinem privaten Schluessel signiert, so gewährt ihm das Netzwerk Zugriff, um die Daten zu verändern.
