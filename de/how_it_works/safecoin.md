#Safecoins

Safecoins können verdient, getauscht oder gekauft werden. Der Wert von Safecoins wird durch den Markt bestimmt, durch eine Kombination aus Nachfrage und Angebot.

## Markt Preis

Die Anzahl an Safecoins im Umlauf erhöht sich mit steigender Nutzung des Netzwerks. Fast alle frühen Besitzer von Safecoins werden Farmer sein, die mit der Bereitstellung von Ressourcen sowohl Liquidität als auch Verteilung des Vermögens erzeugen. Es wird davon ausgegangen, dass fast alle Benutzer mindestens einige wenige Safecoins in ihrer Geldbörse haben werden.

Benutzer können ihre Safecoins gegen Dienste im Netzwerk, Geld (oder andere digitale Währungen) tauschen, in dem sie eine Börse benutzen. Der Anteil an Safecoins die gespeichert werden (in neuen Geldbörsen) gegenüber dem Anteil der Farmern zugeteilt wird, bestimmt den Preispunkt. Dieser Preispunkt wird den Marktwert von Safecoins festlegen.



## Ressourcen und Währung

Safecoins werden genutzt, um Zugang zu Dienstleistungen im SAFE Netzwerk zu erhalten. Dies fördert eine konstante Wiederverwendung, was in einer gesteigerten Nachfrage nach einer limitierten Ressource resultiert. Dies wiederum führt dazu, dass der Wert der Safecoins mit der Zeit steigt. Während die Safecoins ansich im Wert steigen, steigt auch die Zahl der Netzwerk Dienste (Ressourcen) die sie kaufen. Siehe dazu Bild 2.


![](safecoin resources.png)

## Farming Raten

Farming ist ein Prozess bei dem Benutzer dem Netzwerk Ressourcen (Festplattenplatz, Prozessorleistung und Bandbreite) bereitstellen.

Wie in Bild 1 zu sehen ist, basiert der Safecoin Verdienst Algorithmus auf der Sigmoid Kurve. Dies bedeutet, dass Vaults mit geringer Kapazität eine geringe Anzahl Safecoins verdienen. Diese Rate steigt, wenn der Farmer mehr Ressourcen nahe des Netzwerk Durchschnitts zur Verfügung stellt. Die Verdienstrate berücksichtigt ausserdem den Rang des Vaults, ein Prozess bei dem das Netzwerk die Nützlichkeit jedes Vaults von 0 (schlechteste) bis 1 (beste) bewertet. Die Safecoin Farming Rate ist letztlich das Resultat der Netzwerk Rate, der Balance zwischen Angebot und Nachfrage im Netzwerk, multipliziert mit dem Rang des Vaults. Die Netzwerk Rate wird bei 200% über Durchschnitt anfangen abzuflachen und damit die Existenz riesiger Vaults benachteiligen, welche Zentralisierung in den Farming Prozess würden. Safecoin wird ihnen vom Netzwerk zugeteilt und wird den erfolgreichen Nodes ausgezahlt wenn Daten von ihnen abgerufen werden (GETS), im Gegensatz dazu, wenn Daten gespeichert werden (PUTS).


![](safecoin farming speed.png)

Das Netzwerk erhöht die farming Vergütung wenn Platz erforderlich ist und senkt sie wenn Platz im Überfluss vorhanden ist. Daten sind gleichmäßig über das Netzwerk verteilt, daher sollten Farmer die ihren Verdienst maximieren wollen, mehrere durchschnittliche Vaults betreiben anstatt eines hochleistungs Vaults.


## Safecoin Transfer Mechanismus
Im Gegensatz zu bitcoin nutzt das SAFE Netzwerk keine blockchain um den Besitz der Safecoins zu verwalten. Die Transaction Manager des SAFE Netzwerks sind unverkettet, was bedeutet, dass lediglich der letzte und der aktuelle Besitzer von Safecoins bekannt sind. In dieser Hinsicht ist es sinnvoll Safecoins wie digitales Bargeld zu betrachten.

Eines der größten Probleme jeder virtuellen Währung ist das Problem der doppelten Ausgabe (double spending) zu verhindern. Innerhalb des SAFE Netzwerks ist der Transfer von Daten, inklusive Safecoin, atomar, unter Verwendung einer kryptographischen Signatur um den Besitz zu übertragen.

Safecoin, die Währung des SAFE Netzwerks wird in Relation zur Netzwerk Nutzung generiert. Wenn Daten gespeichert werden, oder Programme erstellt und genutzt werden, generiert das Netzwerk Safecoins, jedes mit seiner eigenen ID. Da diese Coins teilbar sind, erhält jede Denominierung eine neue und komplett eindeutige ID.

Wenn das Netzwerk den Benutzern Safecoins zuweist, kann nur dieser spezielle Benutzer den Besitz mit Hilfe der kryptographischen Signatur übertragen. Für illustrative Zwecke: wenn Alice mit dem Client einen Safecoin an Bob bezahlt reicht sie eine Zahlungsanfrage ein. Der Transaction Manager überprüft, ob Alice der derzeitge Besitzer der Safecoins ist, indem er ihre öffentlichen Schlüssel heranzieht und bestätigt, dass sie von dem richtigen und korrespondierenden privaten Schlüssel signiert wurde. Der Transaction Manager akzeptiert nur eine signierte Nachricht vom existierenden Besitzer. Dies belegt zweifelsfrei, dass Alice der Besitzer der Safecoin ist und der Besitz dieser speziellen Safecoin wird an Bob übertragen. Von nun an ist lediglich Bob dazu in der Lage die Safecoin an einen anderen Besitzer zu übertragen. Dieser Prozess ist in Bild 3 dargestellt.


![](safecoin transfer mech.png)
