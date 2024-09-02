---
template: document.html
title: Sistemes d'emmagatzematge de la informació
icon: fontawesome/solid/book-open
---

## Introducció
En una era definida per la transformació digital, recopilar, accedir i transformar les dades 
s'ha convertit en el nucli de la gran majoria d'aplicacions informàtiques. Però, __què són les dades?__
Podem definir les dades com una _representació_ d'una informació del món real que és emmagatzemada
per després poder ser tractada per diferents finalitats.

En aquest tema s'estudiaran els diferents tipus d'emmagatzemar aquestes dades.


## Fitxers i directoris
Abans que les aplicacions informàtiques es convertiren en l'eina principal per a gestionar les dades,
les empreses emmagatzemaven la informació en calaixos, carpetes i arxius. El fet de recopilar, recuperar
i tractar aquestes dades requeria d'un _procés manual_ lent. Malgrat això, el sistema és senzill i fàcil d'utilitzar.

La informàtica ha intentat mantindre la nomenclatura i l'estructura perquè es pareguen al que els usuaris
utilitzen manualment. Es continua parlant de fitxers o arxius, carpetes o directoris, formularis, etc.

<figure id="figure-1">
    <img src="../img/accountants.jpg" alt="Fitxers i directoris en una oficina">
    <figcaption class="attribution">The Office</figcaption>
    <figcaption>Figura 1: Fitxers i directoris en una oficina</figcaption>
</figure>

En informàtica, els __fitxers__ són estructures de dades ordenades, creats i gestionats
pel sistema operatiu. Els fitxers s'identifiquen per un nom, que pot incloure una _extensió_,
per indicar el tipus de dades que conté.


### Fitxers de text
Depenent de com es representa la informació, podem diferenciar els fitxers en __fitxers de text__
o __fitxers binaris__.

Els __fitxers de text__ són fitxers que contenen text i, _generalment_, poden ser llegits per l'usuari.
Algun exemple d'aquests fitxers són:

- __Fitxers de text pla.__: Fitxer que sols emmagatzema text sense format (_.txt_).
    ```
    Aquest text és un text pla.
    ```
- __Fitxers de configuració__: Fitxers que s'utilitzen per configurar el sistema operatiu
    o alguna aplicació en concret (_.ini, .conf, .env, .json, .yml..._). Normalment aquests
    fitxers estan escrits mitjançant un __llenguatge de marques__.
    ```ini
    [Settings]
    dbhost=localhost
    dbname=tenda
    ```
- __Fitxers de codi font__: Contenen les línies de codi que componen un programa, escrites en
    un __llenguatge d'alt nivell__ (que pot entendre una persona) (_.java, .c, .cpp, .py, .js, .php..._).
    ```java
    class Main {
        public static void main(String[] args){
            System.out.println("Hola món!");
        }
    }
    ```
- __Fitxers anotats__: Fitxers que utilitzen un __llenguatge de marques__ per representar dades i
    informació addicional sobre aquestes (_.xml, .html, .json, .yml, .css_).
    ```yml
    centre:
      nom: CIPFP Mislata
      localitat: Mislata
    ```
- __Fitxers de text enriquit__: Guarden text, però permeten oferir una visió del text amb format (_.rtf, .tex, .md_)
    ```md
    # Introducció
    En una era definida per la transformació digital, recopilar, accedir i transformar les dades 
    s'ha convertit en el nucli de la gran majoria d'aplicacions informàtiques. Però, __què són les dades?__.
    ```


### Fitxers binaris
Els __fitxers binaris__ són fitxers que representen la informació utilitzant una codificació
__binària__ (zeros i uns) i què, generalment, no poden ser llegits a simple vista.
Aquests fitxers necessiten d'aplicacions específiques per poder accedir a la informació
emmagatzemada.

!!! info
    Podeu provar d'obrir qualsevol d'aquests fitxers en un editor de text (Notepad, per exemple)
    i veureu símbols sense cap classe de sentit.

