Anwendungsfallbeschreibung

**Reservierung ändern** | UC 2 | v1

**Kurzbeschreibung**

Eine bestehende Reservierung kann von berechtigten Benutzern (registrierte Kunden oder Mitarbeitern) geändert werden. 
Änderungen können das Datum, die Uhrzeit, die Personenanzahl sowie Zusatzwünsche betreffen. 
Die betroffenen Kunden müssen über die Änderungen informiert werden.

**Primär-Akteure**

**Benutzer:**
*	Möchte bestehende Reservierungen ändern und sicherstellen, dass alle Daten aktualisiert werden.

**Mitarbeiter:**
*	Ändern Reservierungen für Kunden telefonisch oder vor Ort und aktualisieren alle betroffenen Informationen.

**Sekundäre-Akteure**

**Benachrichtigungssystem:**
*	Versendet Bestätigungen oder Wartelisten-Updates an die betroffenen Kunden.

**Vorbedingungen:**
*	Benutzer ist authentifiziert und angemeldet.
*	Eine bestehende Reservierung ist vorhanden.

**Ergebnis bei Erfolg:**
*	Die Reservierung ist erfolgreich geändert und gespeichert
*	Alle betroffenen Daten (Datum, Uhrzeit, Personenanzahl, Zusatzwünsche) sind aktualisiert.
*	Kunden werden über die Änderungen informiert

**Ergebnis bei Fehler:**
**Fehler**                         | **Ergebnis**                       | **Bedingung, die dazu geführt hat**
--------                           | --------                           | --------
Benutzer ist nicht authentifiziert | Änderung wird nicht durchgeführt   | Anmeldung erforderlich
Reservierung existiert nicht       | Änderung wird nicht durchgeführt   | Ungültige Reservierungsnummer
Keine Berechtigung zur Änderung    | Änderung wird nicht durchgeführt   | Benutzer ist nicht autorisiert

**Standardablauf**
1.  Benutzer wählt die Option, eine bestehende Reservierung zu ändern.
2.	System zeigt die Details der bestehenden Reservierung an.
3.	Benutzer ändert die gewünschten Daten (Datum, Uhrzeit, Personenanzahl, Zusatzwünsche).
4.	System prüft die Verfügbarkeit für die neuen Daten.
5.	Reservierung wird aktualisiert, sofern keine Konflikte bestehen.
6.	Bestätigung der Änderung wird an den angegebenen Kontakt (Telefonnummer und/oder E-Mail) gesendet

**Alternativ- oder Fehlerabläufe**  
4.af.1: Die neuen Reservierungsdaten führen zu einem Konflikt (z.B. keine Tische verfügbar).  
4.af.2: System informiert Benutzer:in über den Fehler.  
5.af.1: Änderung kann nicht durchgeführt werden, da die Reservierung storniert.  
5.af.2: Änderung kann nicht durchgeführt werden, da die Reservierung storniert.  
6.af: Benutzer hat fehlerhafte Kontaktdaten hinterlegt. Fehler wird protokolliert.  

**Spezielle Anforderungen**
*	Änderungen müssen innerhalb von 10 Sekunden bestätigt oder abgelehnt werden
*	Das System protokolliert alle erfolgreichen und abgelehnten Änderungen.

**Häufigkeit des Auftretens**
*Regelmäßig, abhängig von der Anzahl der Reservierungen

**Status**
*In Review

**Offene Fragen**
*	Wie sollen Benutzer:innen über alternative Optionen informiert werden?
*	Welche spezifischen Protokolldaten sollen bei Änderungen gespeichert werden?
