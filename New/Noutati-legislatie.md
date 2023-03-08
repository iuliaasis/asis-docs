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

- Pentru aceata in ASiS ERP am definit in machetele de corectii/subtipuri de corectii (functie de cum se lucreaza) tipuri/subtipuri de corectii pentru fiecare din aceste tipuri de venituri neimpozabile.
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

### Salariu neimpozabil 200 de RON

- Calcul Salar neimpozabil 200 RON conform Ordonantei 168. Conform Articolul XXXVII din Ordonanta 168 in cazul salariatilor care desfasoara activitate in baza contractului individual de munca, incadrati cu norma întreaga, la locul unde se afla functia de baza, nu se datorează impozit pe venit si nu se cuprinde in baza lunara de calcul al contributiilor sociale obligatorii suma de 200 lei/luna, reprezentand venituri din salarii si asimilate salariilor, daca sunt indeplinite cumulativ urmatoarele conditii:
	- nivelul salariului de baza brut lunar stabilit potrivit contractului individual de munca, fara a include sporuri si alte adaosuri, este egal cu nivelul salariului minim brut pe tara garantat (3000 RON in 2023)
	- venitul brut realizat din salarii si asimilate salariilor, astfel cum este definit la art. 76 alin. (1)-(3) din Legea nr. 227/2015, cu modificarile si completarile ulterioare, in baza aceluiasi contract individual de munca, pentru aceeasi luna, nu depaseste nivelul de 4.000 lei inclusiv.

- Suma de 200 RON se diminueaza functie de perioada lucrata in unitate sau cat timp contractul este activ. Fata de varianta tratata pentru anul 2022 cand nu s-a inclus aceasta suma in venitul total (s-a inclus doar in venitul net si in restul de plata), pentru anul 2023 am inclus aceasta suma in Venitul total si apoi am diminuat bazele de calcul la CAS, CASS, CAM si Impozit cu aceasta suma. Am tratat astfel speta pentru anul 2023 intrucat conditia de nedepasire a venitului brut de 4000 RON, impunea stabilirea acestei dupa determinarea venitului total. S-a modificat calcul de salarii in ASiS pentru aceasta suma neimpozabila.

### Concediu de ingrijitor

- Conform legii 283 din 19.10.2022 (pentru modificarea Legii 53/2003 - Codul Muncii) se introduce un nou tip de concediu: Concediul de ingrijitor (incepand cu luna Decembrie 2022).  Concediul de ingrijitor este concediul acordat salariatilor in vederea oferirii de ingrijire/sprijin personal unei rude/persoane care locuieste in aceeasi gospodarie cu salariatul si care are nevoie de ingrijire/sprijin ca urmare a unei probleme medicale grave. 

- Potrivit Legii 283/2022, angajatorul are obligatia acordarii concediului de ingrijitor salariatului in vederea oferirii de catre acesta de ingrijire/sprijin personal unei rude/persoane care locuieste in aceeasi gospodarie cu salariatul si care are nevoie de ingrijire/sprijin ca urmare a unei probleme medicale grave, cu o durata de 5 zile lucratoare intr-un an calendaristic, la solicitarea scrisa a salariatului.

- Conform dispozitiilor legale, pentru concediul de ingrijitor, se poate stabili o durată mai mare decât cea prevazuta anterior, prin legi speciale sau prin contractul colectiv de munca aplicabil.

- Este foarte important de precizat faptul ca acest tip de concediu de ingrijitor, nu se include in durata concediului de odihna anual si constituie vechime in munca si in specialitate.

- Pentru aceasta in ASIS s-a introdus in macheta de Alte evenemente din ASiSria, un tip nou I-Concediu ingrijitor (pentru cei care au setat operare CO eveniment in macheta de concedii de odihna - parametru COEVMCO cu valoare logica True). Pentru cei care NU opereaza concediile de tip eveniment in macheta de concedii de odihna se va opera concediul de ingrijitor fie in pontaj fie in pontaj zilnic (daca se lucreaza cu pontaj zilnic). 

