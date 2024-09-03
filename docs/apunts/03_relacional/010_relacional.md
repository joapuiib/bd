---
template: document.html
title: Model Relacional
icon: fontawesome/solid/book-open
---

## Introducció
Una vegada s'ha realitzat el disseny del model i l'estructura de les dades,
es pot dissenyar com representar aquesta informació en les estructures
utilitzades en les __bases de dades relacionals__. Aquesta representació s'anomena __Model Relacional__,
que descriu com es poden organitzar les dades mitjançant __taules relacionals__.

## Taula relacional
Una __taula relacional__ és una estructura que organitza les dades en forma de matriu,
distribuïdes en files i columnes.

Una taula relacional té els següents requisits:

- Cada entrada de la taula, és a dir, cada element que es vol emmagatzemar està representat en una __fila__ o __tupla__.
- Cada __atribut__ dels elements emmagatzemats es guarda en una __columna__.
- La taula és homogènia per columnes; és a dir, tots els elements d'una taula tenen el mateix nombre de columnes
    i totes les dades d'una columna representen el mateix atribut dels diferents elements.
- Cada columna de la taula té assignat un nom únic en la taula. En diferents taules es pot repetir el nom.
- No es permeten valors múltiples dins d'una cel·la.

Les propietats d'aquestes taules són:

- Els elements o files poden estar en qualsevol ordre.
- Els atributs o columnes poden estar en qualsevol ordre.
- Els elements poden ser referenciats mitjançant els valors que el formen.
- Les columnes poden ser referenciades mitjançant el nom que la identifica.

La representació que utilitzarem serà, el nom de la taula EN MAJÚSCULA, i entre parèntesi, tots els atributs en minúscula.

!!! tip
    Si una entitat o atribut està compost per diferents paraules, podeu utilitzar la convenció __snake\_case__,
    on cada paraula està separada per guions baixos.

!!! example
    L'entitat __Cotxe__ amb els atributs _Matrícula_, _Número de bastidor_, _Marca_, _Model_, _Quilòmetres_ i _Data compra_ es
    pot descriure com la següent taula relacional.

    Aquesta taula es representaria com:

    - COTXE(matricula, n_bastidor, marca, model, quilòmetres, data_compra)

    Exemple de la taula `COTXE` amb dades:

    | #Matrícula | N. Bastidor | Marca | Model | Km | Data compra |
    | :- | :- | :- | :- | :- | :- |
    | 4231 KJL | 16483920 | Ford       | Focus  | 39031 | 08/12/2000 |
    | 4078 CMP | 23948756 | Ford       | Fiesta | 10542 | 02/01/2001 |
    | 3091 LSF | 12347003 | Volkswagen | Golf   | 8065  | 02/04/2001 |
    | 7012 DLM | 84012398 | Peugeot    | 207    | 48623 | 28/11/2001 |
    | 3877 FFT | 74832134 | Audi       | Q2     | 57737 | 05/12/2001 |
    | 1034 KMC | 56481093 | BMW        | X3     | 8480  | NULL |

El conjunt de tots els valors que pot pendre un __atribut__ s'anomena
__domini__, i és un aspecte que cal tindre en compte.

A més, també es pot assignar el valor __nul__ o `NULL` quan
l'element no té o es desconeix el valor per a un atribut.

## Claus
En les taules relacionals s'utilitzen diferents __claus__ per identificar
els elements de les taules relacionals, tant en una única taula com en
taules externes.

### Clau candidata
La __clau candidata__ és un atribut o conjunt mínim d'atributs que identifica
de manera única cada element d'una taula relacional.

Aquestes claus han de complir les condicions `UNIQUE` i `NOT NULL`, és a dir,
si s'especifica una clau primària, tots elements de la taula han de tindre
un valor assignat (no pot ser `null`) i a més, han de ser diferents entre ells
(dos elements no poden tindre la mateixa clau primària).

!!! example
    En la taula `COTXE`, tenim les claus candidates: `matricula` i `n_bastidor`.

    Els dos atributs són capaços d'identificar cada element de la taula,
    ja que tots els cotxes han de tindre una matrícula i un número de bastidor,
    i en els dos casos, cap cotxe pot tindre el mateix valor que un altre cotxe.

### Clau primària
La __clau primària__ és la clau candidata que es tria per identificar
cada element d'una taula relacional.

