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


## 1. Les funcions poden rebre (o no) valors d'entrada, que seran processats dins del bloc de codi.

**Quan definim la funció:** declarem les variables d'entrada que necessita la funció, indicant el tipus de dada i donant-lis un nom.  **Aquestes variables d'entrada s'anomenen PARÀMETRES d'entrada.**  _Poden haver un nombre indeterminat de paràmetres d'entrada, des de 0 fins a varis, tot i que el més habitual és que el nombre de paràmetres d'entrada d'una funció no sigui superior a 3 o 4. Un nombre de paràmetres més gran de 4 indica un mal disseny de la funció._

**Quan cridem la funció:** usant el nom de la funció, li passem un valor concret per a cadascun dels paràmetres declarats en la definició de la funció. Aquests valors que passem a la funció, s'anomenen ARGUMENTS de la funció. _No podem passar un argument que sigui d'un tipus de dada diferent que el declarat per al paràmetre corresponent en la definició de la funció._

**Les funcions poden no rebre cap argument si estan definides amb 0 paràmetres.**

**L'ordre dels arguments passats en cridar la funció es correspon amb l'ordre en què els paràmetres estan declarats en la definició de la funció.**

_A tenir en compte:_

Per exemple, una funció que calcula el quadrat d'un nombre enter, pot obtenir el valor del nombre enter del qual vol calcular-ne el seu quadrat de dues maneres:

  a. Llegint el valor d'una variable d'àmbit global, o d'àmbit més extern.

  b. Llegint el valor que se li ha passat com a argument, i que correspon a un paràmetre, quan s'ha cridat la funció.

_L'opció_ **a** _és totalment desaconsellable. Sempre optarem per usar els paràmetres d'entrada._

## 2. Les funcions poden retornar (o no) un valor de sortida, com a resultat obtingut en executar-se les instruccions de dins del bloc de codi.

Com a resultat d'executar-se les instruccions que hi ha dins del bloc de codi d'una funció, es pot obtenir un resultat com a valor, o no.

La funció pot no obtenir cap valor com a resultat de l'execució de les seves instruccions. En aquest cas, no retornarà res. Per exemple: una funció que imprimeixi per pantalla.

_A tenir en compte:_

Per exemple, una funció que calcula el quadrat d'un nombre enter, obtindrà com a resultat el quadrat d'un nombre enter, i aquest resultat el pot guardar en: 

  a. Una variable d'àmbit global, o d'àmbit més extern, a la que li assignarà el resultat obtingut.

  b. Retornant el resultat obtingut com a valor de retorn de la funció.

_L'opció_ **a** _és totalment desaconsellable. Sempre optarem per a retornar el valor del resultat obtingut._


## 3. Les funcions poden modificar l'estat de l'entorn.

Una funció pot (o no) modificar l'estat del seu entorn.

Entenem per **entorn** qualsevol àmbit de variables extern al bloc de codi de la funció.

Entenem per **estat** el conjunt de valors que tenen assignats les diferents variables d'àmbits externs a la funció. _Quan almenys una variable d'àmbit extern a la funció canvia de valor, direm que **l'entorn de la funció ha canviat d'estat**._

_A tenir en compte:_ 

**No és aconsellable que les variables canvïin l'estat del seu entorn.** Una programació ben dissenyada evita que això passi.



