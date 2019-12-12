# PROGRAMMING
# Functions

Les funcions són blocs de codi que executen un conjunt d'instruccions, amb les següents característiques:

1. Poden (o no) rebre valors d'entrada, que seran processats dins del bloc de codi.
2. Poden (o no) retornar un valor de sortida, com a resultat obtingut en executar-se les instruccions de dins del bloc de codi.
3. Poden modificar l'estat de l'entorn.
4. Totes les variables declarades dins del bloc de codi de la funció són variables locals i moren quan el bloc de codi es tanca.
5. Les variable locals dins d'una funció no tenen valors per defecte. Per tant, és obligatori assignar-lis un valor.
6. Les funcions poden ser anònimes, o se'ls pot assignar un nom.

_A tenir en compte:_

**Les funcions, a l'igual que les variables i altres estrutures de programació, primer s'han de definir, per a poder ser usades a continuació.**

**Quan usem una funció amb nom en un moment posterior a la seva definició, direm que estem CRIDANT la funció, que s'executarà en aquell moment (en el moment de ser cridada).**

**Quan es crida una funció, el control del fluxe d'execució es transfereix a dins del bloc de codi de la funció, i un cop s'ha acabat l'execució de totes les seves instruccions (amb valor de retorn o no) arribant al tancament del bloc de codi, llavors es transfereix de nou el control del fluxe d'execució a la següent línia de codi des d'on s'ha cridat la funció.**


### 1. Les funcions poden rebre (o no) valors d'entrada, que seran processats dins del bloc de codi.

**Quan definim la funció:** declarem les variables d'entrada que necessita la funció, indicant el tipus de dada i donant-lis un nom.  **Aquestes variables d'entrada s'anomenen PARÀMETRES d'entrada.**  _Poden haver un nombre indeterminat de paràmetres d'entrada, des de 0 fins a varis, tot i que el més habitual és que el nombre de paràmetres d'entrada d'una funció no sigui superior a 3 o 4. Un nombre de paràmetres més gran de 4 indica un mal disseny de la funció._

**Quan cridem la funció:** usant el nom de la funció, li passem un valor concret per a cadascun dels paràmetres declarats en la definició de la funció. Aquests valors que passem a la funció, s'anomenen ARGUMENTS de la funció. _No podem passar un argument que sigui d'un tipus de dada diferent que el declarat per al paràmetre corresponent en la definició de la funció._

**Les funcions poden no rebre cap argument si estan definides amb 0 paràmetres.**

**L'ordre dels arguments passats en cridar la funció es correspon amb l'ordre en què els paràmetres estan declarats en la definició de la funció.**

_A tenir en compte:_

Per exemple, una funció que calcula el quadrat d'un nombre enter, pot obtenir el valor del nombre enter del qual vol calcular-ne el seu quadrat de dues maneres:

  a. Llegint el valor d'una variable d'àmbit global, o d'àmbit més extern.

  b. Llegint el valor que se li ha passat com a argument, i que correspon a un paràmetre, quan s'ha cridat la funció.

_L'opció_ **a** _és totalment desaconsellable. Sempre optarem per usar els paràmetres d'entrada._

### 2. Les funcions poden retornar (o no) un valor de sortida, com a resultat obtingut en executar-se les instruccions de dins del bloc de codi.

Com a resultat d'executar-se les instruccions que hi ha dins del bloc de codi d'una funció, es pot obtenir un resultat com a valor, o no.

La funció pot no obtenir cap valor com a resultat de l'execució de les seves instruccions. En aquest cas, no retornarà res. Per exemple: una funció que imprimeixi per pantalla.

_A tenir en compte:_

Per exemple, una funció que calcula el quadrat d'un nombre enter, obtindrà com a resultat el quadrat d'un nombre enter, i aquest resultat el pot guardar en: 

  a. Una variable d'àmbit global, o d'àmbit més extern, a la que li assignarà el resultat obtingut.

  b. Retornant el resultat obtingut com a valor de retorn de la funció.

