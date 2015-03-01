# Garantierte Vault Identifikation

Vault Identifikation ist essentiell in dem Fall das Vaults messbar für das Ressourcen Management verantwortlich sind.

Ohne Identifikation könnte ein Vault sich als jemand anderes ausgeben. Es gibt bekannte Methoden, um digitale Identitäten zu idenfizieren, wie z.B. Zertifikats Authoritäten (Verisign) oder in manchen Fällen Vertrauensnetze (Web of Trust). Da das SAFE Netzwerk keine Server oder menschliche Beteiligung hat und komplett vertrauenslos ist, stehen diese Optionen nicht zur Verfügung.

Der Vault Identifikationsprozess besteht aus der Erstellung von zwei Schlüsselpaaren. Ein Schlüsselpaar ist ein Annulierungsschlüssel der lediglich zur Erstellung und Löschung eines echten Schlüssels notwendig ist.

Das echte Schlüsselpaar wird erstellt und der öffentliche Schlüssel wird vom privaten Annulierungsschlüssel signiert und dieses Paket (öffentlicher Schlüssel + Signatur) wird dann im Netzwerk als Vault Identifikations Schluesseltyp gespeichert. Dieser Hash wird dann als Vault Idenfitkation benutzt.

Das SAFE Netzwerk kann dieses Identifikationspaket bei Bedarf von jedem Vault abrufen. Der einzige Weg dieses Packet zu verändern ist durch eine Nachricht, signiert von der selben ID die das Paket signiert hat.

Dieser Prozess erlaubt es allen Vaults sich zu idenfizieren indem sie den Hash ihres Identifikationspakets, den sie erstellt und gespeichert haben, nach aussen kommunizieren.

Da lediglich der Ersteller den privaten Schlüssel, dessen öffentlicher Schlüssel im Identifizierungspaket enthalten ist, besitzt, kann davon ausgegangen werden, das dies der richtige Vault ist. Alle Nachrichten sind mit dieser ID verschlüsselt, so dass betrügerische Vaults nicht in der Lage sind Nachrichten zu entschlüsseln, inklusive Verbindungsanfragen welche notwendig sind um sich mit dem Netzwerk zu verbinden.
