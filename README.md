# PROGRAMMING
# Functions

Author: Oriol Boix Anfosso (orboan@ilg.cat) 

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
BiFunction<Double, Double, Double> g = (x, y) -> 2.0*x + y
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

## Signatura d'una funció

La signatura d'una funció està composta de:

   a. El nom de la funció
   b. Els seus paràmetres d'entrada (nombre, ordre, tipus de dada i nom)
   
 El valor de retorn d'una funció **no forma part de la seva signatura** tot i que per costum s'hi inclogui habitualment.
 
 _Exemples:_
 
 ```
 int findMax(int[] array);
 void printMessage(char[] letters);
 boolean isEmpty(double[] array);
 double getPolynomialZerosDivision(double x, double y, int a, int b);
 ```
 
 En el primer cas, la funció findMax espera rebre com a argument el valor d'un array d'enters, i retornarà un enter.
 
 En el segon cas, la funció printMessage espera rebre com a argument el valor d'un array de chars, i no retornarà res (doncs no calcula cap resultat, simplement imprimeix per pantalla).
 
 En el tercer cas, la funció isEmpty espera rebre com a argument un array de doubles, i retornarà com a resultat un booleà (true o false).
 
 En el quart exemple, la funció getPolynomialZeros espera rebre com a arguments els valors (i en aquest ordre) d'un double, d'un altre double, d'un int i d'un altre int. Retornarà com a resultat un valor de tipus double.
 
 _A tenir en compte:_
 
  Les funcions de les quals només s'escriu la seva signatura (amb el tipus de dada de retorn) i es finalitza amb un punt i coma (;) s'anomenen **FUNCIONS ABSTRACTES**.
  
  Tota funció abstracta té pendent de completar-se amb el **COS DE LA FUNCIÓ** (bloc de codi de la funció amb les seves instruccions). Quan un programador escriu el cos d'una funció abstracta, diem que el programador està **IMPLEMENTANT** la funció (respectant la seva signatura).
  
## Function descriptor

El descriptor d'una funció ens indica quins són els tipus de dades dels paràmetres d'entrada (si n'hi ha), i quin és el tipus de dada del valor de retorn (si n'hi ha).

_Exemples:_

Els següents exemples són els descriptors de funcions corresponents a les signatures de funcions posades com a exemples en l'apartat anterior:

```
int[] -> int
char[] -> void
double[] -> boolean
(double, double, int, int) -> double
```

El següent exemple és el descriptor d'una funció que no té cap paràmetre d'entrada i que no retorna res:

```
() -> void
```

Un exemple d'una funció que compleix aquest descriptor, és la següent funció:

```
void sayHello() {
   print("Hello!");
}
```

## Varargs (...)

A vegades necessitem una funció a la que, en el moment de definir-la, no sabem encara quants arguments li necessitarem passar. És a dir, podem necessitar una funció que, en cridar-la, a vegades li vulguem passar més arguments, i d'altres vegades menys.

Per exemple:

Volem crear una funció que ens calculi la mitjana de notes d'un grup d'alumnes, però la quantitat d'alumnes pot canviar depenent de la classe:

```
double getAverage(double ... qualifications) {
   int length = qualifications.length;
   double suma = 0;
   for (int i = 0; i < length; i++){
      suma += qualifications[i];
   }
   return suma / length;
}
```

Exemples de com podem cridar aquesta funció:

```
//Per a una classe de 4 alumnes
double average = getAverage(5.0, 6.5, 7.0, 3.8); 

//Per a una classe de 8 alumnes
double average = getAverage(5.0, 6.5, 7.3, 2.6, 6.2, 5.4, 7.0, 8.2);
```

La notació dels paràmetres corresponents als _varargs_ és la de posar el tipus de dada, tres punt suspensius (...) i el nom de la variable. **Internament, dins del cos de la funció, la variable del paràmetre serà considerada com un ARRAY de mida el número total d'arguments que se li passin quan es crida la funció.**


## Predicats

Els predicats són funcions pures que compleixen amb el següent descriptor:

```
(T...) -> boolean
```
essent T qualsevol tipus de dada, i ... és la notació varags, de manera que podem llegir aquest descriptor com: és un predicat tota funció que rebi com a paràmetres d'entrada qualsevol número de paràmetre de qualsevol tipus de dada, però que **sempre** retorna un booleà.

