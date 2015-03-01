# Router mit Verbindungen in zwei Richtungen
Das SAFE Netzwerk erlaubt Kommunikation zwischen Vaults.

Viele Heimverbindungen werden von Routern vorgenommen die private Adressen bereitstellen, welche nicht im Internet erscheinen können. Ein hingänglich bekannter Mechanismus ist die Verwendung von [STUN](http://de.wikipedia.org/wiki/Session_Traversal_Utilities_for_NAT) Servern.

Dieser Mechanismus ist in einem dezentralen Netzwerk nicht akzeptabel. Im SAFE Netzwerk wird RUDP auf eine Art und Weise verwendet die einen dezentralen STUN Server emuliert. Verteilte Hashtabellen (DHT) stellen dazu Verbindungsinformationen für die verhandelden Vaults bereit.

Das SAFE Netzwerk kann Router Verbindungen handhaben, ohne das der Benutzer die Verbindung durch seinen Router anpassen muss.
