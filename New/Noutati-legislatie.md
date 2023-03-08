---
layout: default
title: Noutati legislative
nav_order: 2
parent: Noutati
---

# Noutăți legislative 2023
## Modificari ASiS.PS valabile de la 01.01.2023
### Venituri neimpozabile și beneficii impozabile 

- Ordonanta 16/2022 a introdus un nou alineat la art. 76 din Codul fiscal (Legea 227/2015) prin care este prevazut ca anumite beneficii (venituri) cumulate lunar sunt **venituri neimpozabile in limita a 33% din salariul de baza corespunzator locului de munca**. 
- Acestea sunt:
	- prestatiile suplimentare primite de salariati in baza clauzei de mobilitate.
	- contravaloarea hranei acordate de catre angajator pentru angajatii proprii,
	- cazarea si contravaloarea chiriei pentru spatiile de cazare/de locuit puse de cttre angajatori la dispozitia angajatilor proprii
	- contravaloarea serviciilor turistice şi/sau de tratament, inclusiv transportul, pe perioada concediului
	- contribuţiile la un fond de pensii facultative suportate de angajatori in limita a 400 EURO/an
	- primele de asigurare voluntara de sanatate, precum si serviciile medicale furnizate sub forma de abonament, suportate de angajator, in limita a 400 EURO/an
	- sumele acordate angajatilor care desfasoara activitati in regim de telemunca in limita unui plafon de 400 lei lunar.
	- contravaloarea abonamentelor pentru utilizarea facilitatilor sportive în vederea practicării sportului

- Pentru aceata in ASiS am definit in machetele de corectii/subtipuri de corectii (functie de cum se lucreaza) tipuri/subtipuri de corectii pentru fiecare din aceste tipuri de venituri neimpozabile.
- Pe langa acestea pentru clauza de mobilitate, daca aceasta este de natura sporului (adica se acorda procent/suma functie de orele lucrate) si este inregistrata deja ca si spor in dreptul salariatilor am introdus in macheta Configurari Sporuri, posibilitatea de marcare a acelui spor care reprezinta clauza de mobilitate.
- Sumele acordate salariatilor pentru telemunca se vor opera pe corectia N cu conditia ca parametru PS,NUASS-N sa aiba valoare logica True.
- La calcul salarii am tratat urmatoarele automatizari:
1. **Indemnizatia aferenta clauzei de mobilitate rezultata din dreptul sporului sa fie neimpozabila**.
2. Am calculat valoarea **cazarii/chiriei neimpozabile in limita plafonului de 20% aplicat la salariul minim brut**.
3. Am determinat la nivel de fiecare salariat **suma veniturilor neimpozabile si am plafonat aceasta suma la nivelul a 33% din salariul de baza**.
4. Suma veniturilor neimpozabile care depasesc 33% din salariul de incadrare, plus valoarea chiriei ce depaseste 20% din salariul minim brut, le-am generat ca si corectie bruta BI-Beneficii impozabile, care este inclusa in Venitul brut si impozitata conform regulilor de impozitare ale veniturilor salariale.
5. Implicit contributiile aferente acestor beneficii impozabile sunt suportate de catre angajator si aplicatia
genereaza corectia BI ca si suma neta (si apoi se determina brutul corespunzator). Daca se doreste ca aceste contributii sa fie suportate de catre angajat, prin macheta Configurare optiuni PS, pe parametru PS,COBIMPSAL se va selecta optiunea Da.
6. Generarea automata a unei retineri cu suma neta sau brut (dupa setarile mentionate la punctul anterior) pe
codul de beneficiar BENEFIMP astfel incat restul de plata al angajatului sa fie modificat corespunzator (fie sa ramina acelasi in varianta in care suporta angajatorul contributiile, fie restul de plata sa fie diminuat cu valoarea contributiilor). In macheta de Beneficiari retineri trebuie completate conturile pentru codul de beneficiar BENEFIMP.