!!! example "Contingut del fitxer de la Figura 1"
    ```
    ÿØÿà JFIF      ÿÛ C 


            
    %# , #&')*)-0-(0%()(ÿÛ C



    (((((((((((((((((((((((((((((((((((((((((((((((((((ÿÂ Ô" ÿÄ              ÿÄ            ÿÚ    æ›…Ãˆr)ëäHCª—”º°9pëA9K©YÉÃÝóÖuåÏrôJá¦ˆG4hž^Ïªßâþ‰ž™gÕX¼¹tIyòÜ§­™žˆ/Êúß×–»³_¬Ýe7øNxÕ%ÁQtŠÌ¤½”³;ÐÍ-s„ãäéd³‰ïü'¿1«ã›ÓruÁ6E¶DE°C´ßH[]æ'¡—)„	¢*hŠœHDc4V¬ŒB»«8QÚ[…nF#b1­ˆÆ¶+2-Š\f´œµ±iÇôœÞÊLg›ÑšÎ›ëŽaÒƒÔy«7(Ä”ÔP™dç¬ó|Ï­åMUeòÎª¼ÔÙ.uiÔÍŠu³ÔøÉfûÊü
    Ì{WäO`¸»ôuyüÏ¯Íäs×¢ó´Ù‰ªüún¦ÕôzòîÆ XD\Ù6°si6°si[› æŒ},uç=ï…÷vP§Þ 4À´ ` -VVrê"Ô¬±‚ !
    -&ˆ¦…]•™[”µ+UT¬QR²54AN$cd
    •Ñ³Káˆóú=(Îü*¢ü±¯Êú¯%JPºn1¹êevãÞuëãm­¹¶FÜOn|våÕŸÅ2È§^—WÍè·ÔÝåú²ò¹½ÎOª‹ªß
    réÒxwà²ºî¤ÏeVrº´gÑ›uÔÜ¾“~‡-©bm‰¶&Ø†ÄÛ"¹˜·b<ÿ ºðÞæÊc%/LLbc &
     Ð *²¢Z3è£"À &„€CBM
     ...
    ```


Alguns dels tipus de fitxers binaris més comuns són:

- __Fitxers multimèdia__: Qualsevol fitxer multimèdia conté la informació en binari, tant siga imatges (_.png, .jpg, .gif, ..._),
    vídeos (_.avi, .mpg, .mp4, ..._) o àudio (_.wav, .mp3, ..._).

- __Fitxers comprimits__: Fitxers que canvien la representació utilitzada "naturalment" en l'ordinador per representar les mateixes dades en menys espai, per tant, de manera comprimida.
    Cal fer una transformació per a obtindre o recuperar les dades d'aquest tipus de fitxers (comprimir i/o descomprimir). _.zip, .z, .rar, .gz, .rar_
- __Executables__: Programes informàtics escrits en __llenguatge màquina__. _.exe, .class, ..._
- __Fitxers d'aplicacions__: Fitxers amb un format específic per cada aplicació, des de documents de processament de text (_.docx o .odt), _.pdf_ o fitxers de Photoshop (.psd).


### Directoris
En un sistema informàtic, un directori, també conegut com a carpeta, és una estructura d'organització
utilitzada per emmagatzemar i gestionar arxius i altres directoris.
Aquesta és una part fonamental de la gestió de l'arxiu del sistema operatiu i
permet als usuaris organitzar els seus documents, aplicacions i altres dades de manera jeràrquica i estructurada.

Els directoris es poden organitzar en una jerarquia. Un directori pot contenir arxius i altres subdirectoris.
A la vegada, aquests subdirectoris també poden contenir arxius i més subdirectoris, creant una estructura en forma d'arbre.

<figure id="figure-2">
    <img src="../img/folders.jpg" alt="Estructura jeràrquica dels directoris" style="max-width: 400px">
    <figcaption class="attribution">Autor desconegut</figcaption>
    <figcaption>Figura 2: Estructura jeràrquica dels directoris</figcaption>
</figure>


## Bases de dades
Malgrat que les dades poden ser emmagatzemades mitjançant fitxers, aquest
sistema pot provocar problemes:

- __Redundàncies i inconsistències__: El fet d'haver de transportar els fitxers i duplicar-los en cada dispositiu
    que vol ser utilitzat porta a la redundància de dades, que pot portar a inconsistències si les modificacions no es fan a escala global.
- __Dificultat d'accés a les dades__: Cada aplicació llegeix les dades d'una manera concreta, que ens pot portar inconvenients si hem d'importar i exportar constantment.

