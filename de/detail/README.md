# Bibliotheken

Das SAFE Netzwerk besteht aus 9 individuellen Bibliotheken. Die folgende Sektion, gedacht für den technisch versierten Leser, bietet eine detailierte Erklärung welche Rolle jede Bibliotheken und wie sie funktionieren

Der Code jeder Bibliothek ist im [GitHub repository](https://github.com/maidsafe) von Maidsafe zu finden. Es gibt die folgenden Bibliotheken:

1. Common - eine Bibliothek aus Utility Funktionen
2. Passport - stellt eine selbst zertifizierende Public Key Infrastructure (PKI) bereit, unabhängig von den Anforderungen jeglicher zentraler Verzeichnisse.
3. RUDP - Implementierung von "Reliable UDP"
4. Routing - Routing ist eine Distributed Hash Table (DHT) Bibliothek die auf Kademlia ähnlichen Routing Tabellen beruht.
5. Encrypt - SAFE Encrypt verwirklicht Funktionen die für die Selbstverschlüsselung von Dateien und Ordnern zuständig sind.
6. Drive - SAFE Drive ist ein virtuelles Laufwerk das es erlaubt Informationen von jedem Speichermedium, inklusive Netzwerk Dateisystemen, zu speichern und abzurufen.
7. Network Filesystem - behandlet das SAFE Netzwerk als ein Dateisystem und legt ein pseudo "Restful Interface" (GET PUT POST DELETE) dar.
8. Vault Manager - Datenspeicher, Datentypen und der Lifestuff Manager.
9. Vault - Selbstheilung, Selbstverwaltung und voll verteiltes Netzwerk.