Daca anumite venituri neimpozabile se doresc a fi virate salariatilor la lichidarea drepturilor salariale, atunci in macheta de tipuri de corectii sau cea de subtipuri de corectii se vor marca acele tipuri/subtipuri care se doresc a fi incluse in venitul net/rest de plata prin campul [X]Includere in venit net.

### Deducerea personală

Conform OUG 168/2022 se modifica modul de calcul al deducerii personale de baza si in acelasi timp se introduce deducerea personala suplimentara.
Deducerea personala de baza se acorda pentru persoanele fizice care au un venit lunar brut de pana la 2.000 de lei peste nivelul salariului de baza minim brut pe tara garantat in plata (5000 la nivelul anului 2023). Acest plafon de 2000 RON + salariul minim brut il vom denumi Venit brut maxim cu deducere suplimentara (VBMDS). Deducerea personala se acorda doar la functia de baza. Deducerea personala de baza scade degresiv pentru veniturile (venit brut lunar=Venit total din Stat de plata + valoare tichete) cuprise intre salariul minim brut (3000 la 2023) si salariul minim brut + 2000 RON (5000 la 2023) conform formulei descrise in Ordonanta 16/15.07.2022 (Articolul 40). 
Pentru contribuabilii care realizează venituri brute lunare din salarii ce depasesc plafonul generat de salariul minim + 2000 RON, NU se acorda deducerea personala de baza.
Deducerea personala suplimentara se acorda astfel:
- 15% din salariul de baza minim brut pe tara garantat in plata pentru persoanele fizice cu varsta de pana la 26 de ani, care realizează venituri din salarii al caror nivel este de pana la nivelul prevazut de VBMDS.
- 100 de lei lunar pentru fiecare copil cu varsta de pana la 18 ani, dacă acesta este inscris într-o unitate de invatamant, parintelui care realizeaza venituri din salarii, indiferent de nivelul acestora.
	- In cazul in care copilul este intretinut de ambii parinti, deducerea personala suplimentara prevazuta mai sus se acorda unuia dintre parinti prin prezentarea documentului care atesta inscrierea copilului intr-o unitate de invatamant si a unei declaratii pe propria raspundere din partea parintelui beneficiar.
	- In situatia in care parintele desfasoara activitate la mai multi angajatori, in plus fata de documentele prevazute la punctul de mai sus parintele care beneficiaza de deducerea personala suplimentara prevazuta mai sus are obligatia sa declare ca nu beneficiaza de astfel de deduceri de la un alt angajator.

- In ASIS ERP in macheta Salariati, tabul Persoane in intretinere s-a introdus campul Deducere suplimentara prin care se va marca in dreptul copilului daca acesta participa la deducerea suplimentara. 

- Pentru deducerea de 15% din salariul de baza minim brut, DACA se lucreaza cu cetateni straini care la momentul angajarii nu au CNP din care sa se poata determina data nasterii (si apoi implicit varsta) trebuie ca in ASiSria in macheta Salariati sa se activeze campul Data nasterii si apoi sa se completeze. Daca NU se lucreaza cu asemenea cetateni straini, NU este nevoie de activarea campului Data nasterii intrucat ea rezulta din CNP.

- S-au modificat procedurile de calcul salarii pentru calcul corectii brut din net - s-a tratat sa se tina cont si aici de noul mod de calcul al deducerilor personale baza si suplimentare.

- S-au modificat in ASiS procedurile de calcul salarii pentru calculul deducerii personale de baza si suplimentare. Momentan in Fluturasi.RDL, Stat de plata.RDL, Stat de plata restrans.RDL am afisat deducerea suplimentara impreuna cu deducerea de baza. In Fluturas centralizator.RDL, Stat de plata directia muncii.RDL si Fluturasul HTML2PDF sau cel cu formular XML am afisat deducerea suplimentara separat de deducerea personala. 
