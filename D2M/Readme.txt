Doc2Mail-programmet er baseret på views, som findes her:

https://github.com/GeoSjaelland/Ejendoms-og-Miljoedatabasen/blob/master/GS_EJER.sql
https://github.com/GeoSjaelland/Ejendoms-og-Miljoedatabasen/blob/master/GS_EJER_PUNKT.sql
https://github.com/GeoSjaelland/Ejendoms-og-Miljoedatabasen/blob/master/GS_BORGER.sql
https://github.com/GeoSjaelland/Ejendoms-og-Miljoedatabasen/blob/master/CVR_PRODUKTIONSENHED.SQL

Disse views er baseret på, at man har adgang til såkaldt nye interfaceviews: http://ejendom.nethotel.dk/emdb/interfaces.asp?DOMAIN=11&DESC=E%26M+BBR-data+nyt+format
Atså views, som starter med JY7
Har man ikke adgang til CVR, kan man undlade at skrive sti og navn i ini-filen. CVR dermed ikke komme med i dialogboksen.

Views skal oprettes i Ejendoms- og Miljødatabasen og geokodes i MapInfo. De kan derefter navngives vilkårligt, hvorefter navnene og stierne angives i D2M.INI
Her angives også, om man benytter ADRESSE_ID eller ADRESSELINK_ID som geokodningskolonne samt stier til de mapper, som benyttes af programmet.

Forudsætningen for, at programmet fungerer i sammenhæng med KMD's Doc2Mail er, at man i sin skabelon har de rette printkoder:
{PRINT %%d2m*DOKSTART |d2m*IDENT:"{MERGEFIELD D2M}" |d2m*OVERSKRIFT: {"MERGEFIELD "Emne"}" |d2m*ATTPNO:"{MERGEFIELD PNO}" |d2m*ADDRETURNADDRESS:true \* MERGEFORMAT}

her er

Derudover skal der naturligvis også flettefelter ind i skabelonen:
«ADRESSERINGSNAVN»
«CO_navn»
«Adresse»
«AUDVADR»
«Postdistrikt»

«EMNE»

Vær MEGET opmærksom på, at man ikke benytter det flettede Worddokument i forbindelse med aktindsigt, eftersom der i printkoden vil stå alle modtageres CPR/CVR-numre. Disse vil være skjult, men kan vises med ALT+F9