- Salariatii care beneficiaza de concediul de ingrijitor sunt asigurati pe aceasta perioada, in sistemul asigurarilor sociale de sanatate fara plata contributiei. Prin urmare s-a tratat si in ASiS ca aceasta indemnizatie sa nu intre in baza de calcul a contributiei de sanatate. Momentan pana se va modifica si DUK Integrator este posibil sa apara mesaj de eroare pentru acesti salariati la validarea D112. S-au modificat momentan rapoartele Stat de plata.RDL, Fluturas centralizator.RDL, Stat de plata directia muncii.RDL, Fluturasul cu detaliere retineri (fluturasul cu sablon XML sau formularul in format HTML2PDF) pentru afisarea orelor si indemnizatiei de concediu ingrijitor. Aceste modificari se vor publica pe ASiSUpdate luni 16.01.2023.
- Obiectele SQL publicate contin popularea parametrilor pentru ore lucratoare luna/salar minim brut pe tara garantat in plata.

### Diurne neimpozabile si impozabile
**01.11.2022 - Solutie pentru lucru in ASiS.PS cu diurne impozabile si neimpozabile pentru aplicare prevederi Legea 72/2022**
**Introducere legislativa:**

 - Incepand cu veniturile aferente lunii mai 2022, prevederile Legii nr. 227/2015 privind Codul fiscal, se modifica astfel incat valoarea indemnizatiei de delegare, indemnizatiei de detasare, indemnizatiei de detasare transnationala, prestatiilor suplimentare primite de salariati in baza clauzei de mobilitate precum si orice alte sume de aceeasi natura, altele decat cele acordate pentru acoperirea cheltuielilor de transport si cazare, primite de salariati potrivit legislatiei in materie, pe perioada desfasurarii activitatii in alta localitate, in tara sau in strainatate, in interesul serviciului, sunt exceptate de la plata impozitului pe venit si a contributiilor sociale ale angajatului si angajatorului, atat timp cat sumele acordate se incadreaza in urmatoarele limite:
