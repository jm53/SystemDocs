### Können ISP sich dem SAFE-Netzwerk entgegenstellen

Das Netzwerk verwendet verschlüsselte [UDP] (http://en.wikipedia.org/wiki/User_Datagram_Protocol) Nutzlasten, um Daten in dem Netzwerk zu bewegen, d.h. UDP mit nicht lesbarem Inhalt und schwer von normalem Internet-Verkehr zu unterscheiden. Dies macht es extrem schwierig für ISPs SAFE Netzwerkverkehr zu erkennen und zu stoppen. Darüber hinaus verbinden sich alle Nodes zu verschiedenen, zufälligen Ports, d.h.  Portfilterung (eine Art der Zugangskontrolle) wird nicht funktionieren.

### Gibt es eine Möglichkeit Maidsafe zu gefährden oder zu stören, z.B. durch Einrichtung einer sehr großen Anzahl von Computern mit schlechter Upload-Geschwindigkeit aber riesigen Festplatten?

Die Anzahl der Computer müsste sehr viel grösser sein als die Anzahl der Netzwerk Nodes. Wenn ein Node sich verbindet, wird dessen ID von vorhandenen Nodes verändert und an eine beliebigen Position gesetzt. Es müsste eine bedeutende Anzahl von Nodes hinzugefügt werden um mit extrem viel Glück 4 nahe beieinander im Adressraum zu bekommen. Selbst dann könnte der Schaden auf eine einzige chunk Gruppe beschränkt werden.

### Wie geht das Netzwerk mit Datenredundanz um, um sicherzustellen dass die Daten zugänglich bleiben?

Jede Datei wird verschlüsselt und während des Verschlüsselungsverfahrens in chunks aufgeteilt (Self-Encryption). Das Netzwerk hält 4 Kopien jedes verschlüsselten chunks instand und bewegt diese rund um das Netzwerk wenn Nodes ausfallen, sei es durch Betriebsausfall oder Abschalten. Um mit diesem churn fertig zu werden, ist das Netzwerk in der Lage, sich global in kürzester Zeit neu zu konfigurieren (20 Millisekunden als schnellste Zeit). Diese Schritte sorgen dafür dass Daten immer verfügbar sind, sofern der Benutzer über Zugang zum Internet und die richtigen Anmeldeinformationen verfügt.


### Wie geht ein verteiltes Netzwerk wie das SAFE Netzwerk mit Latenzzeiten um?

Mehrere Dinge erleichtern die Lösung hier. Erstens speichert nicht eine einzelne Person ein chunk, es gibt zu jeder Zeit mehrere Kopien jedes chunks, mit einem Minimum von 4.
Außerdem bewertet das Netzwerk die Nodes, z.B. wenn ein Node Daten nicht bereitstellt, wird dieser Node durch ein neuen als Datenhalter ersetzt und der original Node wird heruntergestuft. Wenn das Problem weiterhin besteht, wird dieser Node auf einen Rang heruntergestuft, bei dem es keine weiteren Daten zu speichern mehr bekommt. Das Netzwerk ist also in der Lage zu entscheiden welcher Node effizient Daten speichern kann. Schließlich, wenn bestimmte Daten populär sind und oft angefordert werden, so werden diese die Daten in mehreren Nodes im Cache speichern, so dass sich die Zugriffszeiten sogar verbessern. All dies stellt sicher, dass beliebte Daten schneller abgerufen werden können.



### Warum sollte ein verteiltes Netzwerk sicherer sein, als ein herkömmlicher Server mit der gleichen Verschlüsselung, die im SAFE netzwerk verwendet wird?

Hier spielt die physische Sicherheit eine große Rolle. Erstens ist es riskant, die volle Kontrolle über eine Datei an eine einzelne Instanz zu geben, die dann die Datei entschlüsseln oder löschen könnte. Zweitens werden durch die Dezentralisierung der Daten mehreren Quellen für jede Datei verfügbar. Darüber hinaus werden Aktionen im Netzwerk stets auf einer Basis von Gruppenkonsens durchgeführt, so dass ein einzelner Node alleine keine Aktionen durchführen kann. Nur durch mehrheitlichen Einigung der Gruppe können Aktionen ausgeführt werden. Dies macht das SAFE Netzwerk extrem robust, da es extrem unwahrscheinlich ist eine Gruppe von nahe beieinander liegenden Nodes zusammen zu bekommen.