_L'opció_ **a** _és totalment desaconsellable. Sempre optarem per a retornar el valor del resultat obtingut._


### 3. Les funcions poden modificar l'estat de l'entorn.

Una funció pot (o no) modificar l'estat del seu entorn.

Entenem per **entorn** qualsevol àmbit de variables extern al bloc de codi de la funció.

Entenem per **estat** el conjunt de valors que tenen assignats les diferents variables d'àmbits externs a la funció. _Quan almenys una variable d'àmbit extern a la funció canvia de valor, direm que **l'entorn de la funció ha canviat d'estat**._

_A tenir en compte:_ 

**No és aconsellable que les funcions canvïin l'estat del seu entorn.** Una programació ben dissenyada evita que això passi.

### 4. Totes les variables declarades dins del bloc de codi de la funció són variables locals i moren quan el bloc de codi es tanca.

Dins del bloc de codi d'una funció es poden declarar, inicialitzar i usar tantes variable com sigui necessari, que existiran només dins d'aquest àmbit local, és a dir, quan el bloc de codi de la funció es tanqui o quan es retorni un valor, totes aquestes variables locals deixaran d'existir i ja no seran accessibles.

_A tenir en compte:_ 

**Les variables declarades com a paràmetres de la funció són variables locals de la funció.**

Si una variable local, dins d'una funció, té el mateix nom que una variable d'àmbit extern a la funció, la local farà **shadowing** sobre l'externa o global.

### 5. Les variable locals dins d'una funció no tenen valors per defecte. Per tant, és obligatori assignar-lis un valor.

_Exemple_:

El següent codi és vàlid en un àmbit extern a una funció:

```
int n;
int square = n*n;
```

Aquest mateix codi, però, **llençarà una excepció (error) si s'executa dins d'una funció.**

**Explicació:** en l'àmbit extern, la variable n tindrà assignat un valor per defecte, i quan aquesta variable s'usa en el l'expressió _n*n_ se li aplicarà aquest valor per defecte. En canvi, dins d'una funció les variables locals no tenen valors per defecte, per tant en intentar avaluar _n*n_ veurà que no té cap valor assignat i no podrà executar l'expressió (retornant un error).

### 6. Les funcions poden ser anònimes, o se'ls pot assignar un nom.

El motiu principal per a crear una funció és la **REUTILITZACIÓ DE CODI**. Per tant, evitar que hi hagi codi repetit. **Codi repetit indica un mal disseny del programa.**

Una de les principals regles de bones pràctiques de programació és la **reutilització de codi** i evitar al màxim la repetició de codi. La repetició de codi és un dels principals indicadors per a detectar un programa mal dissenyat.

La repetició de codi i altres senyals de mala programació, com un ús innecessari de condicionals i bucles, és el que es coneix com **bad smells**.

_A tenir en compte:_

Quan una funció només l'hem de cridar **un sol cop** en tot el nostre programa, no cal que se li assigni nom i se la pot definir com a funció anònima. Més endavant veurem exemples.

## Funcions pures

Les funcions pures són aquelles que, per al mateix valor dels paràmetres d'entrada, **sempre** retorna el mateix resultat. 

Les funcions matemàtiques són funcions pures.

_Exemples de funcions pures:_

```
Function<Integer, Integer> f = x -> x*x
BiFunction<Double, Double, Double> g = (x, y) -> 2*x + y
Supplier<String> s = () -> "This is amazing!"
```

(Nota: no us preocupeu si no enteneu ara aquesta notació).

_Exemple de funció no pura:_

```
int edat = 23;
int newAge(int increment){
    return edat + increment;
}
int novaEdat = newAge(2); //Retorna 25
edat = novaEdat;
novaEdat = newAge(2); //Retorna 27
```

_Explicació:_ la funció newAge no és pura, doncs per al mateix valor d'entrada (2) no retorna sempre el mateix resultat o valor de sortida (en el primer cas retorna 25, i en el segon, 27).




