# Effiziente Selbst Authentifizierung

Das SAFE NEtzwerk unterstützt Selbst-Authentifizierung. Dies ist ein Mechanismus, der es Benutzern erlaubt Konten im SAFE Netzwerk zu erstellen und sich einzuloggen ohne dabei auf Drittanbieter zurückgreifen zu müssen.

Um das zur erreichen müssen die Authentifizierungsprivilegien (login token) als Teil des Selbst-Authentifizierungprozesses im SAFE Netzwerk gespeichert werden.

Ein Benutzer erstellt seinen eigenen Schlüssel (K) und Passwort (W). Ein
[salt](https://de.wikipedia.org/wiki/Salt_%28Kryptologie%29) (S) wird in reproduzierbarem Weg vom Schlüssel und Passwort abgeleitet.

Um dann einen eindeutigen Identifikator zu erzeugen, wird ein Hash aus dem zusammengesetzten Schlüssel und dem Salt erzeugt, H(K+S).

Ein "Password Based Key Derivation File (PBKDF2)" wird benutzt um das Passwort zu verstärken. Dies ist notwendig, da Passwörter die von Benutzern gewählt werden in der Regel schwach sind.

Zuletzt wird die veschlüsselte Zugangsberechtigung mit folgender Struktur im SAFE Netzwerk gespeichert:


**Speicher im Netzwerk [H(K+S)] Symmetrische Verschlüsselung [ PBKDF2[P][S] ] (Konto)**

Selbst-Authentifizierung verlässt sich auf ein System, in dem der Vault einen eindeutigen Schlüssel erstellen kann um einen Wert im SAFE Netzwerk zu speichern. Der Wert, der in diesem Schlüssel gespeichert ist, sollte ein verschlüsselten Pass zu den Daten enthalten.

Dieser Pass enthält kryptographisch gesicherte Schlüssel und/oder eine Liste von anderen Schlüsseln um sich die zu speichernden oder teilenden Informationen zu Nutze zu machen.

Der Ort dieses initialen Schlüssels ist im SAFE Netzwerk maskiert oder zumindest nicht offensichtlich. Diese Vorgehensweise ist die Basis für Selbst-Authentifizierung und ist in das SAFE Netzwerk integriert. Dies ist wichtig, um den Zugang zu Daten zu erlauben und sie öffentlich zu speichern ohne die zusätzliche Anforderung einer Firewall oder Zugangskontrollen.

##Anmeldeinformation erraten

Ein Angreifer oder feindliche Person im Netzwerk kann die Präsenz eines Benutzers testen und seinen Login token herunterladen. Das ist ähnlich zu kontinuierlichem Testen eines Passwortes auf einem zentralen Server. In zentralen Servern wird dies durch verringern der Anmeldeversuche erreicht.

Wenn ein Benutzer im SAFE Netzwerk einen Login Token anfordert, so erhält er einen. Ungültige Tokens werden bei jedem Versuch geliefert. Das bedeutet das ein Angreifer Millionen verschiedene und stark verschlüsselte Login Tokens entschlüsseln muss. Dieser Prozess sollte solche Attacken rechenbetont unpraktikabel machen.

Der Login Token ist nur für die Authentifizierung nützlich, nachdem er mit Hilfe des Passwortes und der Benutzer Details validiert wurde, welche niemals in das SAFE Netzwerk gesendet werden.
