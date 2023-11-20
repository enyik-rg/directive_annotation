# directive_annotation
Manual annotation of imperative forms in the MedCollect healthcare fake news corpus

## alldirectives.tsv 
A fájlban megtalálható a MedCollect korpusz felszólításannotációja során annotált összes kifejezés. 
A sorok az egyes annotált szó adatait tartalmazzák, tabulátorral elválasztva.  

A sorok egyes oszlopai a következők:  

**id**: a szó azonosítója, fájlnév + 's' + mondatsorszám + 'w' + szósorszám alakban  
**type**: a szöveg típusa: 
* *fn* - álhír
* *tn* - kontroll
* *nemEü* - egyéb (ez nem része a MedCollectnek)

**form**: az annotált szó  
**source**: a *source* jegy értéke, vagy '\_' ha nem jelölt  
**directive**: a *directive* jegy értéke, vagy '\_' ha nem jelölt  
**target**: a *target* jegy értéke, vagy '\_' ha nem jelölt  
**status**: a *status* jegy értéke: 
* *auto* - az előelemzés felszólító alaknak jelölte, és az is
* *error* - az előelemző felszólító alaknak jelölte, de nem az
* *new* - az előelemző által nem megtalált felszólító alak

**sentence**: a teljes mondat, amiben a szó található

## cks_total.xlsx
Az excel fájlban az annotátorok kurátorhoz viszonyított annotátori egyetértési adatai találhatóak 
Cohen-féle kappa módszerrel számítva. 

Az első lapon maguk az egyetértési értékek, a következő három lapon az annotátorok egyetértési értékeinek
az oszlopdiagramjai.

Az annotátori egyetértések nem a teljes annotált szövegre vannak számolva, hanem csak a releváns szavakra -> bázis.  
A *status* jegyek esetében a releváns szavak a *status* jegyek valamelyikével való ellátottság.  
A *directive* jegyek esetében a felszólító alakok, azaz az *auto* vagy *new* *status*-címkéjű szavak.  
A *source* é a *target* jegyek esetében külön számoltunk annotátori egyetértést a *saját hangú*, illetve 
a *közvetített* *directive*-címkéjű szavaknál.  
Az *1|2* jelölésű értékek esetében a vetítési alapba azok a szavak tartoztak, amelyeket legalább 
az egyik annotátor (az annotátor vagy a kurátor) a bázisba sorolt, az *1&2* jelölésű értékek esetén 
azok a szavak, amelyeket mindkét annotátor egyaránt a bázisba sorolt. Például a *dir_1|2* oszlopban 
azoknál a szavaknál mértük a *directive* jegyekkel való ellátottság egyetértését, amelyeket 
vagy a kurátor, VAGY az annotátor *auto* vagy *new* *status*-címkével látott el (unió), a *dir_1&2* 
jelölésű értékeknél pedig azoknál a szavaknál, amelyeket a kurátor ÉS az annotátor is így annotált (metszet).

Az *all*, *dir*, *2sj_src*, *2sj_tgt*, *3kzv_src* és *3kzv_tgt* oszlopok az összes megfelelő címke 
összesített annotátori egyetértését mutatja, az utánuk következő értékek az egyes címkékre lebontva.  
