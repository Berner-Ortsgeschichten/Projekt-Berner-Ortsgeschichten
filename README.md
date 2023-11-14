# Projekt-Berner-Ortsgeschichten
Für das LOD-Pilotprojekt über die "Berner Ortsgeschichten" wurden in einem ersten Schritt die knapp 40 Berner Ortsgeschichten aus dem 19. Jahrhundert ausgewählt, die vollständig digitalisiert und auf [DigiBern](https://www.digibern.ch/katalog/ortsgeschichten-aus-dem-19-jahrhundert) verfügbar sind. Die entsprechenden Metadaten, die aus dem Katalog extrahiert wurden, sind angereichert und auf einer Karte georeferenziert.

[Berner Ortsgeschichten aus dem 19. Jahrhundert](https://www.google.com/maps/d/viewer?mid=1RgPrC4f7u6zwvJJgFIaWRABBFzHYcdg&ll=46.86141647085042%2C7.715000000000023&z=10)

Es gab viele Herausforderungen zu bewältigen: Erstens können GND-IDs nicht einfach aus Alma abgerufen werden. Die vollständigen Metadaten mussten über die SRU-Schnittstelle extrahiert werden, und dann wurden die GND-IDs mit Python extrahiert. Zweitens verweisen die GND-IDs nicht direkt auf die gewünschten Linked Data. Mit Hilfe von muenzfunde.ch konnten jedoch viele der gewünschten Links zu Wikidata (Q-IDs), dem Historischen Lexikon der Schweiz (HLS-DHS) und ortsnamen.ch ermittelt werden. Schließlich hatte die IT-Abteilung keine Zeit, die Daten auf einer Karte anzuzeigen, daher wurde Google My Maps als Workaround gewählt, obwohl es stark eingeschränkte Funktionalitäten bietet. Dennoch zeigen die ca. 9000 Aufrufe der Karte "Berner Ortsgeschichten aus dem 19. Jahrhundert" (Stand 1.11.2023) auf DigiBern ein erhebliches Interesse an dieser Art von Ressource.

Das Python-Skript wurde dann für den größeren Datensatz von Berner Ortsgeschichten aus den Jahren 1975 und später (500+ Titel) angepasst. Darüber hinaus wurde eine separate Datentabelle als Konkordanz erstellt, die die Tabelle von muenzfunde.ch ersetzte, die für die 40 Ortsgeschichten des 19. Jahrhunderts verwendet wurde.

[Berner Ortsgeschichten seit 1975](http://berner-ortsgeschichten.test.ub.unibe.ch/) (Achtung! Nur im Uninetz / Citrix aufrufbar.)

Dank der während dieses Prozesses hinzugefügten Q-IDs können Links zu den Wappen von Dörfern/Städten und zu den offiziellen Websites der Gemeinden sowie andere gewünschte Links nun zuverlässig mit wenigen Zeilen Python aus Wikidata extrahiert werden, zusammen mit den geografischen Koordinaten. Die IT-Abteilung konnte ein Proof-of-Concept für die Karte erstellen, die über das Universitätsnetzwerk (Citrix) zugänglich ist. Automatische Aktualisierungen der Daten aus dem Katalog sind geplant, werden aber voraussichtlich erst 2024 umgesetzt.

Weitere geplante Schritte:
- Kontinuierliche Erweiterung der BErnerOrtsTabelle (BEOT), die die Q-IDs, Links zu HLS-DHS und ortsnamen.ch sowie die GND-IDs enthält.
- Direkte Anreicherung der GND-Datensätze von Berner Ortschaften mit Q-IDs.
- Standortdaten in Wikidata ergänzen und korrigieren.
