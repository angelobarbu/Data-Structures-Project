# Barbu Angelo-Gabriel (angelo.barbu123@gmail.com)
# Structuri de Date si Algoritmi(SDA) - 2019-2020

CERINTE PROIECT ATP_CUP:

1. Se va crea o listă dublu înlănțuită, circulară, cu santinelă, pentru stocarea țărilor participante. Țările se vor adăuga întotdeauna la finalul listei. (Nu la începutul acesteia). Cine nu respectă structura respectivă va primi 0p
2. Din lista anterior creată se vor elimina țări, până când numărul lor devine cea mai mare putere a lui 2 posibilă (exemplu: Dacă există 63 de țări, se vor elimina până când numărul lor ajunge la 32 = 2 la puterea a 5-a). Eliminarea țărilor se face după următorul criteriu: Scorul inițial al unei țări, reprezentat de media aritmetică a scorurilor personale ale jucătorilor din lotul țării respective, este relevant DOAR în cadrul acestei cerințe. Acesta NU se adaugă la scorul global al țării respective. Practic, acest scor NU se va mai folosi în rezolvarea ulterioară a cerințelor.
A nu se confunda cu scorul local sau scorul global al unei țări (aflăm în cadrul următoarei cerințe despre aceste scoruri) pe parcursul turneului!!! Toate țările vor începe cu un scor global egal cu 0.
3. Se vor implementa următoarele structuri de date și se vor realiza următoarele procedee asupra lor pentru buna desfășurare a turneului:
Se va crea o stivă în care se vor adaugă toate țările rămase în turneu, pornind de la santinelă.
Se vor scoate din stivă succesiv câte 2 țări, între care urmează să fie jucate meciurile. Procedeul se repetă până când stiva este goală.
Pentru fiecare pereche de țări extrasă din stiva se va crea o coadă în care se vor pune meciurile dintre jucători.
Fiecare jucător din lotul primei țări va juca cu fiecare jucător din lotul celei de-a doua țări, în următoarea ordine: primul jucător din lotul primei țări se confruntă, pe rând, cu toți jucătorii din cel de-al doilea lot, al doilea jucător din lotul primei țări cu toți jucătorii din cel de-al doilea, etc.
Jucătorul cu scorul personal mai mare câștigă. Acestuia i se adaugă 5 puncte la scorul personal, iar țara pentru care joacă primește 3 puncte la scorul local.
În cazul în care cei doi jucători au scoruri personale egale, se consideră egalitate. Fiecărui jucător i se adaugă câte 2 puncte la scorul personal, iar fiecare țară primește câte 1 punct la scorul local.
Coada meciurilor dintre două țări s-a golit. Confruntarea dintre cele două s-a terminat. Urmează verificarea scorurilor locale ale celor două țări. Celor doua țări li se adaugă scorul local, acumulat pe parcursul meciurilor dintre jucători, la scorul global, dar câștigătoare este doar țara cu scorul local mai mare.
În cazul egalității dintre scorurile locale ale celor două țări, este considerată câștigătoare țara în lotul căreia se află jucătorul cu cel mai mare scor personal (dintre scorurile personale ale jucătorilor celor două țări). În cazul în care există egalitate și între cele două scoruri personale ale celor mai buni jucători, declarați câștigătoare prima țară care este scoasă din stivă.
Se va crea o stivă WINNER, în care se vor adăuga țările câștigătoare în urma meciurilor.
Când stiva inițială devine goală, putem considera încheiată această etapă a turneului. Se vor scoate țările din stiva WINNER și se vor adăuga pe rând în stiva inițială. Se vor repeta procedeele anterioare pentru fiecare etapă a turneului, cu alte cuvinte până când în stiva WINNER va rămâne, în final, o singură țară câștigătoare.
4. Se va crea un BST – arbore binar de căutare, în care se vor afla jucătorii ultimelor 4 țări rămase în turneu, în funcție de scorul personal obținut o dată cu terminarea ultimei etape a turneului.
În cazul în care unul dintre jucători are același scor personal cu unul deja existent în arbore, va fi adăugat jucătorul al cărui nume este mai mic din punct de vedere lexicografic. (Este comparat intai numele de familie, in cazul egalitatii urmand sa fie comparat prenumele jucatorilor.)
5. În fișierul cerinte.in, așa cum a fost prezentat anterior, se vor găsi numele și prenumele a 2 jucători. Se cere numărarea jucătorilor care se află între aceștia în BST (cei 2 jucători nu se includ). Mai explicit, se cere numărul jucătorilor care au scorul personal inclus între cele două scoruri personale.
