Anwendungsfallbeschreibung

**Reservierung anlegen** | UC 1 | v1

**Kurzbeschreibung**

Eine Tischreservierung kann von berechtigten Benutzern (registrierte Kunden oder Mitarbeiter) für ein Restaurant der Kette durchgeführt werden. Die Reservierung wird überprüft und bestätigt oder auf die Warteliste gesetzt. Benutzer erhalten eine Benachrichtigung über den Status der Reservierung.
Nicht registrierte Kunden können auch telefonisch reservieren.
Jede erfolgreiche Reservierung bekommt auch ein Systemweit eindeutige ID.
Reservierung verfällt, wenn nach einer Stunde die Reservierung nicht in Anspruch genommen wurde.

**Primär-Akteure**

**Benutzer:**
*	Möchten eine Reservierung für sich oder andere Teilnehmer durchführen.
*	Möchten mehrere Reservierungen in verschiedenen Restaurants durchführen.
*	Wollen über den Status der Reservierung (bestätigt, Warteliste) informiert werden.
*	Wollen, dass Zusatzwünsche und spezifische Anforderungen berücksichtigt werden.

**Sekundäre-Akteure**

**Messaging-System:**

•	Benachrichtigt die Kunden über den Status der Reservierung.

**Zeitmonitor:**

•	Prüft die Warteliste und fügt die Reservierung bei Bedarf in diese ein.

**Datenbank:**

•	Protokolliert die ausgeführte Aktion und legt die Reservierung in der Datenbank ab.

**Vorbedingungen:**
*	Benutzer ist registriert, authentifiziert und autorisiert.
*	Restaurantdaten (Kapazitäten, Verfügbarkeiten) sind aktuell und korrekt im System hinterlegt.

**Ergebnis bei Erfolg:**
*	Die Reservierung ist im System gespeichert.
*	Die ausgeführten Aktionen sind protokolliert.
*	Benutzer erhält eine Bestätigung über die Reservierung oder den Wartelistenstatus.
*	Zusatzanforderungen sind gespeichert und an das Restaurant übermittelt.

**Ergebnis bei Fehler:**
**Fehler**                                                     | **Ergebnis**                                  | **Bedingung, die dazu geführt hat**
--------                                                       | --------                                      | --------
Benutzer ist nicht autorisiert eine Reservierung zu machen     | Vorgang wird abgebrochen                      | Vorgang wird abgebrochen	Benutzer ist nicht registriert bzw. eingeloggt
Systemfehler                                                   | Vorgang wird abgebrochen und protokolliert    | Ungültige Eingabe, Serverfehler, etc.

**Standardablauf**
1.  Benutzer wählt die Option, eine Reservierung anzulegen.
2.	Das System zeigt eine Übersicht der verfügbaren Restaurants in der ausgewählten Stadt.
3.	Benutzer wählt ein Restaurant aus und gibt die Reservierungsdetails (Datum, Uhrzeit, Personenanzahl, Zusatzwünsche) ein.
4.	Das System überprüft die Verfügbarkeit:
    *	Verfügbar: Die Reservierung wird gespeichert.
    *	Nicht verfügbar: Alternativen werden angezeigt, oder Benutzer wird in die Warteliste eingetragen.
5.	Benutzer erhält eine Bestätigung für die Reservierung.
6.	Das System protokolliert die ausgeführten Aktionen.

**Alternativ- oder Fehlerabläufe**  
4.af.1: Es ist keine Verfügbarkeit mit Zusatzwünschen gegeben. Benutzer wird eine Verfügbarkeit ohne Zusatzwünsche angeboten.  
4.af.2: Benutzer möchte nicht in die Warteliste und bricht den Vorgang ab.  
5.af: Benutzer verlässt die Seite, bevor die Reservierung bestätigt wurde. Keine Daten werden gespeichert.  
6.af: Benutzer hat fehlerhafte Kontaktdaten hinterlegt. Fehler wird protokolliert.  

**Spezielle Anforderungen**
*	Antwortzeit bei Verfügbarkeitsprüfung innerhalb von 10 Sekunden in 90 % der Fälle.
*	Automatische Benachrichtigungen müssen innerhalb von 30 Sekunden versandt werden.

**Häufigkeit des Auftretens**
*Mehrmals täglich pro Restaurant.

**Status**
*In Review

**Offene Fragen**
*	Wie wird mit Reservierungen verfahren, die durch fehlerhafte Kontaktangaben nicht bestätigt werden können?
*	Welche Alternativvorschläge sollen priorisiert werden (z. B. Uhrzeit oder Zusatzwünsche)?
