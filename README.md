# BluePrismUebung
Repo für den Austausch der exportierten Speicherstände inkl. Dokumentation


# Dependencies
Externe Business Objekte werden unter utils/ bereitgestellt. Quellen:
- https://github.com/blue-prism/pop3-smtp-utility
- https://github.com/blue-prism/file-management-utility
- https://github.com/blue-prism/collection-manipulation

#Dokumentation

##1	Beschreibung und Problemstellung
Im Rahmen der Veranstaltung „Geschäftsprozessmanagement 2“ stellte die Partnerfirma ComTS eine Automatisierungsaufgabe, um die gelernten theoretischen Inhalte des Moduls zu verfestigen. In dieser Aufgabe sollte eine Gruppe aus ca. fünf Studierenden gemeinsam einen Prozess innerhalb der Software „Blue Prism“ automatisieren, diesen technisch und formal dokumentieren und eine Präsentation vorbereiten.
1.1	Case-Beschreibung
Der Case „Recherche zur Ermittlung von Berechtigten für Finanzhilfen“ beschreibt die automatische Suche von potentiellen Unternehmen, welche eine Corona-Hilfe an Ansprüch nehmen können, und die Vorbereitung von Informationsbriefen. Für den Prozess wird eine Mail mit einem Anhang bereitgestellt. Im Anhang befindet sich eine CSV-Tabelle, deren Inhalt aus Kombinationen von Branchen und Postleitzahlen bildet. Anhand dieser Postleitzahlen sollen automatisch die entsprechenden Unternehmen aus https://www.dastelefonbuch.de/ herausgesucht und zwischengespeichert werden. Um zu verhindern, dass Unternehmen, die bereits einen Antrag auf Finanzhilfe gestellt haben, erneut angeschrieben werden, wird ein Abgleich der zwischengespeicherten Unternehmen mit einer Liste von Kundendaten abgeglichen. Die bereinigte Liste mit den zu informierenden Unternehmen wird im letzten Schritt weiterverarbeitet, in dem eine Word-Vorlage mit den relevanten Informationen befüllt wird. Diese Dateien werden in einer .zip-Datei an eine festgelegte E-Mail-Adresse gesendet. Damit ist der Prozess abgeschlossen.

1.2	Problemstellung
Die wesentlichen Herausforderungen bei der Umsetzung waren die Analyse der Internetseite sowie die Befüllung der Word-Vorlage.
Zur Recherche im Internet war es erforderlich, ein Business Object zu erzeugen und …
Die Generierung der Informationsschreiben erforderte …
 
##2	Aufgabenverteilung und Projektorganisation
Das Projekt wurde von den Studierenden selbstständig in drei wesentliche Bestandteile gegliedert: Eingabe, Verarbeitung, Ausgabe. Die Dokumentation des Projektes wurde untereinander in die entsprechenden Kompetenzbereiche aufgeteilt, um die präziseste fachliche Beschreibung zu gewährleisten.

Die Eingabe der Daten, bearbeitet von Felix Brockschnieder und Benedikt Kaiser, umfasste die Tätigkeiten:

-	E-Mail-Empfang
-	Auslesen des Anhangs
-	Verarbeitung jeder Zeile der CSV:
o	Aufruf der Internetseite mit entsprechenden Parametern
o	Auslesen der Ergebnisse
o	Speicherung der Unternehmen in einer Queue
-	Fertigstellen des Eingabeprozesses
-	Fehlerhandling

Folgende Tätigkeiten sind für die Bearbeitung des Datenabgleichs durch Florian Göhring getätigt worden:

-	Lesen der Elemente aus der Queue
-	Abgleich des Queue-Elements mit der vorgegebenen Collection
-	Auswahl des Elementes, falls es nicht in der Collection vorkommt
-	Erstellung einer neuen Queue für die zu informierenden Unternehmen

Um den identifizierten zu informierenden Unternehmen ein adäquates Anschreiben zu generieren, übernahmen Oleg Chapaykin und Ravel Siirde die Aufgaben der Ausgabe:

-	Lesen der Elemente aus der Queue
-	Eingabe-Algorithmus in der Word-Vorlage
-	Erstellung des Dokumentenarchivs
-	Senden des Archivs an die definierte Mailadresse

Am Ende der individuellen Bearbeitung der Cases wurden die Teilprozesse zusammengefügt, um eine einzelne Ausführung des automatisierten Prozesses zu ermöglichen. 

Die Kommunikation im Projekt fand primär über das Tool „Discord“ statt. Für die Konzepterstellung, Fragendokumentation und Zeichnungen diente „Microsoft OneNote“ als kollaboratives Notizen-Tool.  

##3	Lösungsprozess
###3.1	Aufgabenteilung
###3.2	Schnittstellenfestlegung
###3.3	Bereichslösungen
####3.3.1	Eingabe
####3.3.2	Verarbeitung
####3.3.3	Ausgabe
###3.4	Zusammenführung
###3.5	Fragen und Probleme

##4	Referenzprozess und Modellierung