Per evitar els problemes anteriors, s'han dissenyat sistemes de gestió de la informació alternatius, com les __bases de dades__.

Una __base de dades__ és un __sistema de gestió de la informació__ que emmagatzema les dades d'una manera eficient i ordenada,
sense redundàncies i les quals poden ser utilitzades per diferents aplicacions.


##### Avantatges
- Independència entre les dades i les aplicacions que accedeixen a aquestes.
- Atomicitat de les actualitzacions (evita inconsistències).
- Accés concurrent o simultani a les dades per part de diverses aplicacions.
- Menor redundància.
- Major seguretat en les dades. Es permet configurar i limitar l'accés a les dades per part dels usuaris.


##### Desavantatges
- Instal·lació costosa. El control i administració de les bases de dades requereix d'un maquinari i programari potent.
- Requereix personal qualificat per administrar i gestionar aquests sistemes.


### Estructura

<figure id="figure-3">
    <img src="../img/estructura_db.png" alt="Estructura d'una base de dades">
    <figcaption class="attribution">Autor desconegut</figcaption>
    <figcaption>Figura 3: Estructura d'una base de dades</figcaption>
</figure>

L'estructura de les bases de dades, típicament, segueix una estructura __client/servidor__ i té la següent estructura:

- __Usuaris__: Els usuaris interactuen en una aplicació connectada a la base de dades. Aquesta aplicació pot permetre als usuaris
    consultar, modificar o explotar les dades.
- __Aplicació__: L'aplicació (programa informàtic) actua com a client i es connecta al __sistema gestor de bases de dades (SGBD)__, en el servidor per recuperar o modificar les dades.
    L'aplicació es comunica amb el SGBD mitjançant un llenguatge comú, típicament el __Structured Query Language (SQL)__.
- __Sistema Gestor de Bases de Dades (SGBD, o en anglés DBMS, DataBase Management System)__: És el programari responsable de la creació i administració de bases de dades i gestionar
    la comunicació amb els clients. Normalment està instal·lat en un servidor. Aquest programari rep les peticions SQL dels clients i les tradueix en accions sobre la base de dades.
- __Base de dades__: Conjunt de dades emmagatzemades en un SGBD d'una manera ordenada i estructurada. _Per exemple, en bases de dades relacionals, s'organitzen en taules i relacions_.


### Metadades
Una base de dades és autodescriptiva, en el sentit que conté una descripció d'ella mateixa.
Per tant, les bases de dades també emmagatzemen descripcions de les dades que es guarden.

Aquestes dades de descripció s'anomenen __metadades__ (dades sobre les dades).
La forma i format de les metadades varia segons el SGBD utilitzat.

Les metadades es poden consultar per determinar les taules existents particulars,
els índexs o altres estructures existents en la base de dades i es troben
definides en les estructures que es coneixen com el __diccionari de dades (DD)__.


### Classificació de les bases de dades
Segons l'organització i estructura interna de les dades, podem classificar les bases
de dades en les següents categories:


#### Bases de dades jeràrquiques
Aquest tipus de bases de dades organitza la informació d'una
manera __jeràrquica__, és a dir, s'organitzen en una estructura
__d'arbre invertit__ on l'informació es guarda en cada node. De cada node,
poden crear-se nodes addicionals. El primer node s'anomena __arrel__, i sobre aquest,
es construeix tot l'arbre. Els últims nodes dels quals no descendeix cap node més s'anomenen
__fulles__.

Aquest model va començar a utilitzar-se en 1992 i va arribar a ser un dels models més utilitzats,
però amb el temps s'ha deixat d'utilitzar.

En aquest model Les connexions en l'arbre són fixes i l'accés a les dades es realitza d'una manera ràpida.
No obstant això, el principal desavantatge és que no es permeten relacions de molts a molts (N:M).

<figure id="figure-4">
    <img src="../img/hierarchical.png" alt="Base de dades jeràrquica">
    <figcaption class="attribution">https://www.geeksforgeeks.org/</figcaption>
    <figcaption>Figura 4: Base de dades jeràrquica</figcaption>
</figure>


#### Bases de dades en xarxa
Aquest tipus de bases de dades és molt similar al model jeràrquic, però en aquest
cas, les dades s'organitzen en una estructura de __graf__, el que permet crear
relacions de molts a molts (N:M).

