---
template: document.html
title: Sistemes gestors de bases de dades
icon: fontawesome/solid/book-open
---

## Introducció
Recordem la estructura d'una base de dades:

<figure id="figure-1">
    <img src="../img/estructura_db.png" alt="Estructura d'una base de dades">
    <figcaption class="attribution">Autor desconegut</figcaption>
    <figcaption>Figura 1: Estructura d'una base de dades</figcaption>
</figure>

L'estructura de les bases de dades, típicament, segueix una estructura __client/servidor__ i té la següent estructura:

- __Usuaris__: Els usuaris interactuen en una aplicació connectada a la base de dades. Aquesta aplicació pot permetre als usuaris
    consultar, modificar o explotar les dades.
- __Aplicació__: L'aplicació (programa informàtic) actua com a client i es connecta al __sistema gestor de bases de dades (SGBD)__, en el servidor per recuperar o modificar les dades.
    L'aplicació es comunica amb el SGBD mitjançant un llenguatge comú, típicament el __Structured Query Language (SQL)__.
- __Sistema Gestor de Bases de Dades (SGBD, o en anglés DBMS, DataBase Management System)__: És el programari responsable de la creació i administració de bases de dades i gestionar
    la comunicació amb els clients. Normalment està instal·lat en un servidor. Aquest programari rep les peticions SQL dels clients i les tradueix en accions sobre la base de dades.
- __Base de dades__: Conjunt de dades emmagatzemades en un SGBD d'una manera ordenada i estructurada. _Per exemple, en bases de dades relacionals, s'organitzen en taules i relacions_.

En aquest material ens centrarem en què és el __Sistema Gestor de Bases de Dades (SGBD)__, les seues
característiques i el seu propòsit.


## Sistemes Gestors de Bases de Dades
Com hem avançat abans, un __Sistema Gestor de Bases de Dades (SGBD, o en anglés DBMS, *DataBase Management System*)__,
és un programa que s'encarrega de gestionar la comunicació entre la base de dades i les aplicacions (clients).

A més, el SGBD proporciona procediments, eines i llenguatges que proporciona als analistes, programadors
o administradors els mitjans necessaris per crear, processar i administrar les bases de dades
presents en el sistema.


### Objectius dels SGBD
Els SGBD ofereixen:

- __Crear i definir les bases de dades__: Especificar l'estructura i l'organització, el tipus de dades,
    les restriccions i relacions entre les dades.
- __Manipulació de les dades__: Permet realitzar consultes per recuperar, inserir, modificar
    o eliminar registres en la base de dades.
- __Accés controlat a la base de dades__: Es permet la creació d'usuaris i rols, per tal
    de controlar l'accés i permitir o denegar certes operacions, per tal d'assegurar les dades
    emmagatzemades.
- __Redundància mínima__: S'evita la redundància de les dades per tal d'optimitzar i reduïr el espai en disc.
- __Integritat i consistència de les dades__: Existeixen mecanismes per evitar que es creen inconsistències
en les dades.
- __Permeten un accés compartit a la base de dades__: Múltiples usuaris i aplicacions es poden interactuar
    de manera concurrent al SGBD.
- __Mecanismes de recuperació i còpies de seguretat__: Per recuperar les dades en cas de que el sistema
    falle.
- __Exportació i importació de dades__.


## Nivells d'abstracció de les dades
En qualsevol sistema d’informació es considera que es poden observar les dades des de dos punts de vista:

- __Vista externa__. Aquesta és la visió de les dades que posseeixen els usuaris o aplicacions externes.
- __Vista física__. Aquesta és la forma en la qual realment estan emmagatzemats les dades en el sistema físic.

En un sistema d’arxius, els usuaris veuen les dades des de les aplicacions creades pels programadors.
Aquesta vista poden ser formularis, informes visuals o en paper... Però la realitat física d'aquestes dades,
tal qual s'emmagatzemen en els discos, no la veuen. Aquesta visió està reservada als administradors.

