# Wie es funktioniert.

Wenn ein Benutzer den SAFE client herunterlädt und installiert, wird ein Vault auf seinem Computer konfiguriert.

Nach dem Beitritt und Anmelden am SAFE Netzwerk sieht der Benutzer eine virtuell eingebunde Festplatte in seinem System. Diese Festplatte zeigt die statischen Daten an, die verschlüsselt und verteilt auf den anderen Vaults liegen.

Der Vault des Benutzers kann ausserdem dynmische Daten wie z.B Kommunikation über VoIP handhaben.

Die Daten werden vor der Speicherung im SAFE Netzwerk automatisch verschlüsselt. Dieser Selbstverschlüsselungsprozess besteht aus dem Aufteilen der Daten in kleine Teile und anschliessendem Verschlüsseln dieser Teile mit den Anmeldedaten des Benutzers und den Daten selbst. Das bedeutet, dass für eine Entschlüsselung der Daten durch Dritte, diese die sicheren Anmeldedaten des Benutzers und Wissen über den speziellen Datenteil haben müssten. Keine dieser Informationen existiert auf Systemen oder Servern von Drittanbietern.

Typischerweise verbindet sich ein Benutzer mit dem Netzwerk durch einen Router. Der Router verwendet das "Reliable UDP (RUDP) Protocol" um sich mit dem Netzwerk zu verbinden. RUDP ist ein stabilieres Protokoll als UDP da verlorene Pakete noch einmal gesendet werden und es im Gegensatz zu TCP im Stande ist NAT Router zu durchqueren. Die Verwendung von RUDP im SAFE Netzwerk erlaubt es, Daten durch Router zu schleusen ohne dabei korrumpiert oder abgefangen zu werden.

Der Vault des Benutzers verbindet sich mit anderen Vaults als Teil des Speicherns und Verwaltens von Daten. Die Vaults werden konstant anhand der folgenden Kritieren überprüft und klassifiziert (durch die Datenhaltungsverwaltung)

* **Verfügbarkeit** - Wie oft der Vault an oder aus ist
* **Speicher** - Wieviel Speicher der Vault besitzt
* **CPU** - Wieviel CPU Ressourcen der Vault hat
* **Bandbreite** - Wie schnell oder langsam der Zugang zum Vault ist

Wenn Bedarf und Verfügbarkeit von Ressourcen sich im SAFE Netzwerk verändern, passt der Vault sich dementsprechend an und gleicht die Last im Netzwerk konstant aus. Dieser Anpassungsprozess wird automatisch durch die Vaults vorgenommen. Da das SAFE Netzwerk komplett autonom arbeitet, kann es sehr schnell und ohne menschliche Hilfe reagieren.

Wenn ein Benutzer mehr Speicherlatz zur Verfügung stellt als er selber benötigt, so wird er nach dem Zufallsprinzip mit safecoins dafür belohnt. Safecoins sind notwendig, um Zugang zum Netzwerk zu erhalten. Wieviele Safecoins ein Benutzer hat, kann er durch einen Blick auf seine Geldbörse erfahren. Die Geldbörse wird automatisch im Zuge der SAFE Client Installation und des Anmeldeprozesses angelegt.

Software Entwickler verdienen Safecoins wenn sie Programme für das SAFE Netzwerk entwicklen. Sobald die Programme genutzt werden, verdienen die Entwickler damit Safecoins.

Entwickler des SAFE Netzwerks können ebenfalls Safecoins verdienen in dem sie zu Code des SAFE Netzwerks beitragen.
