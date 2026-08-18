# Pole tap counters

Vijf statische pagina's die bijhouden hoe vaak elke NFC-sticker (pole A t/m E) is getapt, en de bezoeker daarna doorsturen naar [brik.be/nl](https://www.brik.be/nl).

## Hoe het werkt

Elke `pole-X-redirect.html` doet bij het laden drie dingen:

1. Stuurt één aanvraag naar een gratis publieke teller-service ([countapi.mileshilliard.com](https://countapi.mileshilliard.com)) om de teller van die pole met 1 te verhogen.
2. Wacht op een bevestigd antwoord van de server (geen blind gokwerk — als het misluk, wordt dat gelogd).
3. Stuurt de bezoeker door naar `https://www.brik.be/nl`.

Een ingebouwde beveiliging voorkomt dat één fysieke tap toch dubbel geteld wordt als de pagina per ongeluk twee keer laadt (bijvoorbeeld door een browser-preload).

`resultaten.html` toont de vijf tellers naast elkaar, met een "Vernieuwen"-knop om de laatste stand op te halen en een "Reset tellers"-knop (met bevestiging) om alles terug op 0 te zetten.
