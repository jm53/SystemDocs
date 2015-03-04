# Safecoin Aufträge und Rollen

Es gibt verschiedene Safecoin Typen von Aufträgen

* PUT - wird genutzt um safecoins (data) an einen bestimmten Ort zu legen
* GET - wird genutzt um safecoins (data) von einem bestimmten Ort zu holen
* EXCHANGE - wird genutzt um safecoins (data) zwischen zwei bestimmten Orten auszutauschen

Safecoins sind ein weiterer Datentyp und hat im SAFE Netzwerk PUT und GET Aufträge definiert. Jedoch sind im Gegensatz zu normalen Daten keine DELETE Aufträge verfügbar.

Die PUT Auftrag für Safecoins hat die "keine Vervielfältigung erlaubt" Eigenschaft. Das bedeutet das wenn es bereits einen Safecoin mit gleichem Namen (die ersten 32 bits) gibt, dann wird der PUT Auftrag zurückgewiesen. Diese Überprüfung wird vom Data Manager gehandhabt der den Auftrag erhält.

Ein EXCHANGE erlaubt dem Anforderer die Details des Safecoin zu aktualisieren, unter der Voraussetzung das er den folgenden Regeln folgt:

* Eigentümer ist von einer Mehrheit der Drittanbieter Vaults anerkannt (Treuhänder)
** Eigentümer kann (vorheriger und derzeiter Eigentümer
Owner can (previous and current owners considered as approved themselves) update all fields.**

* Jeder Drittanbieter Vault (Treuhänder) kann seine jeweiligen Felder nur einmal aktualisieren
* Jedes Mal wenn das vorherige und aktuelle Besitzer Feld aktualisiert werden, muss die Safecoin Version um eins erhöht werden und alle Treuhänder Felder werden gelöscht.

Die genannten Regeln werden von dem Pmid Manager, der die Safecoin Daten vorhält, erzwungen. Das Eigentümerfeld wird zusammen mit den Drittanbieter Vault (Treuhänder) Feldern als Transaktion genutzt, der Pmid Manager wird damit effektiv zum Transaktions Manager. In diesem Fall können die Safecoin Daten auch als Empfangsobjekt angesehen werden.

