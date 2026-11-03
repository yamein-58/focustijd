# FocusTijd v5 – afgerond pakket opnieuw starten na nieuwe eindtijd

Deze update gaat verder op de goed werkende v4 en bewaart alle bestaande takenpakketten, voortgang, instellingen en de bestaande geluiden.

## Wat is nieuw?

- Is een pakket vandaag **afgerond**? Dan toont de pakketkiezer normaal **Klaar ✓** en is de knop uitgeschakeld.
- Verander je in de **ouderinstellingen** de eindtijd van dat afgeronde pakket naar een *andere tijd die later vandaag ligt*, dan verschijnt **Start** bij het pakket. Klik op **Start** om de nieuwe ronde te beginnen.
- Verander je de eindtijd naar een tijd die al voorbij is, dan blijft **Klaar ✓** staan en kan het pakket niet vanaf de pakketkiezer worden gestart.
- Als de gewijzigde toekomstige eindtijd inmiddels verstrijkt voordat je op **Start** klikt, blijft het pakket afgerond; de vrijgave vervalt automatisch.
- Opnieuw starten gebeurt pas **na een tik op Start**, niet onmiddellijk nadat je de eindtijd wijzigt. Zo verschijnt niet vanzelf opnieuw de eerste taak.
- De app houdt ook nu de beloning op één keer per voltooide ronde. De oude knop 'Beloning opnieuw tonen' komt niet terug.
- Het soepel verschuiven, bewerken en toevoegen van taken zonder terugspringen in de ouderinstellingen blijft behouden.

**Opmerking:** de bestaande ouderknop *Dit pakket opnieuw beginnen* blijft beschikbaar; de ouderinstellingen zijn nog niet met een pincode beveiligd.

## Installatie op GitHub Pages

1. Pak de ZIP uit.
2. Vervang in de hoofdmap van je bestaande GitHub-repository **`index.html`** en **`sw.js`** door deze bestanden. Commit de wijzigingen.
3. Laat de bestaande mappen `sounds/task_succeeded/` en `sounds/mission_succeeded/` met je MP3's en MP4's ongemoeid.
4. Na publicatie op GitHub Pages: sluit de app op de iPhone volledig af en open opnieuw. Soms is nogmaals openen nodig vanwege de iOS-cache.

De service-worker-cache is opgehoogd naar `focustijd-cache-v5`. Alle bestaande persoonlijke gegevens blijven in dezelfde lokale opslag onder `focustijd-state-v1`.