Normalment, es representen ^^subratllades^^ o amb el símbol `#`.
!!! example
    En la taula __Cotxe__, la matrícula pot ser la __clau primària__.

    Es representaria com:

    - COTXE(^^#matricula^^, resta d'atributs...)

### Clau alternativa
Les __claus alternatives__ són aquelles claus candidates que no són la clau primària.

La principal diferència entre una clau primària i alternativa és que en una taula poden existir múltiples claus
alternatives, però sols una primària.

Aquest tipus de claus no tenen una representació especial respecte a un atribut regular. Quan s'especifiquen les restriccions d'integritat,
es pot definir una restricció de tipus `UNIQUE`, per evitar valors repetits.

!!! example
    En aquest cas, com s'ha decidit que la _matrícula_ s'utilitzarà per a identificar
    els cotxes (clau primària), el _número de bastidor_ és una __clau alternativa__,
    ja que també serveix per identificar cada cotxe.

### Clau forana o externa
La __clau forana o externa__ és l'atribut o conjunt d'atributs que permet relacionar un element d'una taula
amb elements d'una altra taula. Normalment, s'utilitzen les claus primàries per relacionar les taules entre si.

Aquestes claus es representen en _cursiva_, indicant entre parèntesi la taula i l'atribut al qual fa referència.

- ENTITAT(^^#clau_primaria^^, _clau_forana(ENTITAT2:atribut)_)

!!! example
    Ens agradaria saber qui és el propietari de cada cotxe, per tant,
    s'ha afegit la taula `PERSONA` a la nostra base de dades.

    | #DNI | Nom | Cognoms |
    | :- | :- | :- |
    | __91471118A__{.green} | Carles | Perelló |
    | __23986973C__{.yellow} | Òscar | Peris |
    | __24211153L__{.orange} | Andreu | Pastor |
    | __76064612R__{.blue} | Isabel | Mora |

    A més, s'ha afegit la clau forana `_propietari(PERSONA:dni)_` a la taula `COTXE`
    que relaciona les dues taules.
    Aquesta clau forana emmagatzema els valors de la clau primària `dni` de la taula `PERSONA`
    i, per tant, es pot relacionar i saber quin cotxe pertany a cada persona.

    La representació d'aquesta taula és:

    - COTXE(^^#matricula^^, n_bastidor, marca, model, km, _propietari(PERSONA:dni)_, data_compra)

    | #Matrícula | N. Bastidor | Marca | Model | Km | _Propietari_ | Data compra |
    | :- | :- | :- | :- | :- | :- | :- |
    | 4231 KJL | 16483920 | Ford       | Focus  | 39031 | __91471118A__{.green} | 08/12/2000 |
    | 4078 CMP | 23948756 | Ford       | Fiesta | 10542 | __91471118A__{.green} | 02/01/2001 |
    | 3091 LSF | 12347003 | Volkswagen | Golf   | 8065  | __23986973C__{.yellow} | 02/04/2001 |
    | 7012 DLM | 84012398 | Peugeot    | 207    | 48623 | __24211153L__{.orange} | 28/11/2001 |
    | 3877 FFT | 74832134 | Audi       | Q2     | 57737 | __76064612R__{.blue} | 05/12/2001 |
    | 1034 KMC | 56481093 | BMW        | X3     | 8480  | NULL | NULL |

## Integritat
Es defineixen com __regles d'integritat__ a aquelles regles que garanteixen la consistència i
integritat de la informació. Aquestes regles es basen en els dominis dels atributs, les claus
primàries i les claus foranes (integritat referencial).

##### Regles d'integritat
__Taula__:

- Una taula relacional no pot tindre tuples iguals (elements repetits).

__Domini__:

- Cada atribut sols pot prendre un únic valor per cada tupla.
- Un atribut no pot prendre valors que estiguen fora del domini definit.

__Claus primàries__:

- Les claus primàries no poden contindre elements nuls. Aquesta restricció s'anomena `NOT NULL`.
- Les claus primàries no poden tindre valors repetits en diferents elements, és a dir,
    el valor ha de ser únic per a cada element. Aquesta restricció s'anomena `UNIQUE`.
    Aquesta restricció pot ser definida en les __claus alternatives__.

__Integritat referencial o clau forana__:

- Les claus foranes han de prendre valors existents en la taula a la qual es vol referencial o `NULL`.

- Es poden definir diferents comportaments per a la modificació i eliminació de les tuples referenciades:

    - Eliminació o modificació en cascada (`CASCADE`): Si s'elimina una tupla o es modifica la clau primària de la taula referenciada,
    també s'esborren o es modifiquen les tuples de la taula on està referenciada.

        !!! example
            Si s'esborra la tupla __91471118A__{.green} de la taula `PERSONA`, també s'esborraran les tuples __4231 KJL__ i __4078 CMP__ de la taula `COTXE`.

    - Eliminació o modificació restringida (`RESTRICT`): No és possible eliminar entrades d'una taula si són referenciades des d'una altra taula.

        !!! example
            La tupla __91471118A__{.green} no pot ser eliminada i la clau primària no pot ser modificada.

    - Eliminació o modificació amb valors nuls (`SET NULL`): És possible l'eliminació o modificació, però els valors en la taula des d'on es referència passarà a ser `NULL`.

        !!! example
             tupla __91471118A__{.green} de la taula `PERSONA` pot ser eliminada.
             valor de l'atribut `propietari` de les tuples __4231 KJL__ i __4078 CMP__ passarà a ser `NULL`.

    - Eliminació o modificació amb valors per defecte (`SET DEFAULT`): És possible l'eliminació o modificació, però els valors en la taula des d'on es referència passarà a ser un valor per defecte definit.

        !!! example
            La tupla __91471118A__{.green} de la taula `PERSONA` pot ser eliminada.
            El valor de l'atribut `propietari` de les tuples __4231 KJL__ i __4078 CMP__ passarà a ser un valor per defecte definit.

## Bibliografia
- Material de Laura Villalba, _Introducció a les bases de dades_.
- Ahijado Sánchez, A, _Bases de datos_, Ed. Marcombo.
- https://unstop.com/blog/difference-between-primary-key-and-candidate-key