<figure id="figure-5">
    <img src="../img/network.png" alt="Base de dades en xarxa">
    <figcaption class="attribution">https://www.geeksforgeeks.org/</figcaption>
    <figcaption>Figura 5: Base de dades en xarxa</figcaption>
</figure>


#### Bases de dades relacionals o SQL
Aquest model de bases de dades és el més utilitzat en l'actualitat.
Les __bases de dades relacionals__ és basen en el __Model relacional__,
enunciat per Edgar F. Codd en 1969. En aquest model, les dades s'organitzen
en __taules__ que poden estar relacionades enter elles.

Aquestes bases de dades també reben el nom de __bases de dades SQL__, ja que utilitzen
en __llenguatge SQL (Structured Query Language)__ per realitzar les consultes
a la base de dades.

<figure id="figure-6">
    <img src="../img/relational.png" alt="Base de dades relacional">
    <figcaption class="attribution">Autor desconegut</figcaption>
    <figcaption>Figura 6: Base de dades relacional</figcaption>
</figure>


##### Avantatges
- El més utilitzat i conegut pels desenvolupadors.
- S'han elaborat moltes eines al llarg del temps per facilitar la seua gestió.
- L'atomicitat de les operacions en la base de dades. En aquestes bases de dades,
o es fa l'operació sencera o no es fa. Possibilitat de tornar enrere amb `rollback`.
- Les dades han de complir requisits d'integritat.


##### Desavantatges
- L'atomicitat de les operacions penalitza el rendiment.
- L'escalabilitat, que encara que està provada en molts entorns, sol ser inferior a les bases de dades NoSQL.


#### Bases de dades NoSQL
La terminologia __bases de dades NoSQL__ s'utilitza per englobar
noves maneres d'organitzar les dades sense seguir el model relacional.
NoSQL significa __Not Only SQL__.

Depenent de l'estructura interna d'aquestes bases de dades, les característiques
i la utilització serà diferent. Es poden classificar en:

- __Documentals__: Les quals guarden la informació en documents. _Exemple: MongoDB o Firebase_.
- __Gràfiques__: Utilitzen grafs per modelar l'informació i són útlis per modelar
    relacions, com per exemple, en xarxes socials. _Exemple: Neo4j o TypeDB._
- __Clau valor__: Les dades s'organitzen en tuples, que emparella una __clau única__
    amb un __valor associat__ (com podria ser una agenda telefònica). _Exemple: Redis_.

Aquest tipus de bases de dades són flexibles, escalables i simplifiquen el desenvolupament
d'aplicacions web i en el núvol.


#### Bases de dades orientades a objectes
Una __base de dades orientada a objectes__ està dissenyada a partir del paradigma
dels llenguatges orientats a objectes.

##### Avantatges
- Molta capacitat de modelat.
- Es poden definir tipus de dades a partir d'altres ja existents (herència, especialització, ...)

##### Desavantatges
- No existeix un estàndard.
- Complexa d'utilitzar.

Aquest tipus de bases de dades no ha arribat a utilitzar-se d'una manera global,
ja que els llenguatges orientats a objectes han trobat maneres d'accedir 
a les bases de dades relacionals. _Exemple: ObjectDB_


#### Bases de dades objecte relacionals
Les __bases de dades objecte relacionals__ es caracteritza per combinar els aspectes més rellevants
de les bases de dades relacionals i les bases de dades orientades a objectes. Aquestes bases de dades
permeten l'emmagatzematge d'objectes, però també permeten la utilització __SQL__, com les bases
de dades tradicionals.


## Bibliografia
- Material de Laura Villalba, _Introducció a les bases de dades_.
- Ahijado Sánchez, A, _Bases de datos_, Ed. Marcombo.
- https://ioc.xtec.cat/materials/FP/Recursos/fp_dam_m02_/web/fp_dam_m02_htmlindex/WebContent/u1/a1/continguts.html
- https://en.wikipedia.org/wiki/Graph_database
- https://en.wikipedia.org/wiki/Key%E2%80%93value_database
- https://www.tutorialspoint.com/object-and-object-relational-databases
- https://www.geeksforgeeks.org/difference-between-hierarchical-and-network-data-model/

