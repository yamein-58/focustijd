# FocusTijd – iPhone taken-app (prototype v1)

FocusTijd is een eenvoudige, volledig Nederlandstalige **Progressive Web App (PWA)**. Geen App Store, geen Mac en geen abonnement nodig. Geschikt voor iPhone SE (2020 / 2e generatie) met recente iOS-versie. Gebruikt geen online accounts of trackers.

## Wat doet de app?

- Toont één taak tegelijk, met een grote knop **Klaar! Volgende taak**.
- Telt af tot de ingestelde eindtijd van een pakket (standaard **Schooldag → 08:10**), onafhankelijk van hoe snel een taak klaar is.
- Laat je eigen takenpakketten maken, taken toevoegen/verwijderen en volgorde aanpassen.
- Speelt optioneel een kort, zelfgemaakt akkoordje bij het afronden.
- Bewaart instellingen en voortgang op de iPhone zelf (`localStorage`).
- Probeert het scherm wakker te houden terwijl een takenpakket actief is via de Screen Wake Lock API. De app moet daarvoor **zichtbaar op de voorgrond** blijven; iOS kan dit weigeren bij bijvoorbeeld energiebesparing of vergrendeling.
- Werkt offline nadat je hem eenmaal via HTTPS hebt geladen en de offline-bestanden zijn gecachet.
- Een nieuw kalenderdag start een pakket opnieuw als de vorige einddatum voorbij is. Wil je vandaag opnieuw starten, gebruik dan *Nog een keer* na voltooiing, of wissel pakketten.

## Installatie op een iPhone zonder Mac

De bestanden moeten **op een HTTPS-adres** staan (bijvoorbeeld GitHub Pages of een bestaande website). Een `file://`-bestand direct openen is niet voldoende voor betrouwbare installatie/offline-functionaliteit/wake lock.

### Publiceren met GitHub Pages
1. Maak een nieuwe publieke GitHub-repository, bijvoorbeeld `focustijd`.
2. Upload alle inhoud uit deze map **in de root van de repository**: `index.html`, `manifest.webmanifest`, `sw.js` en de complete map `icons`.
3. Ga bij GitHub naar **Settings → Pages → Build and deployment → Deploy from a branch**. Selecteer `main` en `/(root)` en sla op.
4. Open `https://JOUW-GITHUB-NAAM.github.io/focustijd/` op de iPhone in **Safari**.
5. Tik in Safari op het deelmenu, kies **Zet op beginscherm** / **Voeg toe aan beginscherm** en voeg **FocusTijd** toe.
6. Open de app via het nieuwe icoon op het beginscherm.

Een HTTPS-website die je al beheert kan ook; behoud dezelfde mapstructuur en het HTTPS-adres.

## Compatibiliteit en scherm aan

- Het iPhone SE-model **MX9R2ZD/A** is de iPhone SE (2020, tweede generatie), met 4,7-inch scherm.
- Apple ondersteunt de **Screen Wake Lock API in Home Screen Web Apps vanaf iOS 18.4**. Werk iOS bij als dat nodig is.
- Het scherm-aan blijven kan **niet** het zelf indrukken van de sluimerknop, een leeglopende batterij, achtergrondmodus of bepaalde iOS-beperkingen overnemen. Zet de iPhone bij langdurig gebruik op een lader.
- Optioneel kun je de iOS-functie **Begeleide toegang** inschakelen als het kind niet uit de app moet kunnen wisselen: Instellingen → Toegankelijkheid → Begeleide toegang. Activeer deze op de iPhone SE vanuit de geopende app door **driemaal op de thuisknop** te drukken (na het instellen van de functie).

## Testen op je computer

- Eenvoudig: open `index.html` in Chrome; de taaknavigatie en instellingen werken lokaal, maar PWA-installatie/service worker en wake lock werken pas in de juiste beveiligde context.
- Beter: start in deze map `python -m http.server 8000` en open `http://localhost:8000` in een browser op dezelfde machine. `localhost` is voor ontwikkeling toegestaan.

## Wijzigen / aandachtspunten

- Deze eerste versie is een **werkend prototype**, nog niet volledig getest op de echte iPhone SE en diens iOS-instellingen.
- De gegevens staan **uitsluitend op het apparaat en in de browseropslag**. Een verwijderde app/browserdata kan ook de instellingen verwijderen. Er is nog geen export/backup/synchronisatie.
- De knop *Ouderinstellingen* is niet beveiligd met een pincode; dat kan later worden toegevoegd.
- De timer gebruikt een echte einddatum/-tijd (niet het aantal ticks) en blijft daardoor correct als de app even niet zichtbaar is. De app kan echter geen alarm op het vergrendelscherm geven in deze versie.
- De app bevat geen externe afbeeldingen, externe lettertypen of betaalde diensten.