## Function Overriding

Sempre podem definir una nova funció que tingui la mateixa signatura que una altra prèviament definida (mateix nom de funció i mateix nombre, ordre i tipus de dada de paràmetres). Per exemple, suposem que tenim definida la següent funció:

```
int calculateSum(int[] elements) {
   int sum = 0:
   for(int i = 0; i < elements.length; i++){
       sum += elements[i];
   }
   return sum;
}
```

Però ens demanen, posteriorment, que aquesta funció imprimeixi per pantalla la suma acumulada en cada iteració. Per tant, necessitarem tornar a escriure-la:

```
int calculateSum(int[] elements) {
   int sum = 0:
   for(int i = 0; i < elements.length; i++){
       sum += elements[i];
       println(sum);
   }
   return sum;
}
```

Quan això passa, diem que la nova funció calculateSum fa un **overriding** (sobreescriu) de l'anterior (amb la mateixa signatura), de manera que l'anterior es perd, i és la darrera definició la que és ara vàlida.

_A tenir en compte:_

Cal tenir en compte que els noms dels paràmetres i el tipus de dada de retorn són irrellevants. Perquè l'overring tingui efecte, només cal que el nom de la funció sigui igual que el d'aquella que volem sobreescriure, i també el tipus de dada dels paràmetres i l'ordre en què apareixen a la signatura de la funció. Per exemple, la següent funció també farà un overriding de l'anterior:

```
long calculateSum(int[] numbers) {
   ...
   return longVar;
}
```

## Function Overloading

La sobrecàrrega de funcions (en anglès: Function Overloading) té lloc quan definim una funció que té el mateix nom que una altra funció que s'ha creat anteriorment, però que té una signatura diferent.

És a dir, quan la nova funció tot i anomenar-se igual que una d'anterior ja existent, té diferents paràmetres (en nombre i / o en tipus de dada) que l'anterior funció.

Per exemple:

```
long calculateSum(int[] numbers) {
   ...
   return longVar;
}
```

La següent funció és una sobrecàrrega (overloading) d'aquesta darrera funció (calculateSum):

```
long calculateSum(long[] numbers) {
   ...
   return longVar;
}
```

Un altre exemple. Tenim:

```
int calculateSumByStep(int[] numbers) {
   int step = 1;
   ...
   return intVar;
}
```

La següent funció és una sobrecàrrega de l'anterior:
```
int calculateSumByStep(int[] numbers, int step) {
   ...
   return intVar;
}
```

_A tenir en compte:_

Quan hi ha overloading de funcions, no es sobreescriu cap funció, és a dir, **totes les diferents versions de la funció estan disponibles**. Java escollirà la versió apropiada a executar segons els tipus de dades i nombre i/o ordre dels arguments que es passen en cridar la funció.

## Regles per a escriure bones funcions

1. **Una funció ha de fer una sola cosa.**

Per exemple, calcular el factorial. Si la funció que calcula el factorial, a més, ha de llegir el número enter del qual n'ha de fer el càlcul (des d'una base de dades o un fitxer, o llegir-lo com a valor introduit per un usuari des d'un formulari) i/o, a més, ha d'imprimir el resultat per pantalla o guardar-lo en algun lloc (base de dades, fitxers...), tenim una funció **mal dissenyada**, doncs no fa **només** 1 cosa.

En aquest cas, serien altres funcions les que s'encarregarien d'obtenir el valor int del qual es vol fer el càlcul del factorial, i serien altres funcions les que s'encarregarien de guardar el resultat obtingut en algun lloc o d'imprimir-lo per pantalla.

2. **Cal no usar més de 3 o 4 paràmetres.**

Tenir molts paràmetres és un senyal que la funció fa més d'una cosa. A més, serà difícil recordar per part del programador el significat de masses paràmetres usats al mateix temps.

3. **Cal seguir els convenis.**

