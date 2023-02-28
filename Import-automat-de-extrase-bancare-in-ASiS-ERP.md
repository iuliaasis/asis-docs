---
title: Automatizare extrase bancare
layout: home
parent: Financiar-terti
nav_order: 2
has_children: false
---
# Importul automat de extrase bancare în ASiS ERP
Procesul automat de import al extraselor bancare în sistemul ASiS ERP presupune **preluarea automată a informațiilor din fișierul SWIFT MT940** pus la dispoziție de bănci și integrarea acestor informații în ASiS ERP pentru reconcilierea conturilor, raportarea finaciară și gestionarea bugetelor. 

## Beneficiile importului automat a extraselor bancare in ASiS ERP

- Optimizarea **fluxului de lichidități** prin eficientizarea activității
- Existența unor **situații în timp real** asupra fluxurilor monetare
- Eliminarea în mare parte a proceselor manuale
- Îmbunătățirea ergonomiei sistemului de management financiar
- Flexibilitate: pachetul instalare – configurare – implementare este ușor de asimilat 

## Ce este fișierul SWIFT MT940?

**SWIFT MT940**, supranumit și extras electronic bancar este un fișier standard cu extensia *.STA, care conține toate operațiunile unui cont, numărul extrasului, soldurile inițiale și cele finale. 

Acest format este pus la dispoziție de bănci și poate fi importat în ASiS ERP pentru a oferi o viziune de ansamblu asupra operațiunilor de plăți – încasări făcute prin bancă și pentru a ușura munca departamentului financiar. 
Chiar dacă formatul este unul standard, pot exista variațiuni în funcție de bancă, însă în majoritatea cazurilor este identic. Totuși, chiar dacă există mici diferențe, nu există probleme în gestionarea fișierelor de la toate băncile în ASiS ERP. 

Extrasele bancare pot fi importate zilnic sau lunar.

## Aspecte privind un extras bancar

Pentru companiile medii si mari din Romania, un extras bancar poate varia intre **20 si 1000 de pagini de operatiuni lunare**. 
În medie, sunt procesate aproximativ **300 de pagini** de operațiuni bancare lunar. Fiecare companie are cel puțin un cont bancar în lei și într-o altă valută, iar aceste conturi sunt gestionate prin intermediul a cel puțin două bănci.

Printre cele mai frecvente aspecte întâlnite în extrasele bancare ale companiilor se numără **plățile către furnizori, încasările de la clienți, plățile diverse, vânzările realizate prin intermediul terminalelor de plată (POS), plățile și avansurile pentru diurne, plățile de salarii și conversiile valutare.**

Nota: importul de extrase bancare se poate realiza daca in cadrul firmei exista procese bine definite care functioneaza. De exemplu: facturi inaintea incasarilor, etc.

## Flux operational pentru importul de extrase bancare
Sunt urmăriți 3 pași:
- Preluarea datelor bancare într-o tabelă de lucru din sistemul ASiS ERP și, prin folosirea unor algoritmi inteligenți -interpretarea liniilor din extrasul bancar
- Definirea regulilor de încadrare a operațiunilor manual, în primă instanță și apoi sistemul le recunoaște singur.
- Generarea Registrului de bancă

Fișierul emis de bancă este preluat într-o tabelă de lucru în care datele pot fi vizualizate, tranzacțiile sunt recunoscute de persoana responsabilă de la departamentul financiar, iar o parte dintre acestea sunt recunoscute inclusiv de sistemul ASiS. 
Ulterior se definesc reguli de încadrare a tuturor operațiunilor, iar pe baza unui mecanism prin care soluția ASiS ERP învață de la oameni cum să încadreze diverse operațiuni bancare care se regăsesc pe extras, la următoarea preluare a extrasului pentru alte perioade de timp, se observă că operațiunile inițial neidentificate se împuținează considerabil. Tot mai multe fișiere vor fi astfel recunoscute de program, automatizându-se procesele. 
