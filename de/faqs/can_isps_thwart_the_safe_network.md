### Können ISP sich dem SAFE-Netzwerk entgegenstellen

Das Netzwerk verwendet verschlüsselte [UDP] (http://en.wikipedia.org/wiki/User_Datagram_Protocol) Nutzlasten, um Daten in dem Netzwerk zu bewegen. Also UDP mit nicht lesbarem Inhalt und schwer von normalem Internet-Verkehr zu unterscheiden. Dies wird es extrem schwierig für ISP machen SAFE Netzwerkverkehr zu erkennen und zu stoppen. Darüber hinaus verbinden alle Nodes zu verschiedenen, zufälligen Ports, d.h.  Portfilterung (eine Art der Zugangskontrolle) wird nicht funktionieren.

### Gibt es eine Möglichkeit Maidsafe zu gefährden oder zu stören, z.B. durch Einrichtung einer sehr großen Anzahl von Computern mit schlechter Upload-Geschwindigkeit aber riesigen Festplatten?

Die Anzahl der Computer müsste sehr viel grösser sein als die Anzahl der Netzwerk Nodes. Wenn ein Node verbindet, wird dessen ID von vorhandenen Nodes verändert und an eine beliebigen Position gesetzt. Es müsste eine bedeutende Anzahl von Nodes hinzufügen werden um mit extrem viel Glück 4 nahe beieinander im Adressraum zu bekommen. Selbst dann könnte der Schaden auf eine einzige chunk Gruppe beschränkt werden.

### Wie geht das Netzwerk mit Datenredundanz um, um sicherzustellen dass die Daten zugänglich bleiben?

Jede Datei wird verschlüsselt und während des Verschlüsselungsverfahrens in chunks aufgeteilt (Self-Encryption). Das Netzwerk hält 4 Kopien jedes verschlüsselten chunks instand und bewegt diese rund um das Netzwerk wenn Nodes ausfallen, sei es durch Betriebsausfall oder Abschalten. Um mit diesem churn fertig zu werden, ist das Netzwerk in der Lage, sich global in kürzester Zeit neu zu konfigurieren (so schnell wie 20 Millisekunden). Diese Schritte sorgen dafür dass Daten immer verfügbar sind, sofern der Benutzer über Zugang zum Internet und die richtigen Anmeldeinformationen verfügt.

###How you deal with the latency inherit in a distributed network like SAFE?

Multiple things facilitate the solution here. Firstly, not one person stores a chunk of data, there are multiple copies of a chunk kept at any given time with a minimum of 4. Furthermore, the network also ranks nodes, for example, if a vault node fails to retrieve a piece of data then a new node replaces it as the holder and the original node gets deranked. If the issue persists, this node will get de-ranked to a point where in future it will not be asked to store any more data. So the network ends up determining which node is effective for storing data. Finally, if a piece of data you’re requesting becomes popular and is retrieved often, it will be cached in more nodes, making the retrieval times even faster. All this will ensure that popular data gets retrieved more quickly

### Wie geht ein verteiltes Netzwerk wie das SAFE Netzwerk mit Latenzzeiten um?

Mehrere Dinge erleichtern die Lösung hier. Erstens speichert nicht eine einzelne Person ein chunk, es gibt zu jeder Zeit mehrere Kopien jedes chunks, mit einem Minimum von 4.
Außerdem bewertet das Netzwerk die Nodes, z.B. wenn ein Node Daten nicht bereitstellt, wird es durch ein neues Node als Datenhalter ersetzt und der original Node wird heruntergestuft. Wenn das Problem weiterhin besteht, wird dieser Node auf einen Rank heruntergestuft, bei dem es keine weiteren Daten zu speichern mehr bekommt. Das Netzwerk ist also in der Lage zu entscheiden welcher Node effizient Daten speichern kann. Schließlich, wenn bestimmte Daten populär sind und oft angefordert werden, so werden diese es in mehreren Nodes im Cache gespeichert werden, so dass sich die Zugriffszeiten sogar verbessern. All dies stellt sicher, dass beliebte Daten schneller abgerufen werden können.

###Why would a distributed network be more secure than a traditional server with the same encryption that you use within SAFE?

This is where physical security plays a big part. Firstly, giving full control of a file to one entity lets them either decrypt it and read it’s content or delete your data. Conversely, decentralisation spreads the data providing multiple sources for each file. Furthermore, actions in the network are also a made based on group consensus, so just one node wanting to do something doesn't enable the task to be completed. Only by majority group agreement are tasks carried out. This makes SAFE extremely robust as the effort to get a group of close nodes together in this network is extremely unlikely.

### Warum sollte ein verteiltes Netzwerk sicherer sein, als ein herkömmlicher Server mit der gleichen Verschlüsselung, die im SAFE netzwerk verwendet wird?

Dies ist, wo die physische Sicherheit eine große Rolle spielt. Erstens ist es riskant, die volle Kontrolle über eine Datei an eine einzelne Instanz zu geben, die dann die Datei entschlüsseln oder löschen könnte. Zweitens werden durch die Dezentralisierung der Daten mehreren Quellen für jede Datei verfügbar. Darüber hinaus werden Aktionen im Netzwerk stets auf einer Basis von Gruppenkonsens durchgeführt, so dass ein einzelner Node alleine keine Aktionen durchführen kann. Nur durch Gruppenkonsens können Aktionen ausgeführt werden. Dies macht das SAFE Netzwerk extrem robust, da es extrem unwahrscheinlich ist eine Gruppe von nahe beieinander liegenden Nodes zusammen zu bekommen.