„k) indemnizația de delegare, indemnizația de detașare, inclusiv indemnizația specifică detașării transnaționale, prestațiile suplimentare primite de salariați în baza clauzei de mobilitate, precum și orice alte sume de aceeași natură, altele decât cele acordate pentru acoperirea cheltuielilor de transport și cazare, primite de salariați potrivit legislației în materie, pe perioada desfășurării activității în altă localitate, în țară sau în străinătate, în interesul serviciului, pentru partea care depășește plafonul neimpozabil stabilit astfel:
(i) in tara, 2,5 ori nivelul legal stabilit pentru indemnizatie, prin hotarare a Guvernului, pentru personalul autoritatilor si institutiilor publice, in limita a 3 salarii de baza corespunzatoare locului de munca ocupat;
(ii) in strainatate, 2,5 ori nivelul legal stabilit pentru diurna, prin hotarare a Guvernului, pentru personalul roman trimis in strainatate pentru indeplinirea unor misiuni cu caracter temporar, in limita a 3 salarii de baza corespunzatoare locului de munca ocupat. 
Plafonul aferent valorii a 3 salarii de bază corespunzătoare locului de muncă ocupat se calculează prin raportarea celor 3 salarii la numărul de zile lucrătoare din luna respectivă, iar rezultatul se multiplică cu numărul de zile din perioada de delegare/detașare/desfășurare a activității în altă localitate, în ţară sau în străinătate;”
Diurna in 2023 – Model de calcul pentru deplasarea in tara pentru o firma din sectorul privat: Stabilirea diurnei neimpozabile pentru un salariat cu salariul de baza de 3000 de lei brut. 
Diurna interna – angajatul cu salariul de baza de 3000 de lei brut este trimis intr-o delegatie in tara, timp de 5 zile lucratoare, in luna curenta (Mai 2023).
Plafonul de 2,5 x nivelul stabilit pentru insistutii publice: 20×2.5=50 lei/zi, adica pentru aceasta delegatie se poate primi o diurna de 250 de lei (50 lei x 5 zile)
Plafonul raportat la 3 salarii de baza: 3000 lei brut x 3 : 22 zile lucratoare x 5 zile delegatia = 2045,45 lei. 
De aici poate aparea urmatoarea situatie:
Daca salariatul va primi diurna 50 lei/zi asta inseamna 250 lei pentru cele 5 zile. Prin urmare, va fi neimpozabila pentru ca se incadreaza in intervalul valoric prevazut de lege (este mai mica de 2045,45 lei).
Exemplu calcul diurna pentru deplasare in afara tarii pentru o firma din sectorul privat:
Diurna externa – angajatul cu salariul de baza de 3000 de lei brut este trimis intr-o delegatie in strainatate, timp de 5 zile lucratoare, in luna curenta (Mai 2023).
Angajatul va fi trimis in Germania in delegatie, tara pentru care diurna externa pe zi 35 euro pentru sectorul public, asadar, este 87,5 euro pentru sectorul privat (35×2,5)
Angajatul ar putea beneficia pentru o diurna de 437.5 euro, adica 2,119.07 lei (calculat la un curs euro de 4.84 lei)
Aceasta valoare este mai mare decat plafonul de 2045,45 calculat. Rezulta ca 2045,45 lei vor fi diurna neimpozabila, iar diferența de 73,62 lei va fi impozabila.
	Pentru a putea gestiona in ASiS.PS diurnele impozabile si neimpozabile este nevoie ca perioadele de diurna/detasare pe salariati cu numarul de zile/indemnizatia zilnica sa fie operate/preluate/generate in macheta/tabela Diurne. In macheta/tabela CuantumDiurne se pot defini diurnele la nivel de tara (daca exista delegatii/detasari in afara tarii), precum si sumele acordate pe teritoriul Romaniei.
	Ex. de operare date in macheta Cuantum Diurne: 
Tara: Germania, Valuta: EUR, Diurna: 87.5 EUR, Diurna neimpozabila 87.5 EUR. Daca diurna acordata ar
fi de sa zicem 100 EUR, atunci automat diferenta de 12.5 EUR (100-87.5) este diurna impozabila. Diurna neimpozabila de 87.5 EUR va intra la plafonare functie de plafonul reprezentat de 3 salarii de baza corespunzatoare locului de munca.
	In sensul celor de mai sus s-a introdus corectia noua (cod W-) Diurne neimpozabile. Aceasta corectie este inserata automat in tabela tipcor la rularea obiectelor SQL de salarii.
	In macheta Configurare optiuni PS, pe parametrii: DIUNEIMP, DIUIMP si CODBDIURN trebuie sa se configureze faptul ca se lucreaza cu:
Diurne neimpozabile (Optiune=Da si Valoare=Codul tipului de corectie pentru diurne neimpozabile=W-). Daca diurna s-a virat deja inainte de lichidare drepturilor salariale aferente lunii de calcul, atunci in loc de codul corectiei W- se va utiliza codul B1 (Indemniz. Delegare neimpozab).
Diurne impozabile (Optiune=Da si Valoare=Codul tipului de corectie - unul din tipurile de corectie cu efect in venitul brut). In documentul din google drive de la adresa: https://docs.google.com/document/d/1Rmm5mMThHqrO1QAxes19TXIb-VO4QEigFmihK569iTU/edit?usp=sharing sunt specificatii cu privire la tipurile de corectii si efectul lor.
Cod de beneficiar de retinere diurne setat in parametru CODBDIURN in campul valoare alfanumerica.
La calcul salarii, aplicatia determina valoarea diurnelor neimpozabile si impozabile pentru fiecare salariat tinand cont de perioadele de diurna/detasare, indemnizatia zilnica si plafonul specificat mai sus si genereaza in macheta/Tabela Corectii aceste sume.




