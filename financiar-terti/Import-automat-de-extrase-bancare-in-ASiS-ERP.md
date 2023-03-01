---
title: Automatizare extrase bancare
layout: home
parent: Financiar-terti
nav_order: 2
has_children: false
---
# Robotizare/Integrare API: Importul automat de extrase bancare în ASiS ERP
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

Pentru companiile medii si mari din Romania, un extras bancar poate varia intre **30 si 1000 de pagini de operatiuni lunare**. 
În medie, sunt procesate aproximativ **300 de pagini** de operațiuni bancare lunar. Fiecare companie are cel puțin un cont bancar în lei și într-o altă valută, iar aceste conturi sunt gestionate prin intermediul a cel puțin două bănci.

Printre cele mai frecvente aspecte întâlnite în extrasele bancare ale companiilor se numără **plățile către furnizori, încasările de la clienți, plățile diverse, vânzările realizate prin intermediul terminalelor de plată (POS), plățile și avansurile pentru diurne, plățile de salarii și conversiile valutare.**

Nota: importul de extrase bancare se poate realiza daca in cadrul firmei exista procese bine definite care functioneaza. De exemplu: facturi inaintea incasarilor, etc.

## Flux operational pentru importul de extrase bancare
Sunt urmăriți 3 pași:

### 1. Preluarea datelor bancare într-o tabelă de lucru din sistemul ASiS ERP și, prin folosirea unor algoritmi inteligenți -interpretarea liniilor din extrasul bancar

[](../../assets/capturi/Captura 1 - Operatie de import bancar.png)

- Se importa fisierul MT940 oferit de banca. Fișierul emis de bancă este preluat într-o tabelă de lucru în care datele pot fi vizualizate, tranzacțiile sunt recunoscute de persoana responsabilă de la departamentul financiar, iar o parte dintre acestea sunt recunoscute inclusiv de sistemul ASiS. 
- Dupa operatia de import, se pot observa detalii precum: contul, contul IBAN, numarul extrasului, numar de pozitii de pe extras si ulterior, la generarea Registrului, se va vedea si numarul de pozitii generate in Registru.

[](../../assets/capturi/Captura 2- primul import de extrase bancare.png)
- La primul import, se pot vedea ca majoritatea operatiunilor sunt neprocesate (marcate cu rosu), dar exista si cateva procesate de sistemul ASiS (cu negru). 
- La o verificare initiala a operatiunilor procesate, se poate salva IBAN-ul tertului si sistemul, la urmatorul import, va utilizat IBAN-ul salvat. 


### 2. Definirea regulilor de încadrare a operațiunilor manual, în primă instanță și apoi sistemul le recunoaște singur. Dupa o lună de "human - machine learning" a sistemului ASiS ERP, 96% din tranzactii sunt recunoscute de sistem conform regulilor stabilite.

[](../../assets/capturi/Captura 3 - Definire reguli import extrase bancare.png)
- Pentru operatiunile neprocesate de pe extras, se poate incepe cu definirea regulilor, pozitie cu pozitie. 
De exemplu, un comision bancar va fi o plata diversa, cu contul contabil atasat (Cheltuieli cu servicii bancare). ASiS ERP sugereaza utilizatorului regula de contare de exemplu, dar utilizatorul decide care va fi incadrarea unei operatiuni si ca si cont contabil si ca si IBAN, etc. 
- Definirea unei reguli (de exemplu de Comision) inseamna ca toate operatiunile pe care sistemul le detecteaza ca fiind Comisioane de pe extras, sunt procesate conform regulii Comision.

[](../../assets/capturi/Captura 4 - Operare exceptii extrase bancare.png)
- Exceptiile de la orice reguli se opereaza manual conform stilului de introducere/modificare date din macheta de Registru de Banca din ASiS ERP.
- Se definesc reguli de încadrare a tuturor operațiunilor, iar pe baza unui mecanism prin care soluția ASiS ERP învață de la oameni cum să încadreze diverse operațiuni bancare care se regăsesc pe extras, la următoarea preluare a extrasului pentru alte perioade de timp, se observă că operațiunile inițial neidentificate se împuținează considerabil. Tot mai multe fișiere vor fi astfel recunoscute de program, automatizându-se procesele. 


### 3. Generarea Registrului de bancă

[](../../assets/capturi/Captura 5 - Generare registru de banca din extrase bancare.png)
- In cadrul machetei de Extras bancar (aceeasi macheta in care se regasesc operatiunile bancare de pe extras) se apasa butonul de **Generare registru** si acesta e generat automat de ASiS ERP. 
- Toate tranzactiile generate automat se vad in macheta Registru de banca. 

Nota: Pozitiile din Registru de banca nu se pot modifica. Ele sunt legate de cele din **Extras**.
Recomandarea este ca daca se doreste modificarea pentru o pozitie gresita din Registru, suma in dreptul ei sa fie pusa 0 si pozitia respectiva sa fie culeasa manual inca o data.

## Intrebari frecvente
### - Cum aloca sistemul ASiS ERP platile/sumele de pe un extras bancar pe un furnizor cu mai multe facturi in sistem?
Sistemul le aloca FIFO, dar exista si posibilitatea de a selecta o anumita factura la plata prin completarea campului **Factura** din macheta de operare **Extrase**.

### - La ce se mai utilizeaza campul **Factura** din macheta de operare **Extrase bancare**?
Acest camp este gandit si pentru operatiuni precum: Incasare storno, Plata furnizor - incasare storno, Plata storno - incasare beneficiar. 




 
