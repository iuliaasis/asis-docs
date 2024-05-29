# Tutorial de generare a Declaratiei 406 SAF-T din ASiS ERP

## Declarația 406 SAF-T: Ce este și Cum se Generează din ASIS ERP

### Ce este Declarația 406 SAF-T?

Declarația 406 SAF-T (Standard Audit File for Tax) este un standard internațional de raportare a informațiilor fiscale și contabile, utilizat pentru a facilita schimbul de date între contribuabili și autoritățile fiscale. Aceasta include date contabile detaliate, cum ar fi tranzacții, solduri contabile, informații despre terți și multe altele.

### Pașii pentru Generarea Declarației 406 din ASIS ERP

Pentru a genera Declarația 406 din ASIS ERP, urmați pașii de mai jos:

1. **Accesarea Meniului Declarația 406**:
    - Deschideți ASIS ERP.
    - Navigați la meniul "Declarația 406".
    - Alegeți luna pentru care doriți să generați declarația, de exemplu, ianuarie 2023.
    

2. **Completarea Informațiilor Inițiale**:
    - Asigurați-vă că toate informațiile inițiale sunt completate corect, inclusiv numele declarantului.
    - Folosiți un număr limitat de caractere pentru titlul declarantului (maxim 6 caractere) pentru a evita erorile la validare.
    

3. **Generarea Declarației**:
    - Apăsați butonul pentru generarea declarației.
    - ASIS ERP va crea o arhivă ZIP care conține fișierul XML cu declarația 406.
    - De asemenea, se vor genera două fișiere Excel: unul cu datele complete și unul cu datele incomplete.
    

4. **Verificarea și Corectarea Datelor Incomplete**:
    - Deschideți fișierul Excel cu date incomplete.
    - Verificați și corectați erorile specificate, cum ar fi gestiuni fără adresă completată, unități de măsură necompletate sau coduri vamale lipsă.
    

5. **Validarea Datelor cu Documentele din ASIS ERP**:
    - Deschideți fișierul Excel cu date complete și validați informațiile cu documentele din ASIS ERP.
    - Verificați soldurile conturilor, soldurile pe terți, taxe, unități de măsură, tipuri de mișcări, produse și înregistrări contabile.


6. **Generarea Finală și Validarea în DUC Integrator**:
    - După corectarea tuturor datelor incomplete, generați din nou declarația.
    - Deschideți arhiva ZIP și validați fișierul XML în DUC Integrator.
    - Asigurați-vă că nu există erori suplimentare raportate de DUC Integrator.
    

7. **Încărcarea Declarației pe Portalul e-Guvernare**:
    - După validarea fără erori în DUC Integrator, semnați XML-ul și încărcați-l pe portalul e-Guvernare la secțiunea declarații.
    - Așteptați confirmarea și recipisa de la autoritățile fiscale.
    

### Observații și Recomandări

- Este important să corectați toate erorile de date incomplete înainte de a genera declarația finală.
- Validați informațiile contabile cu atenție pentru a evita discrepanțele între balanța contabilă și fișierul generat.
- În cazul unor erori raportate de DUC Integrator care nu sunt prezentate de ASIS ERP, consultați documentația specifică sau cereți suport tehnic.

Pentru a ilustra pașii mai detaliat, urmăriți capturile de ecran asociate fiecărui pas descris. Asigurați-vă că urmați exact instrucțiunile pentru a evita probleme la generarea și validarea declarației 406 SAF-T.