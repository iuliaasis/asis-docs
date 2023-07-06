---
title: Foi de parcurs
layout: home
parent: Managementul transporturilor/tMS
nav_order: 2
has_children: false
---
# Foi de parcurs
Modulul Foi de parcurs din ASiS ERP se adresează companiilor care dețin o flotă proprie de mașini și utilaje. Este foarte util companiilor din zona de construcții - cu multiple șantiere deschise în țară, unde se trimit utilaje și companiilor din zona de transport, cu o flotă proprie de mașini, care realizează multiple curse de transport, ce sunt monitorizate.

# Beneficiile utilizarii modulului Foi de parcurs din ASiS ERP

### salvează timp pentru resursele umane ale companiei
El poate fi redirecționat către ale puncte de interes/necesități ale companiei.
### prin acest modul, mașinile sau utilajele sunt văzute ca și centre de cost intermediare care colectează cheltuieli și apoi le transferă către centrele de cost pentru care “lucrează”
În cazul constructorilor vorbim de șantiere, în cazul transportatorilor este vorba de locuri de încarcare sau descărcare.

Modulul automatizează procesul de completare al foilor de parcurs prin preluarea automată a datelor necesare din sistemele GPS, fără a mai fi nevoie de introducerea manuală a lor.
Deci, pentru a folosi această automatizare/acest modul din cadrul sistemului ASiS ERP, e nevoie ca flota de mașini și utilaje din cadrul unei companii să fie monitorizată prin sisteme GPS. 

Acest modul este interconectat cu cel de **Ordine de deplasare** și **Contabilitate** din ASiS ERP.

# Ce este foaia de parcurs?
Prin intermediul foii de parcurs poate fi justificată cheltuiala cu combustibilul în cadrul unei companii. 
Pentru ca dreptul la deducere să poate fi exercitat, foaia de parcurs trebuie întocmită corect, iar informaţiile veridice. Sunt trecute astfel detalii precum:
- numărul de kilometri efectuaţi,
- caracteristicile deplasării (urban, extraurban, tipul de drum),
- modul de exploatare al automobilului (cu aer condiţionat, în condiţii de iarnă, etc),
- categoria de vehicul utilizat,
- scopul şi locul deplasării,
- norma proprie de consum carburant pe kilometru parcurs.

# Cu ce sisteme GPS interfațează ASiS ERP?

ASiS ERP poate interfața cu orice sistem GPS prin intermediul unui API, și poate prelua date cu o frecvență stabilită de managementul companiei (o dată pe zi, de exemplu).
Cele mai populare sisteme GPS cu care s-a realizat deja interfațarea sunt:
- TracKGPS Arobs
- Webeye
- Dynafleet - Volvo Trucks
- EvoGPS - Vodafone

# Fluxul de lucru în cazul modulului Foi de parcurs
Pentru a putea recepționa date în acest modul ASiS, este nevoie de câteva configurări inițiale, care pot fi făcute doar de personalul tehnic:
- integrarea sistemului ASiS ERP cu sistemul GPS utilizat în companie
- integrarea sistemului ASiS ERP cu Heremaps  pentru a putea vizualiza poziția mașinilor/utilajelor pe hartă.

După aceste configurări inițiale, e nevoie de definirea centrelor de cost în macheta Comenzi din ASiS ERP. 

Centrele de cost pot fi marcate și direct pe hartă (Heremaps) ca și stații sau puncte de interes. 

În dreptul informațiilor pentru fiecare centru de cost, se va lua în considerare/seta o rază de acțiune. Acest lucru e important pentru că sistemul ASiS ERP recunoaște când o mașină care e considerată centru de cost intermediar, se afla în raza de acțiune a centrului de cost 1, de exemplu, și reralizează în mod automat transferul cheltuielilor acumulate pe mașină, într-o perioadă de timp, către centrul de cost 1. 

În macheta Foi de parcurs (care este de fapt un Centralizator de foi de parcurs), se pasă butonul **Import foi de parcurs din**și astfel se realizează importul automat.
În momentul importului, aplicația ASiS ERP face o atribuire a kilometrilor parcurși de o mașina pe centrele de cost prin care a trecut mașina (conform sistemelor GPS și Heremaps). Atribuirea de km se face inclusiv în funcție de **senzorii PTO (care știu când s-a facut descarcarea sau încarcarea)**.

Daca atribuirea stațiilor nu s-a facut corect de către sistemul ASiS ERP, acestea se pot modifica. 
În cazul utilajelor, sunt preluate inclusiv orele de funcționare a lor. 
Se analizează și se verifică datele din centralizator.

Se apasă butonul de **Generare foi de parcurs**. Se genereaza foi de parcurs pentru toate mașinile setate, pentru o anumită lună sau o anumita perioadă.

Pe lângă datele legate de km parcurși, ASiS ERP poate preia tot prin intermediul API-urilor date legate de combustibil (prin interfațarea cu furnizor de combustibili) sau de taxe de drum. 






