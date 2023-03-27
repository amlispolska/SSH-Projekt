# Dienste - Präsentationsnotizen

**Telnet / SSH / RDP / TeamViewer / VNC / etc.**

## Aufgabenstellung

Sie arbeiten bei der „do-IT-all Systemhaus GmbH“, die Netzwerklösungen für 
mittelständige Unternehmen plant und implementiert.

Ihr Teamleiter stellt wiederholt fest, dass es für praktisch jeden 
Netzwerkdienst innerhalb seines Teams einen Fachmann gibt, was aber in der 
Vergangenheit zu Engpässen führte, wenn der jeweils erforderliche Fachmann 
bereits durch andere Projekte gebunden war.

Ihr Teamleiter beschließt daher eine firmeninterne Schulung durchzuführen, bei 
der die einzelnen Team-Mitglieder in Zweier-Gruppen jeweils einen Netzwerkdienst 
auf fachlich hohem Niveau mit Blick auf etwaige Implementationsmöglichkeiten und
auf absehbare „Fallstricke“ für das gesamte Team vorstellen.

Erstellen Sie Ihren Schulungsbeitrag in Partner-/Gruppenarbeit für den Ihnen 
zugewiesenen Netzwerkdienst. Mit Abschluss der Erarbeitungsphase stellen Sie 
alle Schulungs-Quell-Unterlagen zur Verfügung und setzen den genauen zeitlichen 
Umfang Ihres Schulungsbeitrags fest (für Vortrag und „Hands-on“-Szenario ohne 
Frage-Runde). 

Abgabetermin: Am Mittag des 09.04.2023 (elektronische Unterlagen + avisierter 
zeitlicher Umfang)

Alle vorbereiteten Unterlagen inkl. avisiertem Zeitraster per eMail an 
Ruediger.Klimkeit@bkukr.de

Ihr Teamleiter konkretisiert den inhalt für die Netzwerkdienste-Schulungen wie 
folgt: 

---
## Aufbau der Präsentation

- Vortrag im zeitlichen Umfang von ca. 15 Minuten in Form einer entsprechenden 
Präsentation
- Anschließende Fragerunde
- "Hand-Out" für die Team-Mitglieder als geeignete inhaltliche Zusammenfassung
- Hands-on Szenario im zeitlichen Rahmen von 15 bis 45 Minuten, das allen 
Team-Mitgliedern in Eigenarbeit ermöglicht, den jeweiligen Dienst 
kennenzulernen: 
	- Entweder durch Nutzung/Debugging des entsprechenden Dienstes oder 
	(bzw. Zusätzlich) durch das eigenhändige Bereitstellen des Dienstes
- Quiz von mindestens 3-5 Fragen inkl. Musterlösungen, wobei jede Frage mit 1-5 
Punkten einzuszufen ist (5 Punkte bei hoher Relevanz und hoher Schwierigkeit)
- Elektronische Bereitstellung aller Schulungs-Quell-Unterlagen zur Archivierung 
auf dem Firmen-Server
---

## Notizen/Recherche

### Quellen: 
- [Secure Shell (Wikipedia)](https://de.wikipedia.org/wiki/Secure_Shell)
- [Telnet Definition](https://www.computerweekly.com/de/definition/Telnet)
- [RDP (Wikipedia)](https://de.wikipedia.org/wiki/Remote_Desktop_Protocol)


### Notes zur Präsi:

**Überschrift: Eine Einführung in Fernwartungsprotokolle**
1. Einleitung
	- Welches Thema?
	- Inhalt/Aufbau der Präsi? (Inhaltsverzeichnis)
	- Oberflächlich andere Protokolle
	- Hauptfokus auf SSH

2. Vorstellung einzelner Protokolle
	- Telnet
		- Dienst für den Virtuellen Zugriff auf einen Computer und für 
		  die Bereitstellung einer Bidirektionalen, textbasierten 
		  Kommunikationsverbindung zwischen zwei Computern
		- Sollte nicht verwendet werden, da übertragene Daten nicht
		  verschlüsselt werden (Weder der Login noch der Rest der 
		  Kommunikation)
	- RDP
		- Remote Desktop Protocol: Proprietäres Netzwerkprotolkoll für 
		  den Fernzugriff auf (meist WIndows-)Computer. 
		- Ermöglicht die Übertragung grafischer Inhalte eines remote 
		  Rechners und die Bereitstellung der Peripherie eines 
		  Arbeitsplatzes (Tastatur, Maus, Audio-IO, Viedoeingabe, 
		  Clipboard, Drucker und Filesystembereitstellung)
		- Verfolgt ein Server/CLient-Modell: Auf einem Gerät laufen die 
		  sog. "Remote Desktop Services", auf anderen geräten die 
		  Clientkomponente, die eine Verbindung mit diesem Service 
		  aufbauen kann. 
		- Minimum an Input wird an gesteuertem Gerät gesendet und 
		  minimum an Ausgabe (bsp. *Framebuffer/Output der Grafikkarte*) 
		  wird an das Steuernde Gerät gesendet
		- Wurde in Konkurrenz zum Open-Source VNC-Protokoll entwickelt. 
		- VNC
			- Virtual Network Computing
			- Seit den 90s bei UNIX VNC ein für RDP-Ähnliches 
			  X11-Protokoll
			- Stark von RDP abweichende technische Implementierung, 
			jedoch mit gleichem Ziel
			- VNC implementiert das Remote Framebuffer Protocol und 
			ist damit plattformunabhängig

3. Secure Shell (SSH)
- Kryptographisches Netzwerkprotokoll für den Sicheren Betrieb von 
  Netzwerkdiesnten
- In Erster Linie als sicherer Ersatz von Telnet in Verwendung
	- Auch für den Dateiaustausch (sFTP (FTP via SSH) genutzt)
- Verfolgt auch das Client-Server Modell:
	- Eine SSH-Client-Anwendung verbindet sich mit einem SSH-Server. 
- Es werden zwei verschiedene SSH-Spezifikationsversionen unterschieden: SSH-1 
  und SSH-2
- Die IANA hat dem Protokoll den TCP-Port 22, UDP-Port 22 und SCTP-Port 22 
  zugeordnet 

- Entstand 1995 als Reaktion auf die Nachfrage nach drop-in Alternativen zu 
  UNIX's Berkeley Services bzw. deren Befehle rsh, rcp und rlogin
- Erste Version als Freeware

4. TeamViewer
	- Fernwartungssoftware für Kontrollierten zugriff
	  auf andere Rechner.
	- Erfordert die TeamViewer software auf beiden geräten.
	- Baut eine TCP-UDP verbindung über den Port 5938 auf.
	- End to End verschlösselung mit RSA und AES

- Hands-On-Szenario (SSH): 
	1. Linux Server VM über Beamer, ein Freiwilliger richtet unter 
	   Einleitung den SSH-Dienst ein
	2. In Einzelarbeit können dann alle versuchen, sich per SSH auf jene 
	   Linux-VM einzuloggen. Um vorzuweisen, dass sie die Verbindung 
	   erfolgreich übernommen haben, müssen sie eine Textdatei auslesen. 
	   Diese ist die Lösung für eine der Aufgaben. 
