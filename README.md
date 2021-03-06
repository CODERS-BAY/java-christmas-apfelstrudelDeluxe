# Christmas Exercise :santa:
## Wiederholung der Vererbung und der Objektorientierung

Bitte versuche als Übung alles in Markdown zu beantworten. Hier ist ein [Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

1. Was ist das Ziel der Objektorientierung?

 Detailliete Beschreibung von Dingen bzw. so genannten Objekten. Z.B. Beschreibung eines Autos. Das Ziel dabei ist ein Objekt so gut/ detailliert zu Beschreiben, dass man es darstellen/ programmieren kann. Es gibt verschiedene Detailgrade. Man kann ein Objekt in einem Objekt beschreiben und so die Komplexität aufsplitten.

 Bei objektorientierten Programmieren zerlegt man Dinge in einzelne Objekte mit Eigenschaften und Methoden. Mit dieser Herangehensweise kann man komplete Aufgabenstellungen in kleine Teile zerlegen (abstrahieren) und strukturiert im Code umsetzen. 

**Objekt = Auto**

**Objekt Motor im Auto**

Die Beschreibung von Objekten: Eigenschaften oder Attribute

**Eigenschaften von Auto**
* Rad
* Tür
* Farbe
* Lenkung
* Motor

**Eigenschaften von Motor**
* Antrieb
* Hubraum
* Energiequelle

Was ein Objekt machtmachen kann = Funktionen oder Methoden
Mit Befehlen werden die Funktionen im Objekt benutzt. 

**Methoden im Objekt Auto: fahren, lenken**

Obkejte haben Eigenschaften und Methoden.
Alles mit Struktur und Details ist ein Objekt. Man muss ein Objekt nicht anfassen können. Es kann auch abstrakt sein wie z.B. 


2. Gibt es OOP nur in Java?

Es gibt eine Menge an objektorientierter Programmiersprachen. Z.B. Java, Javascript. 
Komplette Liste: https://de.wikipedia.org/wiki/Liste_objektorientierter_Programmiersprachen

3. Was ist der Unterschied zwischen Objekt und Klasse?

Eine Klasse ist ein Bauplan für Objekte und beinhaltet mehrere Objekte mit entsprechenden Eigenschaften. Z.B. aus welchen Objekten besteht ein Auto?

**Klasse Auto hat z.B. 2 Objekte**

autoObject1 = 4 Räder, 3 Türen, grün

autoObject2 = 4 Räder, 5 Türen, blau


Klasse Auto mit 2 versch. Auto-Objekten:
 
![alt text][logo]

[logo]: https://openbook.rheinwerk-verlag.de/actionscript_einstieg/bilderklein/kleinklasse_objekt.gif "Klasse Auto mit 2 versch. Auto-Objekten"


4. Wie erzeuge ich eine neue Instanz? (Welches Schlüsselwort gibt es dafür)

Objekte sind Instanzen von Klassen und werden mit dem new-Operator erzeugt. 
Dazu braucht man zuerst eine Variable und dann new.

```
Auto autoObjekt;      
autoObject1 = new Auto();
```
Der neuen Instanz Werte zuweisen:
```
autoObject.tyres = 4;
autoObject.doors = 3;
autoobject.color = "green";
```

5. Was bedeutet das Schlüsselwort `static` und wo kann es überall verwendet werden?

**static bei Variablen:** Static wird als Schlüsselwort bei Klassenvariablen verwendet. Sie gehören nicht zum einzelnen Objekt, sondern zur Klasse. Mit dem Modifikator final (also static final) kann man eine Konstante erstellen = globale Variablen.

Wird nur einmal angelegt und kann von allen Objekten der Klasse aufgrrufen werden. 

**static bei Methoden:** Existiren unabhängig vom Objekt und werden über eine Klase aufgerufen. (klassenname.methodenname)


6. Wozu dient die Vererbung?

Durch das Prinzip der Vererbung werden Merkmale von bereits vorhandenen Klassen auf andere Klassen abgeleitet.

**Klasse Auto**

**Vererbung von Eigenschaften wie Rad, Tür, Farbe auf andere Klassen: LKW, Traktor,...**

**Eigenschaften von LKW:**
* Nutzlast
* Anzahl Anhänger

**Eigenschaften von Traktor**
* Anhängerkupplung
* Lastenschaltung
* Hydraulik


7. Kann in Java von mehreren Klassen geerbt werden? Wenn ja wie?

Mit "extends" ist nur eine Einfachvererbung möglich. Jede Klasse erbt nur von einer Klasse. 

Eine Mehrfachvererbung ist mit Interfaces möglich. http://u-helmich.de/inf/kursQ1/folge16/folge16-3.html


8. Welche Vererbungshierarchien kennst du? (Ein Bild reicht aus)

Beispiel der Vererbung der Superklasse Lebewesen auf die einzelnen Klassen von Lebewesen (Tier, Mensch, Pflanze): 
![alt text](https://mein-javablog.de/wp-content/uploads/2017/02/Java-Vererbung-Lebewesen.png)


9. Was beudeted Casten und wie ist die Syntax in Java dafür?

Casten bedeutet Typumwandlung oder Typkonvertierung. Ein Datentyp wird in einen anderen Datentyp umgewandelt.

Beim Casten muss man aufpassen, dass man keine Typverletzungen begeht. Beide Datentypen müssen miteinander kompatibel sein.

Int --> Double: 9 --> 9.00
Double --> Int: 9.99 --> 9 (Achtung vor Informationsverlust!)

10. Was ist der Unterschied zwischen explizieten und implizieten Typecasting?

**Explitites Casten**

Im Code wir explizit darauf hingewiesen mit Verwendung des Cast-Operators.

z.B. Double wird in Int umgewandelt

```
double zahl = 7.9;
int zahl2 = (int) zahl;
```

**Implizites Casten**
Hier wird nicht extra im Code darauf hingewiesen, sondern die Umsandlung automatisch vom Compiler durchgeführt.

z.B. Int wird in Double umgewandelt

```
int zahl = 10;
double zahl2 = zahl;
```


11. Erkläre die folgenden Schlüsselwörter: `super`, `this`

**super**

Mit "super" ruft man den Konstruktor einer Oberklasse (Superklasse) auf, von dem auf eine darunterliegende Klasse vererbt wird.

Standardkonstruktor anlegen:

```
public abstract class Auto {
	
protected String color = null;
	
	Auto(String color){
		this.color = color;
      }

```
Den String-Parameter mit der Farbe des Autos bis zur Oberklasse durchschleusen.

```
public class Motor extends Auto{
	
public Motor(){

   Motor(String color){
    	super(color);
    }
}
```
Beim Erzeugen des Motor-Objekts gleich den Parameter color mitgeben.

```
Motor motorObject1 = new Motor("red");
```



**this**

"this" hilft bei Nahmenskonflikten. Wenn Attribut und Wert einen Übergabeparameters ident sind.

this.attribut = value;

Beispiel im Detail: http://www.codeadventurer.de/?p=2631

12. Für was dient der `instanceof` Operator. Gib ein sinnvolles Beispiel.

Mit "instanceof" wird geprüft, ob ein Objekt eine Instanz einer bestimmten Klasse ist. Subklassen sind z.B. automatisch immer auch eine Instanz von der Superklasse. Umgekehrt ist das nicht der Fall. Der Rückgabewert ist ein Boolean. (true oder false)




