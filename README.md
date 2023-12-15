# Grupparbete-Airbean

https://www.figma.com/file/Z2yrqVaPqq1JsG4LYZqIRg/Smooth-surfers%3A-datalogiskt-t%C3%A4nkande?type=whiteboard&node-id=0-1&t=IH7zsXh4L6F0vpHz-0

## Decompisition

### Gränssnit

Lång och klurig diskussion angående gränssitt. Vi funderade över ifall layout innefattar all stil så som positionering till färg och typsnitt. Vi valde nuvarande trädstruktur men det är värt att nämna att vi inte är helt enhetliga i valet av strukturen. Den nuvarande strukturen visar hur positionering har en roll för sig utanför stil, generell positionering. Sedan visar vi även att positionering är beroende av stil genom att använda den igen som subkategori till stiler. Defenitionen av "Layout" diskuterades. Vi valde att inte använda det ordet för att göra strukturen tydligare för oss själva.


### Produkthantering
 
I figma skissen visar en lista med produkter. I listan med produkter går det att se individuella varor samt deras pris och kort beskrivning. Denna information hämtas från en databas.


### Betalningshantering

Betalningshantering behandlas av en extern tjänst.


### Kundhantering

Som kund på AIRBEAN kan du beställa som registrerad medlem alternativt som gäst. Det känns logiskt att en databas är inkopplad oavsätt om användaren är registrerad eller gäst. I övrigt angående profil ingår inlogg och autentisering. Det står inget tydligt om det i figmaskissen men vi gör ett antagande att en användare kan skapa och ta bort konto. Figma skissen visar lite info om inloggad kund, istället för att skriva "orderhistorik" väljer vi profilinfo som täcker orderhistorik samt övrig relevant profilinfo som förekommer.


### Varukorg

I varukorgen kan man visa sina varor. När varukorgen öppnas räknas ett värde ut då varukorgen inte är tom. Man kan även lägga till och ta bort varor. När varor läggs till eller tas bort sker en ny uträkning på priset. Kunden kan sedan välja "checkout", då övergår processen till orderhantering samt betalningshantering.


### Orderhantering

För att lägga en beställning krävs det att varukorgen läses in, detta sker genom att datorn hämtar infon om kundens varukorg. För att kunna lägga order måste kunden även uppge info. Är kunden redan medlem finns det möjlighet för auto-fill för både leverans- samt betalningsinfo. Då beställningen är laggd finns det en integrad karta som visar vart budet befinner sig. Karta samt auto-fill hämtas från databas.
Efter beställning ska kunden kunna se bekräftelse samt beräknad leveranstid tillsammans med den integrerade kartan. Kunden kan även visa gammla ordar och se totalpris för alla ordrar. Gamla ordrar samt totalpris hämtas från databas.


## Pattern recognition

Vi började med att använda decomposition för att dela in applikationen i mindre delar. Sedan använder vi pattern recognition för att samanställa återkommande moment. 

Vi lade till "Formulär" som ett återkommande mönster. Figjam skissen visar att liknande formulär dyker upp då man skapar eller tar bort konto. 
Vi tolkar det även som att formulär kan dyka upp då man fyller i leverans- samt betal-info. 

"Databas" är det mönster som återkommer mest. Variablar som pris, kundinfo, produkter osv behöver databas att hämta info ifrån. 
Gränssnitt förekommer över hela websidan, men som syns i decomposition-trädet har vi valt att sätta gränssnitt för sig. Detta gjorde vi för att inte trädet skulle bli för klottrigt med info, det säger sig själv att gränssnitt täcker hela applikationen.

Mer info angående pattern recognition finns i våran figjam i den gröna rutan.

 
## Abstraction

Vi klurade lite på vad för relevanta saker som finns med i abstraction. (FORTSÄTT FÖRKLARA MOTIVERINGEN TILL VAL I ABSTRACTION)


## Algorithm design

I våran Algorithm har vi valt att använda oss av ett flow-chart som representerar användarens väg från att hen startar appen tills att beställningen är gjord. Vi utgick ifrån figma skissen, men då den inte är 100% interaktiv tolkade vi fritt hur vägen för användaren ser ut. 

Till största del rullade denna flow-chart på naturligt utan större hinder. Användaren uppmanas att logga in eller fortsätta som gäst när hen startar appen. Användaren gör sedan sitt val i menyn. Användaren kan välja att gå vidare till info om AIRBEAN's kaffe, orderstatus samt kaffemeny. I kaffemenyn har vi lagt alla kaffeval i samma "outcome", för att inte göra flow-charten för klottrig. 

Vi visar även med pilar i flow charten hur det är möjligt att "gå tillbaka" till föregående sida när man gör menyval. Vi visar också hur användaren uppmanas att skapa konto eller logga in vid beställning (om kunden inte redan är registrerad). 

Användaren kan fortsätta som gäst eller skapa konto om hen inte redan är inloggad. En gäst får göra sitt val om leveransposition, sedan skriva in sina betalningsuppgifter och  slutligen bekräfta beställning.

En inloggad medlem har sin info sparad om hen tidigare angett denna info. Medlemmen får valet att använda sparad adress, eller att välja adress på kartan. Användaren bekräftar sedan beställningen.

När gästanvändaren ska lägga beställning uppmanas hen att skapa ett konto. Första tanken var att skicka kunden tillbaka upp i trädet till första "skapa konto" som dyker upp. Men vi anser att det är mer användarvänligt att kundens varukorg sparas och efter skapat konto förs varukorgen över och kunden hamnar i "leveransval", istället för att behöva göra om alla steg.
