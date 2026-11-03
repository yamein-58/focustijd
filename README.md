# FocusTijd v4 – taken bewerken zonder verspringen + startknoppen

De bestaande taken, pakketten, instellingen en afgeronde taken blijven behouden. De app gebruikt dezelfde lokale opslag als v3.

## Nieuw

- **Bewerken zonder naar boven te springen**: bij een taak omhoog/omlaag verplaatsen of verwijderen blijft het instellingenscherm op zijn huidige scrollpositie. De app ververst alleen de takenlijst, niet meer het hele venster.
- **Taak toevoegen**: de nieuwe taak verschijnt onderaan de lijst en de naam is meteen geselecteerd om te bewerken.
- **Kies je takenpakket**: elk nog niet afgerond pakket heeft nu een duidelijke knop **Start** (of **Verder** als je er vandaag al mee bezig was).
- Een pakket dat vandaag al volledig is afgerond toont **Klaar ✓**. De startknop is dan uitgeschakeld om te voorkomen dat de eindbeloning telkens opnieuw wordt afgespeeld. De ouder kan het pakket alsnog opnieuw laten beginnen via **Ouderinstellingen → Dit pakket opnieuw beginnen**.
- Geluidsselectie, MP3/MP4-beloningen, timers en scherm wakker houden zijn onveranderd.

## Bijwerken op GitHub Pages

1. Open het ZIP-bestand en pak de bestanden uit.
2. Vervang in de hoofdmap van je bestaande GitHub-repository alleen **`index.html`** en **`sw.js`** door de nieuwe bestanden.
3. Laat je eigen mappen `sounds/task_succeeded/` en `sounds/mission_succeeded/` ongemoeid.
4. Klik op **Commit changes**; wacht tot GitHub Pages de bijgewerkte pagina publiceert.
5. Sluit FocusTijd volledig af op je iPhone en open opnieuw. De service-worker-cache heet nu `focustijd-cache-v4`, zodat de nieuwe versie wordt opgehaald.

Opmerking: net als voorheen zijn de ouderinstellingen niet met een pincode afgeschermd.