Cal seguir els convenis en els noms de les funcions, és a dir:
   * Els noms han de ser autodescriptius.
   * Poden ser tant llargs com es necessiti.
   * Escrits en minúscula. Només posem en Majúscula la primera lletra de la segona i successives paraules, en cas que el nom estigui compost de dos o més paraules.
   * No usem caràcters separadors.
   * Usem paraules de l'idioma anglès.
   * Els noms dels predicats sempre tenen el prefix _is_ o _has_.
   
 _Quins dels següents noms segueixen el conveni de noms de funcions en Java?_
 
 ```
 1. void getCloser();
 2. boolean is_Mine(char c);
 3. byte CheckBytes(byte[] b);
 4. int[] getMyFavoritenumbers();
 5. void prt("Hello");
 6. boolean tryEquals(char c);
 ```
 
 Només l'exemple 1 segueix el conveni.
 
 L'exemple 2 és incorrecte perquè té un separador entre paraules (_ en aquest cas).
 
 L'exemple 3 és incorrecte perquè comença amb majúscula.
 
 L'exemple 4 és incorrecte perquè la paraula _numbers_ comença en minúscula.
 
 L'exemple 5 és incorrecte, perquè del nom de la funció no es pot saber què fa la funció (què vol dir _prt_?, _prt_ no és una paraula de l'idioma anglès).
 
 L'exemple 6 és incorrecte perquè retorna un booleà (és un predicat) i el nom de la funció no comença per _is_ o _has_.
 
 #### Per altra banda, cal seguir el conveni de la indentació, per a fer el codi més llegible: el contingut de cada bloc de codi ha d'estar indentat.
 
 # EXEMPLES
 
 1. Crea una funció que rebi un array d'enters, i retorni un altre array d'enters que contingui els números parells trobats a l'array d'entrada.
 
 ```
 int[] getEvenNumbersArray(int[] numbers){
   int newArraySize = 0;
   for(int i = 0; i < numbers.length; i++) {
      if(numbers[i] % 2 == 0) {
         newArraySize++;
      }
   }
   int[] evenNumbersArray = new int[newArraySize];
   if(newArraySize != 0){
      int i = 0, j = 0;
      while(i < numbers.length) {
         if(numbers[i] % 2 == 0) {
            evenNumbersArray[j] = numbers[i];
            j++;
         }
         i++;
      }
   }
   return evenNumbersArray;
}
```

_Explicació:_

Com que els arrays, a Java, són de mida fixa, caldrà primer esbrinar quina és la mida de l'array a retornar per la funció. La mida d'aquest array a retornar serà el número (quantitat) de nombres parells que hi ha dins de l'array que es passarà com a argument en cridar la funció.

Això ho calculem a la primera part del codi del cos de la funció. Creem una variable local `newArraySize` que guardarà la mida de l'array a retornar, és a dir, la quantitat d'enters parells que hi ha dins de l'array d'entrada.

**Recorrem** l'array d'entrada i, a cada iteració del bucle, anem sumant 1 a la variable `newArraySize` si l'enter (valor de l'array d'entrada donat per `numbers[i]`) que estem avaluant en el condicional, és parell. Si no és parell, no fem res i seguim a la següent iteració.

```
   int newArraySize = 0;
   for(int i = 0; i < numbers.length; i++) {
      if(numbers[i] % 2 == 0) {
         newArraySize++;
      }
   }
```

Un cop sabem quants nombres parells haurà de contenir l'array a retornar, creem l'array a retornar:

```
int[] evenNumbersArray = new int[newArraySize];
```

Si la mida de l'array creat és 0 (és a dir, no em trobat cap número parell a l'array d'entrada) llavors no cal fer res més i retornarem un array buit (no s'executa el codi dins del bloc de codi de _`if(newArraySize != 0)`_ i es passa directament a la instrucció `return`). 

En cas que la mida de l'array sigui diferent de 0, caldrà anar guardant a l'array a retornar tots els nombres parells que hi ha a `numbers`.

Per tant, cal recorrer de nou l'array d'entrada `numbers` (usant l'índex _i_) i si el número que hi trobem (amb `numbers[i]`) és parell, llavors guardarem aquest valor a dins de l'array a retornar, que es va recorrent amb l'índex _j_. L'índex _j_ només avança (_j++_) quan es troba un número parell i es guarda a l'array a retornar.

```
   if(newArraySize != 0){
      int i = 0, j = 0;
      while(i < numbers.length) {
         if(numbers[i] % 2 == 0) {
            evenNumbersArray[j] = numbers[i];
            j++;
         }
         i++;
      }
   }
```