En el cas dels sistemes de base de dades i segons el model ANSI, s’afegeix una tercera vista,
que és la vista conceptual. Aquesta vista se situa entre la física i l'externa.
Es parla doncs en bases de dades de la utilització de tres esquemes o models per representar les dades,
entenent per model les normes que permeten crear esquemes (dissenys de la base de dades).


### Esquema físic
Es refereix a la forma que s'organitzen les dades en l'emmagatzematge físic
(índexs o punters, longitud dels camps, camins d'accés a les dades, particions de memòria, etc.)
Aquesta visió la requereix només l'administrador.


### Esquema conceptual
Es correspon amb la visió total de les dades a nivell lògic.
És a dir, totes les dades i les seves relacions. Aquesta vista global s'interposa entre el nivell extern i
el nivell físic, sent independent tant de l'equip informàtica com de cada usuari en particular.

Es tracta de la proposta teòrica de la base de dades i, és per tant,
el primer pas per crear una nova de base de dades.
Consisteix en el disseny d'un model per aquest nivell.
Normalment, les persones encarregades de realitzar el diseny de la base de dades
són els __analistes__ (programadors amb experiència en el disseny de solucions informàtiques).

Aquesta organització de les dades és la que utilitzen els __desenvolupadors__ per tal de saber
com accedir a les dades des de l'aplicació que estan desenvolupant. Totes les diferents
aplicacions que accedeixen al sistema utilitzen el mateix esquema.


### Esquema extern
Es tracta de la visió de les dades que posseeixen els usuaris finals.
Aquesta visió es la que obté mitjançant les aplicacions.
Les aplicacions creades pels desenvolupadors abstreuen la realitat conceptual
de manera que l'usuari no coneix les relacions entre les dades,
com tampoc coneix totes les dades que realment s'emmagatzemen.


### Independència entre els esquemes
El més interessant d'aquests esquemes és que treballen de manera independent.
Cada usuari utilitza l’esquema que necessita sense saber res de la resta.
Aquesta independència es tradueix en:

- __Independència física de les dades__: Encara que l’esquema físic canvie,
    l'esquema conceptual no ha de veure’s afectat.
    A la pràctica això significa que encara que la base de dades s’emmagatzeme en altra disc dur,
    la part conceptual de la base de dades no s’ha de veure afectada. No tindrem que modificar l’esquema.
- __Independència lògica de les dades__: Encara que es modifique les dades de l’esquema conceptual,
    les vistes que posseeixen les aplicacions (els esquemes externs) no es veuran afectats.


## SQL
__SQL, *Structured Query Language*__, és un llenguatge estandarditzat per la ISO (_International Organization for Standardization_),
és a dir, que tots els SGBD que el suporten han de tenir la mateixa sintaxis a l'hora d'aplicar el llenguatge.
Es divideix en 4 subllenguatges, el total de tots permet al SGBD complir amb les seves funcionalitats:

- __Llenguatge DDL__: llenguatge de definició de dades (_Data Definition Language_).
    Permet crear tota l'estructura d'una base de dades, les relacions entre les dades i
    les regles que han de complir.
    Les operacions són de tipus `DROP` (esborrar), `ALTER` (modificar) i `CREATE` (crear).

- __Llenguatge DML__: llenguatge de manipulació de dades (_Data Manipulation Language_).
    Aquest llenguatge permet: `SELECT` (seleccionar/buscar), `INSERT` (inserir), `UPDATE` (actualitzar) i `DELETE` (esborrar).

- __Llenguatge DCL__: llenguatge de control de dades (_Data Control Language_).
    Inclou comandes com `GRANT` i `REVOKE` que permeten a l'administrador gestionar l'accés a les dades contingudes
    en la base de dades.

- __Llenguatge TCL__: llenguatge de control de transaccions (_Transaction Control Language_).
    El propòsit d'aquest llenguatge és permetre executar varies comandes de forma simultània
    com si fossin una comanda atòmica o indivisible.
    Si es possible, s'aplica la transacció (`COMMIT`), i si, en algun pas de l'execució passa quelcom inesperat,
    es poden desfer tots els passos realitzats (`ROLLBACK`).

- __Lenguatge de procediments__: Permet la creació de funcions, procediments,
    rutines i disparadors ens bases de dades SQL. En les bases de dades
    SQL d'Oracle rep rel nom de __PL/SQL (_Procedural Language for SQL_)__,
    afegeix una extensió per sobre de SQL. No existeix un estàndard.


## Solucions SGBD
Avui dia, trobem múltiples Bases de dades en el mercat i això ens obliga a realitzar
comparacions per a descobrir quina és la que millor s'adapta al nostre entorn. 

Una selecció de tecnologia d'emmagatzematge correcta, amb un ús senzill, segur, amb eines útils i
una comunitat que doni suport a el producte, marcarà la diferència a l'hora de gestionar un negoci.
Millorarà la nostra productivitat i, per tant, es converteix en aspecte vital per a qualsevol solució de programari.

Per tots aquests motius, el monitoratge de les bases de dades és prioritària en qualsevol instal·lació.
És recomanable investigar els avantatges i desavantatges de cada eina.
No només hem de pensar en la solució a curt termini, sinó que cal avaluar la base de dades pensant en quina serà la solució final.

Algunes de les preguntes que hem de formular-nos abans de triar una base de dades són les següents:

- A quants clients vull donar servei?
- Quina grandària de dades necessitaré gestionar? 
- Quina exigència de temps de resposta necessite donar als meus clients?
- Com escalaré la meva base de dades segons vaja augmentant el nombre de clients i transaccions?
- Com monitoraré la meva base de dades per a evitar temps d’indisponiblitat?
- Quin tipus de base de dades necessite? (SQL, NoSQL, ...)
- Com es comportarà la base de dades en cas de caiguda? Com podré restablir la normalitat?
- És un SGBD propietari o lliure? Quina llicència d'utilització té? Té cost?


### Bases de dades SQL
#### Bases de dades propietàries
- __Microsoft SQL Server__: Un SGBD desenvolupat i mantenit per Microsoft, que sols
    té compatibilitat amb sistemes Windows. La integració amb Microsoft Azure (núvol)
    ha millorat molt la seua flexibilitat i rendiment.
- __[:simple-oracle: Oracle](https://www.oracle.com/database/)__: Gestionat per l'empresa amb el mateix nom, la base de dades Oracle
    és un SGBD molt complet, amb multitud d'eines per a la seua administració i monitoratge.
    Destaca l'abundància de perfils amb experiència en aquesta tecnologia.


#### Bases de dades lliures
- __[:simple-mysql: MySQL](https://mysql.com/)__: Un dels principals SGBD lliures. La seua utilització està baix les
condicions de la llicència GPL. Va ser adquirida per Oracle en 2009.
- __[:simple-mariadb: MariaDB](https://mariadb.org/)__: Degut a que MySQL va ser adquirida per Oracle i hi havia certa incertesa respecte
a la llicència d'utilització, la comunitat va impusar la creació de MariaDB per mantindre
la seua llicència a GPL. Aquest SGBD soporta la mateixa sintaxi SQL que MySQL, encara que ha inclòs algunes extensions.
- __[:simple-postgresql: PostgreSQL](https://www.postgresql.org/)__: Alternativa a MySQL o MariaDB. És un SGBD lliure que permet crear fàcilment bases de dades distribuides.


## Bibliografia
- Material de Laura Villalba, _Introducció a les bases de dades_.
- Ahijado Sánchez, A, _Bases de datos_, Ed. Marcombo.
- https://ioc.xtec.cat/materials/FP/Recursos/fp_dam_m02_/web/fp_dam_m02_htmlindex/WebContent/u1/a1/continguts.html
- https://www.guru99.com/dbms-schemas.html
- https://en.wikipedia.org/wiki/PL/SQL
- https://ca.wikipedia.org/wiki/MySQL
- https://ca.wikipedia.org/wiki/MariaDB
- https://ca.wikipedia.org/wiki/PostgreSQL
- https://kinsta.com/blog/mariadb-vs-postgresql/

