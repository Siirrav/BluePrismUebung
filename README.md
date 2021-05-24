# BluePrismUebung
Repo für den Austausch der exportierten Speicherstände

# Dependencies
Externe Business Objekte sind werden unter utils/ bereitgestellt. Wir sollten jedoch die Quellen (Repos) hier sammeln:
- https://github.com/blue-prism/pop3-smtp-utility
- https://github.com/blue-prism/file-management-utility
- https://github.com/blue-prism/collection-manipulation

# Beschreibung
Die Lösung des Cases basiert auf ein klassisches "Eingabe-Verarbeitung-Ausgabe"-System. Zunächst werden die Daten aus der Quelle bezogen, anschließend werden sie gegengeprüft und verarbeitet und schließlich in vordefinierter Form ausgegeben.

## Eingabe
**Hier euer Part ^^**

## Verarbeitung
Für die Gegenprüfung von Unternehmen, die bereits einen Antrag gestellt haben, ist initial eine Collection dieser Unternehmen in den Prozess zu geben. Die zu prüfenden Unternehmen stehen in einer Queue bereit.

Zunächhst wird geprüft, ob ein Element erfolgreich aus der Queue *PotentialCompanys* bezogen wurde. Ist dies nicht der Fall, z.B. weil keine Elemente vorhanden sind oder alle abgearbeitet wurden, endet der Prozess. Sind noch verfügbare Elemente vorhanden, wird die eigentliche Prüfung durchgeführt. Dazu wird die Unternehmens-ID (*Company ID*, **nicht** die GUID, da diese immer eineindeutig für das zu verarbeitende Element ist) in der Collection *CompanysWithRequest* gesucht. Ist der Eintrag in der Spalte *Company ID* vorhanden, wird der Wert "Requested" auf *True* gesetzt, das Unternehmen wird mit einer Exception in der Queue abgeschlossen und das nächste Element der Queue wird aufgerufen. Ist das Unternehmen aber noch nicht in der Liste der Antragssteller, wird das Unternehmen in die nächste Queue *CompanysWithoutRequest* kopiert und steht damit für die Bearbeitung der Ausgabe zur Verfügung.
Der Vorteil der zwei Queues besteht darin, dass parallel mehrere Recheneinheiten darauf zugreifen können, um die Aufträge schneller abzuarbeiten. Außerdem kann die Ausgabe direkt auf die für Sie relevante Queue mit den Elementen zugreifen, sobald diese verfürbar sind.

## Ausgabe
