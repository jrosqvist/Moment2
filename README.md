# Moment 2 - Webbutveckling III

## Automatisering av arbetsprocessen
Med automatisering underlättas utvecklandet av webbplatser och applikationer. Vanligt förekommande uppgifter går att hantera
automatiskt, vilket sparar tid. Exempelvis kan filer komprimeras för att reducera filstorleken eller konkateneras för att 
reducera antalet filer. Det är även möjligt att automatiskt konvertera filer till ett annat format och filer kan kopieras
och skickas mellan olika kataloger.

## Använda paket i uppgiften
I den här uppgiften används NodeJS och Gulp för att sköta automatiseringsprocessen.
Paketen som används är
* gulp-concat - för sammanslagning av JS-filer
* gulp-uglify-es - för att komprimera JS-filer
* gulp-concat-css - för att konkatenera CSS-filer
* gulp-clean-css - för att komprimera css-filer
* browser-sync - för att ladda om webbläsarfönstret automatiskt då en uppdatering skett

## Systemets uppbyggnad och funktion

#### Systemstart
Systemet startas genom att skriva "gulp" i terminalfönstret.

#### Deklarering av variabler & inkludering av paket
Konstanta variabler deklareras och tilldelas de olika paketen så de kan användas
i taskarna.

#### Sökvägar
Sökvägar till respektive filtyp skapas i ett objekt.

#### Tasks
En task tar hand om html-filer, kopierar dem från en arbetskatalog till en publicerings-dito.
Den andra tasken tar hand om js-filer. Konkatenerar och komprimerar dem. Slår ihop 
dem till en enda fil - "main.js".
Den tredje tasken tar hand om css-filerna på precis samma sätt som den tasken ovan.
Den fjärde tasken kopierar bilder från arbetskatalogen till publiceringskatalogen.
Den femte tasken, "watchTask", skaper en konfigurationsfil för browser-sync, 
för att sedan lyssna efter förändringar i någon utav katalogerna med arbetsfiler.
Görs en förändring laddas webbläsarfönstret om för att alltid visa uppdaterat innehåll.
