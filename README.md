# Troya - HackMyVM (Medium)
 
![Troya.png](Troya.png)

## Übersicht

*   **VM:** Troya
*   **Plattform:** HackMyVM (https://hackmyvm.eu/machines/machine.php?vm=Troya)
*   **Schwierigkeit:** Medium
*   **Autor der VM:** DarkSpirit
*   **Datum des Writeups:** 18. November 2022
*   **Original-Writeup:** https://alientec1908.github.io/Troya_HackMyVM_Medium/
*   **Autor:** Ben C.

## Kurzbeschreibung

Das Ziel der "Troya"-Challenge war die Erlangung von User- und Root-Rechten. Die initiale Reconnaissance identifizierte einen Host mit offenen Ports 22 (SSH - OpenSSH 7.9p1) und 80 (HTTP - Nginx 1.14.2). Die Web-Enumeration (Nikto) ergab keine signifikanten Angriffspunkte außer fehlenden Security Headern. Versuche, sich per SSH als Benutzer `troya` mit geratenen Passwörtern anzumelden, scheiterten. Der bereitgestellte Writeup-Text dokumentiert keinen erfolgreichen initialen Zugriff oder eine nachfolgende Privilegieneskalation. Die Flags wurden am Ende des Berichts ohne Kontext zur Erlangung aufgeführt.

## Disclaimer / Wichtiger Hinweis

Die in diesem Writeup beschriebenen Techniken und Werkzeuge dienen ausschließlich zu Bildungszwecken im Rahmen von legalen Capture-The-Flag (CTF)-Wettbewerben und Penetrationstests auf Systemen, für die eine ausdrückliche Genehmigung vorliegt. Die Anwendung dieser Methoden auf Systeme ohne Erlaubnis ist illegal. Der Autor übernimmt keine Verantwortung für missbräuchliche Verwendung der hier geteilten Informationen. Handeln Sie stets ethisch und verantwortungsbewusst.

## Verwendete Tools

*   `arp-scan`
*   `nmap`
*   `nikto`
*   `ssh`
*   `ssh-keyscan`
*   `cat` (zur Anzeige der Flags)

## Lösungsweg (Zusammenfassung)

Der Angriff auf die Maschine "Troya" gliederte sich in folgende dokumentierte Phasen:

1.  **Reconnaissance:**
    *   IP-Findung mit `arp-scan` (`192.168.2.126`).
    *   `nmap`-Scan identifizierte offene Ports: 22 (SSH - OpenSSH 7.9p1) und 80 (HTTP - Nginx 1.14.2).

2.  **Web Enumeration:**
    *   `nikto` auf Port 80 fand keine kritischen Schwachstellen, nur fehlende HTTP Security Header.
    *   Weitere Web-Enumerationsschritte oder Funde wurden nicht dokumentiert.

3.  **Initial Access (Versuche):**
    *   Versuche, sich per SSH als Benutzer `troya` mit verschiedenen Passwörtern anzumelden, scheiterten (`Permission denied (publickey,password)`).
    *   `ssh-keyscan` wurde ausgeführt, um die Host-Schlüssel zu sammeln, lieferte aber keine Zugangsdaten.
    *   *Im bereitgestellten Bericht wurde kein erfolgreicher initialer Zugriff dokumentiert.*

4.  **Privilege Escalation:**
    *   *Da kein initialer Zugriff erlangt wurde, konnten keine Schritte zur Privilegieneskalation dokumentiert werden.*

## Wichtige Schwachstellen und Konzepte

*   **Fehlende HTTP Security Header:** Ein häufiger, aber meist geringfügiger Konfigurationsmangel.
*   *Basierend auf dem bereitgestellten Log wurden keine ausnutzbaren Schwachstellen für einen erfolgreichen Zugriff identifiziert oder dokumentiert.*

## Flags

*   **User Flag (`user.txt`):** `pleasestop` (Erlangungsmethode nicht im Log dokumentiert)
*   **Root Flag (`root.txt`):** `partyishard` (Erlangungsmethode nicht im Log dokumentiert)

## Tags

`HackMyVM`, `Troya`, `Medium`, `SSH`, `Nginx`, `Reconnaissance` (ohne erfolgreichen Exploit im Log)
