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
1. Telnet
	- *Teletype Network*
	- Entwckelt 1969 im Rahmen des ARPANET
		- Ziel: Rechenzeit, Anwendungen und Datenbanken remote nutzen
		  können
		- Erster einsatz 1974
	- Dienst für den Virtuellen Zugriff auf einen Computer und für
	  die Bereitstellung einer Bidirektionalen, textbasierten
	  Kommunikationsverbindung zwischen zwei Computern
	- Sollte nicht verwendet werden, da übertragene Daten nicht
	  verschlüsselt werden (Weder der Login noch der Rest der
	  Kommunikation)
2. RDP
	- Remote Desktop Protocol: Proprietäres Netzwerkprotolkoll für
	  den Fernzugriff auf (meist WIndows-)Computer.
	- Entwickelt 1998 von Microsoft basierend auf die von Microsoft
	  lizensierte Citrix-Technik Multiwin
	- Verfügbar ab WindowsNT 4.0 bzw. Windows XP SP-1
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
3. VNC
	- Virtual Network Computing
	- Seit den 90s bei UNIX VNC ein RDP-Ähnliches
	   X11-Protokoll
	- Stark von RDP abweichende technische Implementierung,
	  jedoch mit gleichem Ziel
	- VNC implementiert das Remote Framebuffer Protocol und
	  ist damit plattformunabhängig

4. TeamViewer
	- 2005 veröffentlicht und Funktionalität schrittweise aufgebaut
	- Basierte ursprünglich auf VNC
	- Wollte unnötige Fahrten zu Kunden meiden
	- Fernwartungssoftware für Kontrollierten Zugriff
	  auf andere Rechner.
	- Verfügbar auf fast jedem gängigem Betriebssystem (Windows, macOS,
	  Linux*, Android, iOS)
	- Erfordert die TeamViewer software auf beiden Geräten.
	- Baut eine TCP/UDP Verbindung über den Port 5938 auf.
	- End to End verschlösselung mit RSA und AES

5. Secure Shell (SSH)
	- Entwickelt 1995 von Tatu Ylönen
		- Bemerkte Sniffing-Angriffe auf RSH- und Telnet-Verbiundungen im
		  Netzwerk der Universität Helsinki
			- RSH, rlogin und Telnet sind plain-text
			  Fernzugriffs-Protokolle aus der
			  Prä-Internet-Zeit
	- Funktion
		- Entwickelt für sichere verschlüsselte Remote Shell-Sitzungen
		- Eigentlich nur Dienst zur Verschlüsselung von TCP-Verbindungen
		- Sichtbar:
			- Dass eine SSH-Verbindung stattfindet
			- Mögl. Anzahl Datenpakete
			- Mögl. Frequenz des Datenaustauschs
		- Nicht sichtbar:
			- Inhalt der Datenpakete
		- Beispiel:
			- Amazon-Pakete vor der Haustür des Nachbarn
		- Ablauf
			1. Aufbau einer TCP-Verbindung (meistens)
				- Auch Websocket-Verbindung möglich
			2. Server identifiziert sich mit RSA- DSA- o.
			   ECDSA-Zertifikat
			3. Symmetrische Verschlüsselung der Verbindung
			4. Authentifizierung des Clients
				- Public-Key/Private-Key
				- Passwort
				- Auch die Privaten Schlüssel können verschlüsselt
				  werden
				- Bei aktuellen Versionen auch MFA möglich 
			- Außerdem wird pro SSH-Verbindung ein Channel eingerichtet
				- Mehrere Verbindung zwischen gleichem Client
				  Server möglich

		- Paketaufbau:
			1. Paketlänge (4 Bytes) (Unverschlüsselt)
			2. Paddingmenge (1 Byte) (Verschlüsselt)
			3. Payload/Inhalt (Verschlüsselt)
				- Kann auch anderes Protokoll sein
				- Kann Komprimiert werden
			4. Padding (Verschlüsselt)
				- Zufällig generierte Bytes, zur Erhöhung der
				  Sicherheit
				- Beispiel von vorher:
					- Zusätzlich zu den Amazon-Paketen weitere
					  Leere Pakete vor der Haustür
					- Oder Alle Pakete unabhängig von Inhalt
					  gleichgroß und Rest mit
					  Verpackungsmaterial gefüllt
			5. Nachrichtenauthentifizierungscode (Unverschlüsselt)
				- Dient der Verifizierung der Integrität des Pakets

- Hands-On-Szenario (SSH):
	1. Einrichten eines SSH-Servers unter Ubuntu
		- Installation
		- Konfiguration
		- Starten und Einschalten des Daemons unter systemd
	2. Verbinden und Authentifizieren via Kennwort
		- Hinterlegen des eigenen Public Keys auf dem SSH-Server
	3. Verbinden und Authentifizieren via SSH-Keys
	4. Upload und Download von Dateien via SCP (Secure Copy/copy over SSH)
	5. Weiterleiten einer X11-Sitzung über SSH

---

### Konkreter Aufbau SSH-Hands-On

- Vorbereitetes VMDK Image
	- Dateien zum Hoch- und Runterladen
	- SSH nicht Vorkonfiguriert
- Schriftliches Guide
	- Womit kann man die Aufgaben erledigen
- Schriftlicher Multiple-Choice Test
	- Wie baue ich eine SSH-Shell-Verbindung auf?
	- Welche Segmente einer SSH-PDU sind unverschlüsselt?
	- Warum wurde SSH entwickelt?
	- Wofür ist das Padding da?

---

### SSH-Hands-On-Vorbereitung

1. Ubuntu VM unter VirtualBox
2. Ein Paar Dateien verschiedener Formate für die SCP-Befehle ablegen
3. VMDK Image erstellen und auf SourceForge hochladen
4. Testen
5. Dokumentieren und als Guide zusammenfassen
6. Multiple-Choice-Test erstellen
