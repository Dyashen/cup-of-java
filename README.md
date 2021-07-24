# Cup Of Java ☕
Hallo! Ik ben Dylan Cluyse. Washed-up student leerkracht secundair onderwijs en nu student Toegepaste Informatica aan Hogeschool Gent. In deze Github repo wil ik vooral de basis voorleggen van programmeren met Java. Deze leerinhoud is gebaseerd op basis van het curriculum 2020-2021 en omvat zowel "OOSD1" als "OOSD2".

Met deze GitHub page wou ik de materie in een andere vorm gieten. Hier worden onder meer andere voorbeelden tonen en een nadruk op aanschouwelijke schema's en structuren. De structuur is ook redelijk anders, maar volgt volledig dezelfde inhoud. 

!! De page is nog volledig work-in-progress. Mocht je vragen of opmerkingen hebben, laat me gerust weten via Discord!

Handige websites:
- JavaTpoint
- W3schools
- Jenkov Tutorials






# 1. [Inleiding] 

## Opbouw van een simpele applicatie binnen een IDE

Voor het programmeren in Java heb je verschillende IDE's. Een IDE is een editor die wordt gebruikt om code op te bouwen en later te kunnen uitvoeren. Een functie bij de meeste IDE's is om te zien of je fouten hebt gemaakt in je code. Deze worden dan rood onderstreept en is vergelijkbaar met spellingsfouten bij het programma Word.

Vooraleer we kijken naar de code moeten we eerst een structuur opbouwen in onze compiler. Hiervoor maken we gebruik van packages waar we onze klassen/interfaces/enums gaan opslaan. 

Een **klasse** is een soortgelijk sjabloon waarin we later meer gebruik van gaan maken eenmaal we ons gaan focussen op object-geörienteerd programmeren. Meerdere klassen gaan we opslaan in een package om structuur te behouden.

Een package maak je als volgend aan: Eerst selecteer je de source map, daarna maak je iets nieuws aan en dat nieuwe onderdeel is een package. Je geeft je een package een toepasselijke naam.

![Package aanmaken in Eclipse.](https://i.imgur.com/kSac0T8.png)

## Drielagenmodel

Nu kunnen we klassen aanmaken binnenin één van de packages. Later gaan we ook zien dat we ook enums en interfaces kunnen aanmaken, maar dat komt pas later aan bod. We volgen de zelfde stappen, maar selecteren "Class" in plaats van "Package". 

We mogen wel klasses niet zomaar in eender welke package gaan plaatsen. We moeten rekening houden met het drielagenmodel. Dit is één van de vier pijlers van object-georiënteerd programmeren waar er ook gedurende deze cursus rekening mee zal worden gehouden. Het drielagenmodel wordt gebruikt om structuur te behouden binnen onze applicatie.

![image](https://user-images.githubusercontent.com/70543493/125161421-995dee00-e182-11eb-8d7c-a3755c8f528f.png)

Naast de drie vermelde lagen heb je ook nog de **main-klasse**. Dit is het aanspreekpunt om de applicatie op te starten. Het is van belang dat we een main-klasse hebben, want anders kunnen we ons programmaatje niet opstarten.

```java
//programma die bij het opstarten een lijntje tekst in de console gaat schrijven
public static void main(String[] args) {
	System.out.println("Hallo!");
}
```


## Opbouw van een klasse.

Eenmaal onze structuur is opgebouwd kunnen we beginnen met ons allereerste lijntje code te schrijven. Ter illustratie heb ik een kort code-blokje opgesteld om de essentials nog eens te doorlopen van wat er allemaal terecht moet komen in een klasse. 

Let op: We kunnen commentaar toe voegen door gebruik te maken van '//' ofwel twee schuine streepjes. Alles na deze twee strepen wordt gezien als commentaar en niet meer als functionele code.

1. Je klasse gaat altijd beginnen met een "**package** x": Dit is een verwijzing naar de package waarin jouw klasse zich bevind. In dit geval zit onze klasse in de package CUI.
2. **"Import"** verwijst naar bepaalde methodes/functies die onze IDE moet invoeren om diezelfde functies te kunnen uitvoeren bij het compilen. Als dit niet gebeurt zal je een foutmelding krijgen bij het compilen. Hier voeren wij bijvoorbeeld de Scanner functie in om zo invoer te kunnen vragen van de gebruiker.
3. WillekeurigGetal is een **klasse** die we hebben opgebouwd. Hierin kunnen we meerdere methodes aanmaken waarin we bepaalde zaken kunnen uitvoeren of aanpassen. Hier hebben we enkel en alleen onze "main" methode in staan.
4. De **main** methode zit binnen in onze klasse. Deze gaat worden gebruikt om het programma op te kunnen starten. Extra info: args bevat de meegegeven command-line argumenten die worden opgeslagen in een array van String-objecten. Hier moet je vooral geen rekening mee houden en dit gaan we ook niet veranderen want anders gaat ons programma niet meer goed functioneren.
5. We willen een variabele **declareren** en hier een waarde aan toewijzen. De Scanner komt later aan bod, maar voor de uitleg van declareren ga ik het voorbeeld van het willekeurigGetal gaan gebruiken. Als we binnen Java een variabele willen declareren MOETEN we eerst meegeven van welk primitief datatype deze variabele is. Binnen Java werken we met 
* integers (int = reële getallen die we gebruiken voor op te tellen)
* strings (String => enkel tekst + hoofdlettergevoelig!)
* double (Double => ook rekenen en wordt gebruikt voor kommagetallen)
* booleaanse waarden (Boolean => enkel true/false)
* float (float => uitbreiding op Double en wordt gebruikt voor kommagetallen met grotere waarden na de komma)
6. Als we iets willen **uitprinten** in onze console maken we gebruik van "System.out.println()" met tussenin de twee ronde haakjes tekst. De tekst begin en eindig je met een dubbele aanhalingsteken. We kunnen echter géén variabele meegeven zoals bij JavaScript waar we gebruik maken van ${variabeleNaam}. Hier moeten we een ander soort functie gaan gebruiken en die noemt _System.out.printf()_. Tussen de haakjes zijn we verplicht om minstens twee argumenten mee te geven. 
* Het eerste is de tekst die we willen dat ons programmaatje uit print. In dit geval willen we dat ons programma zegt "Jouw ingegeven getal is 'x'" waarbij x het getal is dat de gebruiker daarnet heeft ingegeven. Voor iedere variabele gebruiken we %s. 
* Onze volgende argument(en) zijn de variabelen die we willen meegeven. We gebruiken de naam van de variabele die we willen uitprinten. Als je meerdere variabelen wilt gebruiken (zoals verder in de code) kan je ze opsommen door na iedere variabele een komma te plaatsen. Hou rekening met de volgorde waarin je de argumenten aanspreekt.
7. We hebben als laatste een controlestructuur. De bedoeling van if() is een vergelijking maken tussen twee waarden. Als deze voldoet gaan we een bepaalde operatie uitvoeren, als dit niet zo is gaan we een andere operatie uitvoeren. Dit komt in het tweede hoofdstuk aan bod.


```java
package cui; //1

import java.util.Scanner; //2

public class WillekeurigGetal { //3

	public static void main(String[] args) { //4
		
		Scanner invoerVanGebruiker = new Scanner(System.in); //5
		
		System.out.println("Waag een gokje!"); //6
		
		int getalGebruiker = invoerVanGebruiker.nextInt();
		invoerVanGebruiker.close();
		
		double willekeurigGetal = Math.floor(Math.random()); //5
		
		System.out.printf("%s", getalGebruiker);
		
		if(willekeurigGetal == getalGebruiker) { //7
			System.out.printf("Goed gegokt!"); //6
		} else {
			System.out.printf("Je gokte %s en het juiste antwoord was %s", getalGebruiker, willekeurigGetal); //6
		}

	}

}
```

## Variabelen

Als we een programma gaan laten draaien (of runnen) wordt er een deel van ons geheugen gebruikt. We kunnen ook gebruik maken van het geheugen om gegevens tijdelijk te gaan opslaan. Aan deze gegevens kunnen we één of meerdere waarden gaan toekennen die gedurende het proces kunnen veranderen. Deze gegevens gaan we ook variabelen gaan noemen.

Om het proces wat te visualiseren zie je hieronder een tabel. Dit is een visuele weergaven van hoe ons computergeheugen werkt. Je ziet dat er op dit moment nog niks opgeslagen is in ons geheugen.

Opmerking: Java is een programmeertaal die niet specifiek moet weten waar een variabele zich bevindt. Dit wordt wel zo opgeslagen in het geheugen en heeft géén direct effect op het opslaan van variabelen, maar het is simpelweg iets dat niet echt van belang is voor de compiler/IDE. Dit in tegenstelling tot programmeertalen zoals bijvoorbeeld C++.

| Plaats  | Waarde |
| ------------- | ------------- |
| 101  |   |
| 102  |   |
| 103  |   |
| 104  |   |
| 105  |   |
| 106  |   |
| 107  |   |
| 108  |   |

We gaan nu eens een variabele 'leeftijd' gaan aanmaken. Dit is een numerieke waarde, dus dit gaan we gaan opslaan als een 'integer'. Je ziet hieronder dat er op een willekeurige plaats in ons geheugen nu de waarde '23' wordt opgeslagen.

```java
int leeftijd = 23;
```
| Plaats  | Waarde |
| ------------- | ------------- |
| 101  |   |
| 102  |   |
| 103  |  23 |
| 104  |   |
| 105  |   |
| 106  |   |
| 107  |   |
| 108  |   |

We gaan een tweede variabele gaan opslaan. Dit keer een stukje tekst met daarin onze naam. Tekst gaan we in 99% van de gevallen gaan opslaan als een String.

```java
int leeftijd = 23;
String naam = "Dylan";
```

Je ziet dat we nu twee plaatsjes hebben opgebruikt in ons geheugen. Eén daarvan is de leeftijd, die wordt opgeslagen als een integer, en de tweede variabele is de naam, die wordt opgeslagen als een String.

| Plaats  | Waarde |
| ------------- | ------------- |
| 101  |   |
| 102  |   |
| 103  | 23   |
| 104  |   |
| 105  |   |
| 106  | "Dylan" |
| 107  |   |
| 108  |   |

Stel dat we de leeftijd nu verkeerd hebben ingegeven. Dit zou 27 moeten zijn. We kunnen na het aanmaken van een variabele er nog altijd voor kiezen om een andere waarde toe te kennen. Dit doen we hieronder. Hier gebruiken wij de vorige waarde van 'leeftijd' en gaan we dit gaan optellen met 4. We kunnen verschillende dingen doen met variabelen. In principe zijn dit waarden die onder een bepaalde naam opgeslagen worden. Deze waarden kunnen zo gedurende de draaitijd/runtime van een programma gebruikt worden.

```java
//twee variabelen aanmaken
int leeftijd = 23;
String naam = "Dylan";

//waarde veranderen van leeftijd
leeftijd = leeftijd + 4;
```

Bij een optelling/aftrekking/vermenigvuldiging of deling kunnen wij eigenlijk nog korter te werk gaan:

```java
//declaratie
int leeftijd = 23;

//bewerkingen
leeftijd += 4; // vorige waarde wordt opgeteld met 4        --> 23 + 4 = 27
leeftijd -= 4; // vorige waarde wordt afgetrokken met 4     --> 23 - 4 = 19
leeftijd *= 4; // vorige waarde wordt vermenigvuldigd met 4 --> 23 * 4 = 92
leeftijd /= 4; // vorige waarde wordt gedeeld door 4        --> 23 / 4 = 5
leeftijd %= 4; // restwaarde berekenen van leeftijd met 4   --> 23 % 4 = 3
leeftijd ^= 4; // machtberekening met 4 als exponent        --> 23 ^ 4 = 279 841

//let op!
leeftijd += 1.1; // --> foutmelding want '1.1' is een double terwijl 'leeftijd' een integer is
```

We zien dat de waarde mee verandert. Er is géén nieuw plaatsje opgebruikt als we een bestaande variabele een andere waarde gaan toekennen.

| Plaats  | Waarde |
| ------------- | ------------- |
| 101  |   |
| 102  |   |
| 103  | 27   |
| 104  |   |
| 105  |   |
| 106  | "Dylan" |
| 107  |   |
| 108  |   |



Het omgekeerde van een variabele is een constante, een waarde die éénmaal aangemaakt niet meer zal veranderen. We willen een constante bijhouden van de minimumleeftijd, ofwel de waarde 18. Een constante aanmaken in Java doe je als volgt:

Opmerking: Je hoeft géén constante waarden in hoofdletters te schrijven. Het is géén verplichting voor Java, maar wel iets dat in de praktijk nog vaak voorkomt.

```java
final static int MINIMUMLEEFTIJD = 18;
```

'final' is zeer belangrijk bij de declaratie van een constante. Zonder 'final' zal je een gewone variabele aanmaken die nog steeds veranderd kan worden.. Simpel gezegd ken je de finale of laatst mogelijke waarde toe aan een variabele. Je kan het datatype vanzelfsprekend ook niet meer veranderen.

'static' wilt eerder zeggen dat dit een waarde is die we over grenzen heen kunnen gebruiken. Dit wilt zeggen dat we buiten de huidige klasse nog steeds kunnen werken met deze constante waarde.

Deze constante krijgt ook een plaats in ons geheugen.

| Plaats  | Waarde |
| ------------- | ------------- |
| 101  |   |
| 102  |   |
| 103  | 27   |
| 104  | 18  |
| 105  |   |
| 106  | "Dylan" |
| 107  |   |
| 108  |   |



## Methoden: basis

We gaan voornamelijk gebruik maken van variabelen/constanten en methoden. Hieronder nog even een schema om de twee wat te verduidelijken. Over methodes komt nog meer aan bod in een later hoofdstuk, maar ik wel toch nog even aanhalen hoe we een methode kunnen aanmaken en ook kunnen oproepen vanuit de main-klasse.

We maken een methode die simpelweg 'Hallo' gevolgd door een gegeven naam gaat teruggeven aan het systeem. 

De naam kan variëren dus deze moeten we mee geven als parameter. Parameters komen tussen de ronde haakjes. De naam maakt niet zo zeer uit, maar het datatype (in dit geval String) is wel zeer belangrijk. Je kan meerdere parameters opvragen in een methode. Dit kunnen Strings, integers, doubles, enz. zijn maar de volgorde speelt wel een belangrijke rol.

Dit stukje tekst moet teruggegeven worden aan het systeem. Dit betekent dat we iets moeten terugsturen en daarvoor gaan we vóór de naam van onze methode het datatype zetten dat wordt teruggestuurd. Hier is dit een String dat we gaan terugsturen. Mochten we een integer terugsturen, dan zou dit 'int begroeting(String naam)' zijn. 
De 'return' is hier ook zeer belangrijk. Alles dat na 'return' komt is ook hetgeen dat wordt teruggestuurd. Vaak gaat dit een variabele zijn, maar het is van belang dat wat je ook na return gaat plaatsen, dat dit overeenstemt met het gevraagde datatype. Geef je géén return mee, dan zal jouw IDE ook een foutmelding geven.

Je merkt waarschijnlijk ook op dat het woordje 'static' hier ook nog staat. Dit komt later aan bod, maar is voorlopig wel essentieel voor de opbouw van onze methode.

```java
public static String begroeting(String naam) {
	return String.format("Hallo %s!", naam);
}
```

Het aanroepen van de methode gaat dan als volgt. We schrijven de naam van onze methode, hier dus 'begroeting', gevolgd door twee ronde haakjes. De methode verwacht dat we een String mee geven, dus geven we hier eender welke naam in. Let wel op dat je hier gebruik maakt van dubbele aanhalingstekens. Anders gaat de compiler dit niet als een String zien en dit fout rekenen.

We weten dat deze methode een String teruggeeft. Het enige wat we moeten doen is deze nog uitprinten en hiervoor gebruiken we dus 'System.out.println()' met tussen de ronde haakjes onze begroeting-methode.

```java
public static void main(String[] args) {
	System.out.println(begroeting("Dylan"));
}
```

We kunnen ook een methode opbouwen die direct het lijntje gaat uitprinten zonder iets terug te geven aan het systeem. Als er niks wordt teruggegeven, dan gaan we niet het datatype gaan mee geven maar gaan we hiervan een 'void-methode' maken. Je ziet waarschijnlijk ook al dat er géén return-keyword te zien is in de methode.

```java
public static void begroeting(String naam) {
	System.out.printf("hallo %s!");
}
```

Nu hoeven we bij het aanspreken enkel en alleen de methode te schrijven inclusief de enkele parameter.

```java
public static void main(String[] args) {
	begroeting("Dylan");
}
```


## Nog een korte samenvatting van variabelen en methoden: 

![image](https://i.imgur.com/nra1wFs.jpg)

## Scanner / Input via console

Bij programmeren met een command-line interface ga je praktisch altijd een Scanner nodig hebben. Een Scanner is zogezegd een object binnen Java die de waarde gaat bijhouden van hetgeen wat de gebruiker ingeeft. Let op: dit is géén primitief datatype. We kunnen dus niet de waarde van een scanner direct gaan gebruiken voor bijvoorbeeld een integer of een String te gaan declareren. Hiervoor moeten wij een extra methode gebruiken. Ik licht de Scanner even toe in onderstaand voorbeeld, lijntje per lijntje :

```java
Scanner invoerVanGebruiker = new Scanner(System.in);
		
System.out.println("Geef een getal in: ");
		
int getalVanGebruiker = invoer.nextInt();
		
System.out.printf("Je hebt het getal %s ingegeven.");
		
```

1. Je ziet dat we eerst een Scanner-object aanmaken met een duidelijke naam. Als je een nieuw object van iets aanmaakt declareer je de variabele in de linkerhelft en gebruik je "new Scanner()" in de rechterhelft. We spreken over objecten in een later hoofdstuk, maar hier spreek je de constructor aan van Scanner die een object voor jou gaat aanmaken, later hier meer over (3. Objecten).
2. Nu gaan we een lijn uitprinten die voor de gebruiker een boodschap gaat tonen. Op deze boodschap wordt een reactie verwacht. Als je jouw programma draait zal je zien dat je opeens kan typen in de console. Je kan nu bijvoorbeeld een getal in typen en dan op enter klikken.
3. Het Scanner-object houdt nu een waarde bij. Dit is nog niet bruikbaar voor ons dus moeten we de waarde gaan ophalen vanuit dit Scanner-object. Dit doen we door in de linkerhelft ons variabele te declareren en in de rechterhelft de naam van het Scanner-object in te geven, gevolgd door ".next". Wil je heel specifiek zijn over welk datatype dat je wilt moet je bijvoorbeeld ".nextInt()" gebruiken voor een integer of ".nextLine()" voor een String.
4. Uiteindelijk kunnen we de waarde gaan uitprinten dat de gebruiker daarnet heeft ingegeven. Je kan de waarde ook direct gaan ophalen door volgende code te gebruiken: 

```java
System.out.printf("Je hebt het getal %s ingegeven.", invoer.nextInt());
```

Op deze manier bespaar je ook een variabele. Let wel op dat we hier géén foutcontrole hebben toegepast. Ons programma is met andere woorden niet robuust want als de gebruiker in dit geval een stuk tekst gaat ingeven (of met andere woorden alles behalve een getal), dan gaat onze CUI-applicatie crashen en een foutmelding gaan geven. Hiervoor kunnen we een controlestructuur gebruiken om zo de gebruiker in een lus te zetten zodat hij enkel en alleen de applicatie kan afsluiten wanneer de persoon een correcte waarde heeft ingegeven.

## Type Casting

Type casting is eigenlijk het gaan omzetten van het ene primaire datatype naar een ander. We kunnen dit op twee manieren: narrowing (manueel) of upcasting (automatisch). Vanzelfsprekend lukt het ook niet altijd om van het ene datatype naar het andere te gaan. Denk maar bijvoorbeeld aan een String naar een boolean te gaan. Of van een String naar een integer.

![image](https://static.javatpoint.com/core/images/type-casting-in-java.png)

Hieronder zie je een voorbeeld van upcasting. We gaan een integer, ofwel een reëel getal, gaan omzetten naar een double, ofwel een kommagetal. Dit kunnen we automatisch doen omdat integer hoger dan double staat op ons lijstje.

```java
int reëelGetal = 5;
System.out.println(reëelGetal);
		
double kommaGetal = reëelGetal;
System.out.println(kommaGetal);
```

De uitvoer ziet er dan als volgt uit:

```
5
5.0
```

Omgekeerd gaat dit niet lukken. We krijgen een foutmelding in onze IDE als we van double naar integer proberen te gaan. Dit omdat we naar een groter datatype willen omzetten. Hiervoor gaan we downcasting moeten gebruiken.

Downcasting wilt juist het omgekeerde zeggen. Hier gaan we een double naar een integer omzetten. Hiervoor moeten we in de rechterhelft iets extra schrijven, namelijk '(naam van datatype)'. Tussen de ronde haakjes moet dus het datatype komen wat je wilt converteren. Hieronder willen we dus van een double naar een integer getal gaan:

```java
double kommaGetal = 5.6;
System.out.printf("kommagetal: %s", kommaGetal);
		
int reëelGetal = (int) kommaGetal;
System.out.printf("reëel getal: %s", reëelGetal);
```

De uitvoer ziet er als volgt uit. Bij een double gaan we 

```
5.6
5
```

# 2. [Controlestructuren]

Bij Java hebben wij drie soorten structuren: sequentie- , selectie- en herhalingsstructuren.

De **sequentiestructuur** kan je eigenlijk niet zelf implementeren in jouw code. Dit wordt namelijk gedaan door jouw IDE. Kort gezegd gaat jouw programma in de juiste volgorde lijn per lijn het programma uitvoeren. Het programma stopt ook onmiddelijk eenmaal er een fout wordt getroffen in de code. Hier moet je wel rekening houden met het declareren van variabelen. Je kan bijvoorbeeld niet een variabele gaan aanpassen als deze nog niet bestaat.

In onderstaand voorbeeld willen we de som van twee optellers gaan berekenen. We krijgen een foutmelding te zien omdat we deze twee variabelen pas na onze berekening gaan een waarde geven.

```java
int som = opteller + opteller2;		
int opteller = 5;
int opteller2 = 10;
```

**Korte opfrisser in verband met operatoren en prioriteitsregels**

![image](https://i.imgur.com/L1PiTBx.png)


**Selectiestructuren** gaan ons helpen om bepaalde paden in ons programma te gaan filteren. Zo kan je bijvoorbeeld een bepaalde actie gaan toepassen als de gebruiker een waarde in heeft gegeven die overeenstemt met of groter/kleiner is dan een andere waarde. De meest essentiële structuur is de if/else structuur. 

![Gewone If](https://i.imgur.com/NtCX5T2.jpg)

Bij If/Else ga je één voorwaarde meegeven. Voldoet een variabele niet aan een bepaalde voorwaarde, dan gaat het programma over gaan naar het "Else" deel. Hieronder zie je dat we bijvoorbeeld twee variabelen hebben. De variabele snelheidWagen en snelheidBeperking. In onze If-lus kijken we of de snelheid van de wagen sneller was dan de beperking. Als dit zo is dan geven we aan de gebruiker mee dat hij/zij een boete krijgt en gaan we met andere woorden alle code gaan uitvoeren die tussen de accolades staat. Is dit niet zo, dan krijgt de gebruiker het lijntje "no problemo" te zien en opnieuw ook alle code uitvoeren die tussen de accolades staan. 
Let op: we kunnen maar één keer een else gebruiken. We kunnen ons wel nog verdiepen binnen de If-lus.

Extra opmerking: Je bent niet verplicht om een else toe te voegen. Als je geen else uitvoerd zal er vanzelfsprekend wel géén alternatief worden aangeboden. In de meeste gevallen zal het wel handig zijn om toch een Else op te bouwen. 

```java
int snelheidWagen = 45;
		
final int snelheidBeperking = 50;
		
if(snelheidWagen >= snelheidBeperking) {
	System.out.println("Je reed te snel. Hier is je boete.");
} else {
	System.out.println("No problemo.");
}
		
```

Stel dat we willen dat de snelheid van de wagen tussen 50 en 70 ligt, dan kunnen we onze eerste voorwaarde als volgt aanpassen:

```java
if(snelheidWagen >= 50 && snelheidWagen <= 70) {
	System.out.println("Je reed te snel. Hier is je boete.");
} else {
	System.out.println("No problemo.");
}		
```

Twee '&&' tekens betekent een EN-vergelijking. Deze twee voorwaarden (>= 50 EN <= 70) moeten voldoen om een boete te kunnen meegeven. Stel dat de snelheid 75 zou zijn, dan zitten we met het probleem dat ons programma "no problemo" gaat zeggen omdat het getal wél groter is dan 50, maar niet kleiner dan 70. Stel dat je deze EN-vergelijking wilt veranderen naar een OF-vergelijking, dan moet je gebruik maken van '||'. Ons programma is nu wel onlogisch dus we moeten een voorwaarde toevoegen die gaat kijken om een operatie uit te voeren als we met een waarde zitten die groter is dan 70. Hiervoor gebruiken we een Else-If.

We voegen een extra toe aan onze huidige code. Je ziet dat er tussen onze if en onze else een extra lijn is gekomen. Else-If kijkt, net zoals de voorafgaande If, of een waarde voldoet aan de gegeven voorwaarde. Is dit zo? Dan gaat hij, net zoals de If, de code tussen de accolades gaan uitvoeren. Is dit niet zo? Dan gaan we, net zoals de If, rechtstreeks naar de Else.

```java
if(snelheidWagen >= 50 && snelheidWagen <= 70) {
	System.out.println("Je reed te snel. Hier is je boete.");
} else if(snelheidWagen > 70) {
	System.out.println("Wow, zo snel rijden in een zone 50. Are you out of your mind?!");
} else {
	System.out.println("No problemo.");
}
		
```

Stel dat we een programma moeten ontwerpen waarin we een getal mee krijgen die een dag van de week voorstelt (bijvoorbeelde de 6de dag). Voor iedere dag moeten we de dag voluit schrijven in onze console. Je zou in principe meerdere If's kunnen maken, maar dit is niet efficiënt en komt over als een omslachtig.

Daarom kunnen we gebruik maken van de switch structuur. 

_Extra: Hier gebruik ik een Date object. Dit is een object waar een datum wordt bijgehouden en waarvan we waaronder de dag, maand, week, enz. onmiddellijk kunnen opvragen zonder enige omslachtige code._

We starten met een switch() met tussen de ronde haakjes onze parameter waar we zo meteen ons op gaan baseren. Tussen in onze accolades gaan we meerdere "cases" gebruiken. Hier gaan we kijken of de waarde van onze variabele overeenkomt met de waarde die bij de case staat. Als we bvb de tweede dag zijn, dan gaan we _case 1_ negeren, maar wel _case 2_ gaan uitvoeren. 

Maar wat met de rest? De rest wordt niet bekeken door ons programma als we gebruik maken van het **break;** lijntje. Dit gaat zeggen tegen ons programma om direct uit de Switch-lus te gaan. Er is zeker de mogelijkheid dat je meerdere cases kan aanspreken, denk maar bijvoorbeeld als je met groter dan/kleiner dan gaat werken. 

En wat als er géén case is die aangesproken wordt? Dan wordt er ook niets veranderd of getoond... tenzij je een **default: ** lijn gebruikt. Dit gaat zogezegd de standaard operatie zijn mocht er niks aan de voorwaarde voldoen.

```java

Date vandaag = new Date();
		
int dagVanWeek = vandaag.getDay();
		
switch(dagVanWeek) {
	case 1:
	    System.out.println("Maandag");
	    break;
	  case 2:
	    System.out.println("Dinsdag");
	    break;
	  case 3:
	    System.out.println("Woensdag");
	    break;
	  case 4:
	    System.out.println("Donderdag");
	    break;
	  case 5:
	    System.out.println("Vrijdag");
	    break;
	  case 6:
	    System.out.println("Zaterdag");
	    break;
	  case 7:
	    System.out.println("Zondag");
	    break;
	  default:
		  System.out.println("Maakt niet uit welke dag het is, we chillen vandaag!");
	}

```


Tot nu toe hebben we dus de sequentiestructuur gezien waarin de code lijn per lijn wordt doorlopen. We hebben drie verschillende selectiestructuren gezien (if zonder else, if/else en switch). Stel dat we nu willen dat we één bepaalde actie of operatie een aantal keer willen uitvoeren of uitvoeren tot we een bepaald punt raken in ons programma? Hiervoor gaan we gebruik maken van controlestructuren. Er zijn er drie:

De eerste die ik wil toelichten is **While**. Letterlijk vertaald is dit een operatie die code gaat uitvoeren zolang een voorwaarde voldaan is. Is de voorwaarde niet voldaan dan gaat de code niet uitgevoerd worden. We starten met het while keyword gevolgd door ronde haakjes met daarin de voorwaarde, daarna ga je dan twee accolades gebruiken met daartussen de code die je wilt uitvoeren in de lus.



De tweede is heel gelijkaardig aan de While en noemt **Do-While**. Het verschil hier in is dat je eerst sowieso de code gaat uitvoeren vooraleer je de voorwaarde gaat controleren. Het programma gaat met andere woorden iets doen zolang dat iets aan een voorwaarde voldoet. Die "iets" gaat heel vaak een variabele zijn. Dit in tegenstelling met de While die eerst kijkt of de voorwaarde voldaan is. De structuur is ook logischerwijs anders opgebouwd dan de While-lus. Eerst ga je het do-keyword gebruiken, gevolgd door de accolades met daartussen je code. Na het sluiten van de lus ga je de while-voorwaarde schrijven. 

Dit gebruik je eerder voor foutcontrole. Beide zijn zeker mogelijk, maar hier heb je een efficientievoordeel omdat je maar je Scanner-statement éénmalig opschrijven.



De laatste is de **for-lus**. Deze is wat complexer, maar laat wel enkele mogelijkheden toe. Bij de for-lus gaan we werken met drie parameters: de teller, voorwaarde en wat er veranderd nadat een lus is doorlopen. In dit voorbeeld zie je dat we een variabele 'teller' maken die we op 0 plaatsen. De teller moet kleiner zijn dan tien om de lus te doorlopen en nadat de lus is afgerond gaan we de teller verhogen met één. 

Het grote verschil tussen een for-lus en de while/do-while, is dat deze een einde heeft die we zelf bepalen. We weten met andere woorden wanneer de for-lus gaat stoppen. Als we onze for-lus zo gaan instellen dat dit na vijf herhalingen gaat stoppen, dan gaat dit ook daadwerkelijk na exact vijf keer ook stoppen. Een while/do-while wordt ook eerder gebruikt voor een aantal herhalingen dat we zelf niet kunnen bepalen, zoals bijvoorbeeld invoercontrole waar we wachten op de gebruiker die een correcte invoer moet geven. Dit zou dan één keer, maar ook vijf/tien/twintig keren kunnen zijn. 

Een heel simpel voorbeeld is een programmaatje dat tot tien gaat tellen voor het spel verstoppertje. Zoals het spel gaat, wordt er enkel nadat er tot tien werd geteld het zinnetje "Wie niet weg is, is gezien!" afgeroepen. Voor we naar de code kijken, kunnen we hier al uit afleiden dat ons programma precies tien keer zich moet herhalen. 

```java
for (int teller = 1; teller < 11; teller++) {
	System.out.println(teller);			
}

System.out.println("Wie niet weg is, is gezien!")
```

Onze output ziet er dan zo uit:

![Simpele For](https://i.imgur.com/1khtibu.png)


In onderstaand voorbeeld gaan we vijf sterretjes uitschrijven in onze console. Je ziet dat onze lus start op 0. Persoonlijk vind ik het handiger om te starten met een nulwaarde in plaats van één. Stel dat je toch wilt starten met één, dan ga je het bereik ook met één moeten verhogen (5 wordt dus 6). Tijdens onze lus gaan we een lijntje uitprinten met daarin één sterretje. Na iedere keer dat onze lus doorlopen wordt gaan we met één vermeerderen. 

```java
for (int teller = 0; teller < 5; teller++) {
	System.out.println('*');			
}
```

![Gewone For](https://i.imgur.com/ms6Nm8P.png)

Om de drie herhalingsstructuren nog eens samen te vatten, wil ik onderstaand voorbeeld toelichten. Je ziet hier dat het grote verschil tussen een while en een do-while is dat je bij een while eerst gaat kijken of de page interessant is. Je gaat met andere woorden eerst kijken of iets voldoet aan eisen. Zo ja? Dan ga je verder lezen totdat je het niet meer goed vindt. Dan stopt de lus.
Bij een do-while ga je eerst lezen en later pas kijken of je het interessant vindt. Vindt je het niet interessant dan stopt de lus.
Bij de for-lus ga je, net zoals een boek, beginnen bij het eerste hoofdstuk. Als je klaar bent met het eerste hoofdstuk, ga je over naar het volgende. Dit kan je zien als de teller die met andere woorden wordt opgeteld.

![image](https://i.imgur.com/Mdqd8vc.png)

## Geneste controlestructuren

We kunnen lussen ook gaan nesten. Dit betekent dat we een controlestructuur binnenin een lus gaan plaatsen. Dit kunnen we zogezegd oneindig doen, maar om niet te ver te gaan wil ik toch de geneste for-lus en een geneste if toelichten. Dit zijn de twee die je het vaakst zal tegenkomen.

In onderstaand voorbeeld willen ik opnieuw sterretjes uitprinten, maar in plaats van één per lijn wil ik ze zogezegd laten aftellen van vijf. Dus op het bovenste lijntje gaan er vijf sterretjes staan. Het lijntje eronder gaat er één minder hebben. Dit doen we tot aan het laatste lijntje waar er maar één sterretje is.

Je ziet dat we onze teller gaan laten beginnen op 5 en die gaan verminderen per keer dat we door de lus gaan. We doen dit totdat onze teller

```java
for (int aantalLijntjes = 5; aantalLijntjes > 0; aantalLijntjes--) {

	String output = "*";
	
	for (int aantalSterretjes = 0; aantalSterretjes < aantalLijntjes; aantalSterretjes++) {
		output += '*';
	}

	System.out.println(output);

}
```


![Geneste if-lus](https://i.imgur.com/djqvJJs.png)


# 3. [Objecten en klassen]

![image](https://user-images.githubusercontent.com/70543493/124633975-1e48bf00-de86-11eb-99db-d02cf7a86bb0.png)

Stel je voor, je bent ergens op vakantie (pic related) en je hebt een kamer gereserveerd.  Iedere kamer is ook anders ingericht, sommige kamers hebben internetbekabeling, sommige kamers zijn luxueuzer en hebben bijvoorbeeld een jacuzzi of ingebouwde sauna. Niet iedere kamer gaat ook even groot zijn want er zijn prijsverschillen voor iedere kamer. Belangrijk om te onthouden is dat je ook één sleutel hebt die bedoelt is om de deur van jouw hotelkamer te openen. Logischerwijs kan je deze sleutel niet gebruiken om bijvoorbeeld de deur van jouw buurman of -vrouw te openen. Hiervoor heb je een andere sleutel nodig. 

Kern: Iedere kamer heeft bepaalde **kenmerken** die het zo **uniek** maakt. Je kan ook bepaalde **acties** gaan uitvoeren binnen bepaalde kamers familievriendelijke activiteiten zoals chillen, relaxen, browsen en meer.

Hieronder zie je bijvoorbeeld vier verschillende hotelkamers gekozen via een willekeurige website. Iedere kamer is anders op zijn eigen manier.

![image](https://i.imgur.com/i4LM8Ec.jpg)

Een kamer gaan we altijd gaan herkennen aan de hand van **kenmerken**. In dit geval heeft iedere kamer:

* Een berekende oppervlakte
* Wordt er een keycard gebruikt?
* Is de kamer luxueus?
* Extra's?
* Een prijs per nacht.

Eén zo een kamer gaan we een **Object** noemen. Dit is een manier binnen het programmeren waarin we structuur kunnen behouden waar we kenmerken en methoden (ofwel een actie uitvoeren) kunnen gebruiken. We kunnen deze objecten aanspreken en bijvoorbeeld kenmerken gaan opvragen, maar ook om bepaalde acties te gaan uitvoeren. Denk maar bijvoorbeeld aan het relaxen in een kamer of de deur van de kamer openen. 

We kunnen niet zomaar een object aanmaken. Er zijn programmeertalen (bijvoorbeeld JavaScript) waarin je een object kan aanmaken via één actie. Java werkt anders en voor een object aan te maken moet je werken met een soort blueprint of sjabloon dat we een **Klasse** gaan noemen. Deze klassen gaan we nog specifieker domeinklassen gaan noemen, dat vooral met oog op het ontwerpen van applicaties. Dat komt later aan bod.

Domeinklasses maken we enkel en alleen aan in het domein. Op deze manier kunnen we een goed overzicht houden van al onze domeinklassen die we gaan gebruiken voor het maken van objecten. Als we een domeinklasse maken in onze cui-package, dan één in onze persistentielaag en uiteindelijk een aantal in onze domeinlaag, dan gaan we uiteindelijk onze rode draad verliezen en niet meer mee zijn met onze zelf opgebouwde structuur.

Hieronder zie je hoe we een klasse maken. Eerst gaan we alle nodige kenmerken gaan declareren in een variabele. Hou hiermee rekening met het juiste datatype. 
'String[]' verwijst naar een lijst van strings. Dit komt aan bod in het hoofdstuk rond arrays en moet je je nu nog geen zorgen om maken.

Géén paniek als dit overweldigend overkomt. We overlopen ieder deeltje apart.

```java
package domein;

import java.util.Arrays;

public class HotelKamer {
	
	int nummer;
	int oppervlakte;
	boolean keyCardNodig;
	boolean isLuxueus;
	String[] extras;
	double prijs;
	
	
	//1. Constructor met géén default waarden.
	public HotelKamer(int nummer, int oppervlakte, boolean keyCardNodig, boolean isLuxueus, String[] extras, double prijs) {
		this.nummer = nummer;
		this.oppervlakte = oppervlakte;
		this.keyCardNodig = keyCardNodig;
		this.isLuxueus = isLuxueus;
		this.extras = extras;
		this.prijs = prijs;
	}
	
	
	//2. Constructor met default waarden.
	public HotelKamer(int nummer, int oppervlakte, double prijs) {
		this.nummer = nummer;
		this.oppervlakte = oppervlakte;
		this.keyCardNodig = false;
		this.isLuxueus = false;
		this.extras = new String[]{"geen"};
		this.prijs = prijs;
	}
	
	public HotelKamer() {
		this.nummer = 0;
		this.oppervlakte = 0;
		this.keyCardNodig = false;
		this.isLuxueus = false;
		this.extras = new String[] {"geen"};
		this.prijs = 0;
	}


	//3. Getters voor alle kenmerken.
	public int getNummer() {
		return nummer;
	}


	public int getOppervlakte() {
		return oppervlakte;
	}


	public boolean isKeyCardNodig() {
		return keyCardNodig;
	}


	public boolean isLuxueus() {
		return isLuxueus;
	}


	public String[] getExtras() {
		return extras;
	}


	public double getPrijs() {
		return prijs;
	}
	
	
	// 4. Setters voor alle kenmerken.
	private void setNummer(int nummer) {
		this.nummer = nummer;
	}


	private void setOppervlakte(int oppervlakte) {
		this.oppervlakte = oppervlakte;
	}


	private void setKeyCardNodig(boolean keyCardNodig) {
		this.keyCardNodig = keyCardNodig;
	}


	private void setLuxueus(boolean isLuxueus) {
		this.isLuxueus = isLuxueus;
	}


	private void setExtras(String[] extras) {
		this.extras = extras;
	}


	private void setPrijs(double prijs) {
		if(prijs > 0){
			this.prijs = prijs;
		}
	}

	
	//5. Methoden
	public void relax() {
		System.out.println("good vibes.....");
	}
	
	public void browsen() {
		System.out.println("Instagram: pastalovers, motivationalquotes en .");
		System.out.println("duolingo: lol!");
		System.out.println("Bpost App: Jouw pakketje heeft vertraging opgelopen. Onze excuses hiervoor maar we proberen..");
	}

	@Override
	public String toString() {
		return "Kamer " + nummer + " is " + oppervlakte + "m² groot.\n"
				+ "Keycard nodig? " + keyCardNodig + "\n"
				+ "Luxueuze suite? " + isLuxueus + "\n" 
				+ "Extras: " + Arrays.toString(extras) + "\n" 
				+ "Kostprijs: €" + prijs + "";
	}
}
```

We gaan eerst kijken om al onze kenmerken te verzamelen en deze te gaan declareren. We kennen géén waarde toe tenzij het een variabele is die voor alle objecten hetzelfde gaat zijn.

```java
int nummer;
int oppervlakte;
boolean keyCardNodig;
boolean isLuxueus;
String[] extras;
double prijs;
```

Om een object te maken van een klasse gaan we gebruik maken van een **constructor**. Deze is de kern van een klasse want zonder een constructor zouden wij geen objecten kunnen aanmaken van deze klasse. Bij een constructor ga je parameters meegeven. Zogezegd ga je een kamer bouwen aan de hand van de kenmerken zoals oppervlakte, prijs, enz.

Het voordeel bij Java is dat je meerdere constructors kan aanmaken om zo heel specifiek te kiezen welke kenmerken we met een standaardwaarde gaan instellen en welke we gaan instellen met de meegegeven waarde. Hieronder zie je drie verschillende constructors: de eerste gebruikt géén standaardwaarden, de tweede gebruikt deels standaardwaarden en de derde en laatste gebruikt enkel en alleen standaardwaarden.

De eerste manier is door een object aan te maken waarin elk kenmerk gelijk staat aan een meegegeven parameter. Met andere woorden zijn alle kenmerken 'ter plaatse' bepaald en er wordt niks van standaardwaarde gebruikt. Je ziet dat we tussen de ronde haakjes ook al onze kenmerken (niet enkel de naam, datatype moet ook inbegrepen zijn!) gaan meegeven.
Tussen de accolades gaan we dan de parameters gaan toekennen aan de kenmerken. We kunnen niet zomaar 'nummer = nummer' gaan zeggen. We hebben twee variabelen: één behoort tot de klasse, één behoort tot de constructor en is de meegegeven parameter. 

Als we iets willen veranderen aan een kenmerk van een object, dan gebruiken we 'this.' gevolgd door het kenmerk. Willen we de prijs gaan aanpassen, dan gaan we 'this.prijs = prijs' gaan doen waarbij 'this.prijs' het kenmerk prijs is en 'prijs' de meegegeven parameter is.

![image](https://user-images.githubusercontent.com/70543493/124655838-afc52a80-dea0-11eb-80e5-101b867b5a19.png)


```java
//1. Constructor met géén default waarden.
	public HotelKamer(int nummer, int oppervlakte, boolean keyCardNodig, boolean isLuxueus, String[] extras, double prijs) {
		this.nummer = nummer;
		this.oppervlakte = oppervlakte;
		this.keyCardNodig = keyCardNodig;
		this.isLuxueus = isLuxueus;
		this.extras = extras;
		this.prijs = prijs;
	}
```


We kunnen ook vooraf bepaalde waarden gaan instellen. Denk maar bijvoorbeeld aan iets dat we zelf nog niet vooraf kunnen weten. Bij een nieuwe kamer kunnen we vragen stellen zoals 'heeft er hier iemand al gewoond?' dat we op false kunnen zetten of 'aantal mensen die hier hebben verbleven' die we beter op 0 zetten. We hoeven dit niet met de constructor mee te geven, maar in de plaats daarvan kunnen we dit al vooraf in te stellen zodat dit niet als een parameter moet worden meegegeven.

Hieronder zie je dat we enkel vragen naar het nummer, de oppervlakte en de prijs. De niet-vernoemde parameters gaan we een standaardwaarde gaan geven. Voor de linkerhelft blijven we het sleutelwoord 'this.' opschrijven, maar op de rechterhelft kunnen we al direct de waarde gaan opschrijven. Bij het kenmerk 'isLuxueus' gaan we dit standaard op false zetten of bij extra's gaan we maar één element in onze array hebben dat 'geen' is.

```java
	
	
	//2. Constructor met default waarden.
	public HotelKamer(int nummer, int oppervlakte, double prijs) {
		this.nummer = nummer;
		this.oppervlakte = oppervlakte;
		this.keyCardNodig = false;
		this.isLuxueus = false;
		this.extras = new String[5];
		this.prijs = prijs;
	}
	
```

De laatste soort is een constructor waarbij we géén enkele parameter gaan mee geven. Alles is dus een standaardwaarde. In de ronde haakjes moeten we ook géén parameters gaan mee geven.
	
```java
	public HotelKamer() {
		this.nummer = 0;
		this.oppervlakte = 0;
		this.keyCardNodig = false;
		this.isLuxueus = false;
		this.extras = new String[] {"geen"};
		this.prijs = 0;
	}
```
Let wel op! De naam van je constructor moet exact dezelfde zijn zoals jouw klassenaam. 

Wat is nu het verschil tussen een methode en een constructor? Er zijn wel degelijk verschillen tussen deze twee. In onderstaand schema wil ik de belangrijkste nog eens toelichten:

![image](https://i.imgur.com/wntaZtr.jpg)


We keren eventjes terug naar ons voorbeeld van hotelkamers. We willen graag het nummer van een kamer weten en ook de bijhorende extras. We willen met andere woorden iets opvragen van een object en dat kunnen we doen met een **getter**. Een getter is niet verplicht, maar wel nodig als je iets wilt opvragen. Voor ieder kenmerk dat je wilt opvragen ga je dus een getter moeten aanmaken.

```java

	//3. Getters voor alle kenmerken.
	public int getNummer() {
		return nummer;
	}


	public int getOppervlakte() {
		return oppervlakte;
	}


	public boolean isKeyCardNodig() {
		return keyCardNodig;
	}


	public boolean isLuxueus() {
		return isLuxueus;
	}


	public String[] getExtras() {
		return extras;
	}


	public double getPrijs() {
		return prijs;
	}
```

Stel dat je de prijs van een kamer wilt aanpassen, dan ga je geen getter kunnen gebruiken. Een getter gaat enkel iets van een bepaald datatype gaan teruggeven. Voor iets te veranderen ofwel de waarde van iets te gaan setten gaan we **setters** gaan gebruiken. We weten ondertussen dat als we iets willen veranderen zonder iets terug te geven dat we gebruik moeten maken van een void methode. 

Hier moet je wel rekening houden dat het datatype van jouw parameter (tussen de ronde haakjes) overeen komt met het datatype dat gebruikt wordt in de klasse. Er zijn wel manieren om datatypes te gaan omzetten, maar dat gaat buiten de inhoud van OOSD1.

 

```java	
// 4. Setters voor alle kenmerken.
private void setNummer(int nummer) {
	this.nummer = nummer;
}


private void setOppervlakte(int oppervlakte) {
	this.oppervlakte = oppervlakte;
}


private void setKeyCardNodig(boolean keyCardNodig) {
	this.keyCardNodig = keyCardNodig;
}


private void setLuxueus(boolean isLuxueus) {
	this.isLuxueus = isLuxueus;
}


private void setExtras(String[] extras) {
	this.extras = extras;
}
```

Bij onze setters kunnen we ook invoercontrole gaan toepassen. We gebruiken hiervoor een If/else. Bij prijs zie je bijvoorbeeld dat het een positief getal moet zijn. Als dit zo is, dan gaan we de nieuwe prijs gaan doorvoeren. Als dit niet zo is, dan gaan we een foutmelding 'gooien' die ons programma later zal 'opvangen'. Zo een zelf ingestelde foutmelding noemen wij een **exception** en dit komt verder aan bod in het deel van OOSD2. 

```java
private void setPrijs(double prijs) {
	if(prijs > 0){
		this.prijs = prijs;
	} else {
		throw new IllegalArgumentException("Prijs moet positief zijn!");
}
```


We hebben methodes gezien buiten klasses. Je kan ook methodes gaan aanspreken die invloed hebben of gebruik maken van een specifieke object. Simpel gezegd kan je via een methode iets gaan teruggeven, iets gaan wijzigen, enz. Hieronder heb ik twee methodes uitgewerkt. 

Om een klassemethode aan te spreken heb je een object nodig. Je kan deze methode met andere woorden dus niet gaan uitvoeren als je géén object hebt.



```java
//5. Methoden
public void relax() {
	System.out.printf("good vibes in room %s.....", this.nummer);
}

@Override
public String toString() {
	return "Kamer " + nummer + " is " + oppervlakte + "m² groot.\n"
			+ "Keycard nodig? " + keyCardNodig + "\n"
			+ "Luxueuze suite? " + isLuxueus + "\n" 
			+ "Extras: " + Arrays.toString(extras) + "\n" 
			+ "Kostprijs: €" + prijs + "";
	}
```

Bij relax() ga je een lijn uitprinten in de console die de tekst 'good vibes in room _n_.....' waarbij _n_ het nummer is van dat specifiek object. Bijvoorbeeld bij kamer 343 zal het lijntje 'good vibes in room 343' uitgeprint worden. Bij kamer 404 zal dit dan 'good vibes in room 404' zijn. Omdat er niks wordt teruggegeven gaan we deze methode ook void maken.

toString is een heel belangrijke methode die je ook zelf kan genereren binnen in Eclipse. '@Override' komt later aan bod, maar simpel gezegd gaan we eigenlijk de methode anders gaan maken dan dat die aan ons wordt gegeven. Als we deze methode niet in onze klasse steken, krijgen we een heel andere uitvoer. Dit heeft wel géén effect op de kenmerken van ons object, die blijven namelijk het zelfde. Enkel de uitvoer zal anders zijn.

Bij toString gaan we een String teruggeven, let ook op want nu is het niet meer void maar wel String, met daarin tekst waarin we al de kenmerken van ons object aan bod laten komen. Een voorbeelduitvoer van kamer 666 zal dan bijvoorbeeld zijn: 

```Kamer 666 is 31m² groot.
Keycard nodig? true
Luxeus? false
Extras: ['Aanwezigheid van demons']
Kostprijs: €66
```


Nu hebben we zogezegd ons sjabloon om objecten te gaan aanmaken. Buiten deze klasse gaan we enkele kamers gaan aanmaken. Een object aanmaken is nog vrij logisch.

1. We starten ons lijntje met de klassenaam mee te geven. We willen een object aanmaken van de klasse HotelKamer dus we gebruiken ook deze naam.
2. Vervolgens gaan we ons object een naam gaan geven. We gaan eerst van kamer 343 een object maken, dus we noemen dit 'room343'. De naam speelt, net zoals bij een variabele, van weinig belang, maar het is wel essentieel dat je een logische naam gaat toekennen om verwarring te voorkomen.
3. Het is een nieuw object van een bepaalde klasse, dus we gaan het keyword 'new' gevolgd door de klassenaam gaan schrijven.
4. De parameters die je meegeeft zijn afhankelijk van de constructor die je gebruikt. Heb je een constructor die géén parameters vraagt, dan kan je de ronde haakjes leeg laten. Het hangt er vooral van af welke gegevens het object zeker moeten bevatten dus kijk vooral naar de constructor die daar rekening mee houdt;

![image](https://i.imgur.com/PCj1P8y.jpg)

```java
	//object aanmaken met constructor die géén standaardwaarden gebruikt
	HotelKamer room343 = new HotelKamer(343, 28, true, true, new String[]{"xbox"}, 56);

	//object aanmaken met constructor die standaardwaarden gebruikt
	HotelKamer room404 = new HotelKamer(404, 24, 44);
		
	//object aanmaken met lege constructor
	HotelKamer roomUnknown = new HotelKamer();
		
	//geeft alle kenmerken terug van kamer 343
	System.out.println(room343.toString());
				
	//print uit: 'good vibes in room 404.....'
	room404.relax();
		
	//print de oppervlakte uit van de kamer met 0 als oppervlakte
	System.out.println(roomUnknown.getOppervlakte());
}
```

# 4. [Arrays]

Stel: Ieder jaar krijg je een rapport met daarin alle scores per opleidingsonderdeel. Alle scores worden samen bij elkaar gehouden om zo enige structuur te kunnen maken. Het zou vrij verwarrend en omslachtig worden mochten we voor iedere score apart gaan bijhouden. Ieder onderdeel wordt ook in een voorbepaalde **volgorde** geplaatst. Dit kan bijvoorbeeld alfabetisch zijn.

Bij het programmeren kunnen we gebruik maken van een soort datastructuur dat we **arrays** gaan noemen. Een array is een container waarin je verschillende elementen kan samen gaan houden. Deze elementen hebben een specifieke volgorde die ook wel de **index van een element** wordt genoemd. Een belangrijk puntje is dat de index altijd vanaf **nul** begint. Het eerste element in een array zal dus altijd nul als index hebben.

Op iedere index van een array hangt er een waarde vast. Arrays binnen Java zijn homogeen wat betekent dat je enkel en alleen maar één datatype mag gebruiken in een array. Je kan dus niet een array bouwen die bestaat uit integers gevolgd door een String en dan weer een integer enz. Alle elementen in de array **moet** van hetzelfde datatype zijn.

Binnen Java hebben alle arrays een bepaald aantal elementen die in de array passen. Als je een array aanmaakt waar je maximaal vijf elementen in kan plaatsen, dan kan je logischerwijs ook geen zeven elementen erin plaatsen. Dit is met andere woorden buiten het bereik van de array.

We kunnen een array als volgt declareren. 
In de linkerhelft moet je het datatype meegeven gevolgt door vierkante haakjes, hier is dit een array van integers. Daarna geef je dan de naam van de array mee, in dit geval 'hotelkamerNummers'.
In de rechterhelft gaan we het keyword 'new' gebruiken gevolgd door opnieuw het datatype waaruit onze array gaat bestaan. Tussen de vierkante haakjes merk je waarschijnlijk al een getal op. '6' betekent hier de grootte van onze array. Er kunnen dus hoogstens zes elementen in de array geplaatst worden.

```java
//lege array maken
int[] hotelkamerNummers = new int[6];
```

Elementen kan je toevoegen aan de array door de naam van de array te typen gevolgd door rechte haakjes met daarin de index. Deze index is belangrijk want hier gaat de waarde van het element, dat je wilt toevoegen, opgevuld worden. Onder de code vind je een schema van hoe de array er zogezegd dan uit ziet.

We zijn niet verplicht om alle plaatsen in de array te gaan gebruiken. Het is zeker mogelijk om lege plaatsen over te laten. Het omgekeerde daarentegen is wat moeilijker en hier moet je zeker rekening mee houden. Stel dat we zeven waarden in de accolades zouden schrijven, dan zullen we hoogstwaarschijnlijk een foutmelding krijgen omdat we zogezegd 'out-of-bounds' gaan ofwel buiten het bereik van onze array. 

```java
//elementen toevoegen aan de array
hotelkamerNummers[0] = 343;
hotelkamerNummers[1] = 101;
hotelkamerNummers[3] = 404;
```

![image](https://user-images.githubusercontent.com/70543493/125082007-f4caa600-e0c6-11eb-87d7-065e3dfa9baf.png)


Er is ook een directe manier om een array op te vullen. Alleen geef je hier juist niet de limiet handmatig mee, maar wordt die berekend aan de hand van hoeveel gegevens je doorgeeft. De linkerhelft blijft praktisch gelijk, maar in de rechterhelft gaan we enkel accolades gaan gebruiken met daarin alle waarden die we gaan mee geven. 



```java
int[] hotelkamerNummers = {343, 101, 404, 666, 314};
```

![image](https://user-images.githubusercontent.com/70543493/125082210-3b200500-e0c7-11eb-845f-8d1ceaeadb93.png)


![image](https://i.imgur.com/amZj7Ej.jpg)


Nu houden we enkel de nummers bij van hotelkamers, maar zou het niet mogelijk zijn om het gehele object van de klasse Hotelkamer? Het antwoord op die vraag is ja!

Als voorbeeld gaan we drie hotelkamers toevoegen aan een array. We zorgen er voor dat er hoogstens vier objecten in deze array kunnen geplaats worden. Eerst zorgen we ervoor dat deze objecten aangemaakt worden. Eenmaal aangemaakt kunnen we ze in de array gaan plaatsen. Hiervoor zijn beide manieren mogelijk.

```java
//Eerst maken we drie HotelKamer-objecten aan.
HotelKamer room343 = new HotelKamer(343, 28, true, true, new String[]{"xbox"}, 56);
HotelKamer room404 = new HotelKamer(404, 24, 44);
HotelKamer roomUnknown = new HotelKamer();

//We gebruiken niet meer int[] of String[], maar wel de naam van de klasse gevolgd door vierkante haakjes '[]'.

//Manueel opvullen
HotelKamer[] hotelkamers = new HotelKamer[4];
hotelkamers[0] = room343;
hotelkamers[1] = room404;
hotelkamers[3] = roomUnknown;
```
![image](https://user-images.githubusercontent.com/70543493/125085532-f7c79580-e0ca-11eb-821c-3e8e689ddc51.png)

Hieronder gaan we direct na het declareren de array opvullen. We laten géén lege plaats tussen. Met andere woorden krijgen we hier een array van maximaal drie elementen. 

```java
//Direct opvullen
HotelKamer[] hotelkamers2 = {room343, room404, roomUnknown};
```
![image](https://user-images.githubusercontent.com/70543493/125085777-3f4e2180-e0cb-11eb-9103-5081143fdcf3.png)


Het nadeel aan het gebruik van arrays is dat we met een limiet zitten. Echter kunnen we binnen Java gebruik maken van **ArrayLists**. Dit zijn op papier ook gewoon arrays, maar hebben een dynamische grootte en laten het ook makkelijker toe om objecten toe te voegen en te verwijderen. Als we niet weten hoe groot onze array kan worden, dan is het beter om te werken met een ArrayList. Weten we wél hoe groot onze array maximaal wordt, dan gebruiken we gewone arrays met een vooraf bepaalde limiet.

![image](https://i.imgur.com/BqwZuGB.jpg)



Arrays zijn datastructuren die je in bijna iedere programmeertaal gaat terugvinden. Een ArrayList is een speciale klasse in Java die ook zijn eigen methoden heeft. Deze methoden laten je bijvoorbeeld toe om elementen te kunnen verwijderen, toevoegen en te veranderen. Dat is iets dat je niet, of ten minste in beperkte mate, kan doen bij gewone arrays.

De belangrijkste methoden zijn de volgende:

'.add(waarde)' gaat een element achteraan de array gaan toevoegen. De enige parameter die je moet meegeven is de waarde van het element dat je wilt toevoegen aan de array. Hou hierbij rekening dat je enkel en alleen elementen kan toevoegen die van hetzelfde datatype zijn. Je kan met andere woorden géén String toevoegen aan een ArrayList van integers of een integer toevoegen aan een ArrayList van doubles.

![image](https://i.imgur.com/MnqLiAV.png)

```java
lijstHotels.add("Overlook Hotel"); //Voeg achteraan de array "Overlook Hotel" toe
```

'.set(index, nieuweWaarde)' gaat een element op een specifieke plaats in de array gaan aanpassen. Het is van belang dus dat je meegeeft waar je iets gaat aanpassen en ook wat de nieuwe waarde wordt. In onderstaande afbeelding zie je een voorbeeld van zo een ArrayList. We geven de index mee (4) wat betekent dat we het element op index 4 gaan aanpassen met de nieuwe waarde, in dit geval wordt dit "Ice Hotel".

![image](https://i.imgur.com/fQZvSJo.png)

```java
lijstHotels.set(4, "Ice Hotel"); //Verander de waarde van het element, dat index '4' heeft, naar "Ice Hotel"
```

'.remove(index)' is een methode die het element op de meegegeven index gaat verwijderen. Let op! De waarde wordt niet enkel leeggemaakt, de opeenvolgende cellen gaan worden doorgeschoven en de index van iedere cel gaat dus ook veranderen.

```java
lijstHotels.remove(2); //Verwijder het element dat index '2' heeft
```

![image](https://i.imgur.com/FRKVkKh.png)


'.clear()' is een methode die geen parameters vereist en die simpelweg de gehele ArrayList gaat leegmaken. De ArrayList wordt niet verwijderd, maar wel elke cel die zich in de ArrayList bevindt. Als je een nieuwe element gaat toevoegen zal deze dus index 0 krijgen, of met andere woorden de eerste element in de ArrayList. 

```java
lijstHotels.clear();
```
![image](https://i.imgur.com/87TxiCS.png)

'.size()' is ook een methode die geen parameters vereist en die gelijkaardig is aan de '.length()' methode die we hebben gezien bij arrays. Als je '.size()' gaat gebruiken krijg je het aantal elementen in een ArrayList te zien, of kortgezegd de 'grootte' van de ArrayList.

```java
lijstHotels.size(); //5
```

Als laatste kunnen we ook onze ArrayList gaan doorlopen om zo alle waarden uit te gaan printen of om ze te gaan gebruiken. Eigenlijk gelden de zelfde principes op twee veranderingen na.

Allereerst gaan we niet '.length()' gaan gebruiken om de limiet te weten, maar we gebruiken hiervoor de vooraf genoemde '.size()'.
Als tweede kunnen we ook niet 'arrayList[index]' gaan gebruiken. Hiervoor moeten we werken met de '.get' methode.

```java
for (int teller = 0; teller < lijstHotels.size(); teller++){
	System.out.println(lijstHotels.get(teller); // print de naam van het hotel uit op een lijntje
}
```

Ook komt de enhanced-for lus hier opnieuw van pas. Beide zijn even goede en functionerende mogelijkheden. In onderstaand voorbeeld doorlopen we een array van Strings. 

```java
for(String hotel : lijstHotels){
	System.out.println(hotel); // gebruikt géén '.get()' omdat dit al de waarde is uit de array
}
```

We hebben gezien hoe we primaire datatypes zoals Strings, integers, booleans, enz. bij elkaar kunnen houden, maar we kunnen, net zoals bij gewone arrays, ook ArrayLists gaan gebruiken om objecten te gaan verzamelen. Hiervoor moeten we enkel en alleen de naam van het object in de eerste diamond-operator.

```java
//Eerst maken we een HotelKamer-object aan.
HotelKamer room343 = new HotelKamer(343, 28, true, true, new String[]{"xbox"}, 56)

//Hier maken we de ArrayList aan.
List<HotelKamer> hotel = new ArrayList<>();
``` 

Nu kunnen we de hotelkamers gaan toevoegen. Hieronder toon ik twee verschillende manieren. We kunnen kiezen om een al gemaakte object te gaan toevoegen door de naam van het object mee te geven:



```java
//kamer toevoegen
hotel.add(room343);
```

We kunnen daarentegen ook het object aanmaken en direct toevoegen aan de ArrayList. We nemen in principe de rechterhelft van het aanmaken van een object en plaatsen die in onze '.add()'. Dit werkt bij eender welke constructor die je gaat gebruiken.

```java
//kamer aanmaken + direct toevoegen
hotel.add(new HotelKamer(404, 24, 44);

//kamer toevoegen met enkel defaultwaarden
hotel.add(new HotelKamer());
```

Tot nu toe hebben we enkel arrays gezien waarbij je enkel met een rij werkt. De data staat zogezegd 'naast elkaar' en gaat een bepaalde positie in die rij gaan bijhouden.
Bij objecten hebben we ook gezien hoe we op een bepaalde manier verschillende data op één zo een blokje kunnen krijgen. Binnen arrays kunnen we ook met een soortgelijke grid-structuur werken. Hier gaan we niet enkel één rij hebben, maar kunnen we zelf kiezen om een array op te bouwen uit een gekozen aantal rijen en kolommen. Dit noemen we een tweedimensionale array.

# Tweedimensionale Arrays

We gebruiken tweedimensionale arrays voornamelijk als we in twee richtingen bepaalde data willen gaan bijhouden. Ik leg dit eventjes uit aan de hand van het gekende computerspel: Minesweeper. Minesweeper is een spelletje waarbij je een raster te zien krijgt. Je moet strategisch blokjes gaan selecteren om zo te kunnen achterhalen waar wél en waar géén bom zit. Raak je de bom, dan ben je dood!

We maken een tweedimensionale array lichtjes anders dan bij een gewone array. In plaats van één paar vierkante haakjes (rijen) gaan we twee paar vierkante haakjes gebruiken bij het declareren (rij + kolom). 

![image](https://user-images.githubusercontent.com/70543493/125513926-9febb554-569f-4dca-b8d2-4a1ab9e59921.png)

Onze twee dimensionale array ziet er als volgt uit. Eigenlijk is het zo dat je een array hebt met in iedere 'cel' een array van elementen. Voorlopig is ons spelbord nog leeg en is er géén waarde toegekend. Dit is dus bij alles '0'.

```
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
```

Bij een eendimensionale array konden we kijken welke element er was op een bepaalde positie in een array. We kunnen dit eveneens ook hier doen:

```java
System.out.println(spelbord[3]);
```

We zien nu dat we eigenlijk een array krijgen met alle elementen die zich op de derde rij bevinden.
```
Output:
[0,0,0,0,0,0,0,0]
```

Stel dat we de waarde willen weten van het vijfde blokje van links op diezelfde rij, dan kunnen we dat als volgt gaan opvragen:

```java
System.out.println(spelbord[6][3]);
```

We krijgen dus de waarde van het element dat zich op die specifieke plaats in de array bevindt. In dit geval is dat dus nul.

```
Output:
0
```

Nu is ons spelbord nog bommenvrij, we kunnen daar verandering in brengen door een bommetje (ofwel een element met waarde 1) te gaan plaatsen in de array. Dit gaat gelijkaardig als met een eendimensionale array. We gaan een bommetje plaatsen op de derde kolom van zesde rij.

```java
spelbord[6][3] = 1;
```

Ons bord ziet er dan als volgt uit:

```
     '
     '  
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,1,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
[0,0,1,0,0,0,0,0] <-----
[0,0,0,0,0,0,0,0]
[0,0,0,0,0,0,0,0]
```

Een tweedimensionale array doorlopen is een stukje ingewikkelder, maar volgt een heel gelijkaardig principe. Hieronder zie je nog eens hoe we een gewone eendimensionale array kunnen doorlopen:

```java
int[] rijVanArray = new int[5];

// voor zolang er elementen in de array zijn, blijven doorlopen
// teller met één optellen --> naar het volgende blokje in de array gaan
for (int teller = 0; teller < rijVanArray.length; teller++)
{
	System.out.println(rijVanArray[teller]; // de waarde uitprinten van het element dat zich op die positie in de array bevindt
}
```

Dit is hoe we te werk gaan bij een tweedimensionale array. We gaan werken met een geneste for-lus. We gebruiken een for-lus om alle rijen te doorlopen. Bij iedere rij gaan we dan met een for-lus alle kolommen binnen die specifieke rij gaan doorlopen.

De for-lus werkt dan als volgt:

rij 0 => for-lus waar je de kolommen van 0 -> 7 gaat doorlopen; stoppen met for-lus van de kolommen dus op naar de volgende rij --> teller van de rij verhogen
rij 1 => for-lus waar je de kolommen van 0 -> 7 gaat doorlopen; stoppen met for-lus van de kolommen dus op naar de volgende rij --> teller van de rij verhogen
rij 2 => for-lus waar je de kolommen van 0 -> 7 gaat doorlopen; stoppen met for-lus van de kolommen dus op naar de volgende rij --> teller van de rij verhogen
...
rij 7 => kolommen 0 -> 7; we verhogen de teller niet meer omdat we op de laatste rij zijn aangekomen, we doorlopen alle kolommen van de laatste rij en sluiten de for-lus af 

![image](https://user-images.githubusercontent.com/70543493/125654153-ea3ef37f-9302-4c44-a711-507b4da0b97a.png)

```java
int[][] spelbord = new int[8][8];
	
// bommetjes plaatsen op spelbord, we geven de coördinaten mee [kolom][rij]
mineSweeper[4][2] = 1;
mineSweeper[3][4] = 1;


// we doorlopen alle rijen
for(int rij = 0; rij < spelbord.length; rij++) {
	
	// we doorlopen alle kolommen van de rij waar we op dit moment zitten
	for(int kolom = 0; kolom < spelbord[rij].length; kolom++) {		
		
		// is er een bommetje op deze plek/coördinaten? 
		// zo ja --> vierkante haakjes met sterretje
		// anders --> vierkante haakjes met lege ruimte er tussen
		if(spelbord[rij][kolom] == 1) {
			System.out.print("[*]");
		} else {
			System.out.print("[ ]");
		}						
	}

	//gedaan met alles van deze rij, naar de volgende rij & nieuw lijntje
	System.out.println();

}
```

## Andere datastructuren

Dit hoofdstuk is voornamelijk optioneel, maar wel handig als je de richting van Development kiest in de toekomst van jouw Informatica-studies. Arrays zijn maar één van de vele soorten datastructuren, ofwel manieren om gegevens te gaan bijhouden in een logische structuur die je kan gebruiken binnen Java (en vele andere soorten programmeertalen). De belangrijkste worden hieronder nog eens opgesomd, maar een aantal van deze komen ook aan bod in het tweede deel van Cup of Java.

Stack

Een stack wordt gebruikt om een verzameling van objecten of elementen te gaan opslaan. Via een push-bewerking kunnen items toegevoegd worden aan de stack. De werking kan je vergelijken met een stapel papieren. Het papier dat bovenaan de stapel ligt, wordt eerst verwerkt of behandeld. 

![image](https://user-images.githubusercontent.com/70543493/126044761-594eac3c-82c2-42ae-ba99-db87c3da41c2.png)

```java
//een nieuwe stack aanmaken
Stack<int> verzamelingVanHotelKamerNummers = new Stack<>();

//is dit een lege stack?
System.out.println(verzamelingVanHotelKamerNummers.empty());

//nummers van hotelkamers toevoegen aan de stack
verzamelingVanHotelKamerNummers.push(20);
verzamelingVanHotelKamerNummers.push(13);
verzamelingVanHotelKamerNummers.push(89);
verzamelingVanHotelKamerNummers.push(90);
verzamelingVanHotelKamerNummers.push(11);
verzamelingVanHotelKamerNummers.push(45);
verzamelingVanHotelKamerNummers.push(18);

//18 is als laatste toegevoegd, dit is dus het element dat bovenaan de stapel ligt

//element dat bovenaan de stapel ligt gaan verwijderen
verzamelingVanHotelKamerNummers.pop();

//element tonen dat bovenaan de stapel ligt
System.out.println(verzamelingVanHotelKamerNummers.peek()); // 45 want dit ligt nu bovenaan de stapel

//op welke positie in de stack staat 90?
System.out.println(verzamelingVanHotelKamerNummers.search(90)); // 3

//stack doorlopen
for(int nummer : verzamelingVanHotelKamerNummers)
{
	System.out.println(nummer);
}
```

Queue

Een queue is letterlijk vertaald een wachtrij en de werking is heel gelijkaardig. Sta je als eerste in de wachtrij? Dan ben je ook als eerste aan de beurt. Dit is dus in tegenstelling tot de werking van een stack waarbij het enkel het laatste element is dat aan de beurt komt.

Het verschil met een stack is dat je van Queue géén objecten kan maken. Queue is een interface, een aspect dat voornamelijk aan bod komt in OOSD2. Er is géén directe manier om een Queue object aan te maken, maar we kunnen wel gebruik maken van klassen die afgeleid zijn van de Queue-interface. De meest voor de handliggende is de PriorityQueue klasse.

```java
//de Queue aanmaken
Queue<String> residentEvilGames = new PriorityQueue<String>();

//leerlingen toevoegen aan de Queue
residentEvilGames.add("Resident Evil");
residentEvilGames.add("Resident Evil 2");
residentEvilGames.add("Resident Evil 3: Nemesis");
residentEvilGames.add("Resident Evil Survivor");
residentEvilGames.add("Resident Evil Gaiden");
residentEvilGames.add("Resident Evil Code: Veronica");

//leerlingen toevoegen: extra manier
residentEvilGames.offer("");

//Eerste leerling is behandeld dus die gaan we verwijderen uit de wachtrij:
residentEvilGames.remove(); //

//Queue uitprinten
for(String gameNaam : residentEvilGames)
{
	System.out.println(gameNaam);
}
```

Linked List

Een linked list is anders opgebouwd dan eender van de voorbij getoonde datastructuren. Voornamelijk bestaat een Linked List niet uit blokken die elkaar aansluiten zoals bij een array, maar hier wordt er gewerkt met verwijzingen naar ier ga je rekening moeten houden dat er twee zaken worden bijgehouden: De positie

```java
//
	LinkedList<String> perioden = new LinkedList<String>();
  
        // Adding elements to the linked list
        perioden.add("Klassieke Oudheid");
	perioden.add("Nieuwe Tijd");
        perioden.addLast("Eigen Tijd");
        perioden.addFirst("Prehistorie");
        perioden.add(2, "Middeleeuwen");
  
        System.out.println(perioden); // ["Prehistorie", "Klassieke Oudheid", "Middeleeuwen", "Nieuwe Tijd", "Eigen Tijd"];
	
	perioden.removeFirst(); //Prehistorie wordt verwijderd
	perioden.removeLast(); //Eigen Tijd wordt verwijderd
	
	System.out.println(perioden); // ["Klassieke Oudheid", "Middeleeuwen", "Nieuwe Tijd"];
	
	perioden.remove(1); // Middeleeuwen wordt verwijderd
	perioden.remove("Nieuwe Tijd"); // Nieuwe Tijd wordt verwijderd
	
```

Hash

Een Hash is zeer toepasselijk wanneer je gegevens wilt opslaan waarvan er géén enkel gegeven twee of meerdere keren voorkomt. Daarnaast wordt ieder gegeven niet op index bewaard, maar met een "key". Deze key kan eender welke waarde hebben, maar is ook uniek in de lijst. Het object dat we gaan gebruiken is HashMap.

```java
hashmap
```

Stel dat je toch een unieke lijst wilt hebben zonder het gebruik van keys, dan kan je gebruik maken van een HashSet.

```java
HashSet<String> cars = new HashSet<String>();
cars.add("Volvo");
cars.add("BMW");
cars.add("Ford");
cars.add("BMW"); // is al in de lijst --> niet toevoegen
cars.add("Mazda");
System.out.println(cars); // ["Volvo", "BMW", "Ford", "Mazda"]
```




	
# 5. [Repositories]

We kunnen allerlei objecten aanmaken, maar we houden ze niet echt bij. Alles is zogezegd los in ons programma. Bij arrays hebben we gezien hoe we waarden binnen één bepaalde structuur kunnen bijhouden. Dit kunnen we ook doen bij objecten en hiervoor gaan we die lijst van objecten gaan gebruiken. Om objecten te gaan verzamelen en bij te houden gaan we gebruik maken van repositories ofwel een klasse die objecten gaat bijhouden in een lijst van objecten. 

Let op: dit is géén databank. Een databank gaat gegevens bijhouden die blijven bestaan zelfs al wordt ons programma afgesloten. Een repository wordt aangevuld/verminderd/geleegd enkel en alleen als ons programma draait en als we het afsluiten wordt er ook niks bewaard. Met andere woorden, is onze repository leeg bij het opstarten van het programma, dan zal die ook leeg zijn als we het programma een volgende keer gaan opstarten

Over de naamgeving: Als we een lijst willen bijhouden van hotelkamers gaan we dit HotelKamerRepository noemen. De naam is niet zo belangrijk, maar het is wel van belang dat je duidelijk kunt maken dat dit een lijst gaat bijhouden van allerlei hotelkamers. "Hotel" is zeker een mogelijk en geeft ook duidelijk aan dat het een verzameling is van bepaalde kamers. 

Andere voorbeelden:
* Klasse Bier -> BierWinkel / BierRepository
* Klasse Dvd -> DvdWinkel / DvdRepository
* Klasse FitnessApparaat -> Fitness / FitnessApparaatRepository

# 6. [Methodes]

In dit hoofdstuk gaan we wat verder op methodes in. Je hebt gezien hoe je een methode kan aanmaken en aanspreken. We hebben ook al gezien hoe we een methode van een object/klasse kunnen aanmaken en aanspreken. Als we werken met methodes van klassen moeten we goed het onderscheid houden tussen een static en een non-static methode.

## Static en non-static methodes.

Een **non-static methode** is een methode die we enkel en alleen kunnen gebruiken als we een object van een klasse hebben. Bijvoorbeeld bij hotels kunnen we de methode 'relax()' aanspreken die de zin 'good vibes in room x' gaat uitprinten waar 'x' staat voor een specifieke kamer. Deze methode is met andere woorden uniek per object.

```java
public void relax() {
	System.out.printf("good vibes in room %s.....", this.nummer);
}
```

We spreken de methode aan in de main-klasse. Bij non-static methodes hebben we een object van de klasse nodig. Deze maken we eerst aan (room404) en we spreken hierop de methode 'relax()' aan.

```java
public static void main(String[] args) {	
	//object aanmaken
	HotelKamer room404 = new HotelKamer(404, 24, 44);
	
	//print uit: 'good vibes in room 404.....'
	room404.relax();
}
```

Een **static methode** is een methode waar je helemaal géén object van een klasse nodig hebt. Hier wordt er vaak géén gebruik gemaakt van unieke waarden zoals bijvoorbeeld het nummer van de kamer zoals in het vorige voorbeeld. Bij het aanmaken van een static methode ben je verplicht om het keyword 'static' voor de naam van de methode te plaatsen. Anders zal Java deze methode herkennen als een non-static methode en dan heb je wél een object nodig.

```java
public static void browsen() {	
	System.out.println("Instagram: motivationalquotes, davidattenborough en woutvanaert hebben iets op hun verhaal geplaatst.");	
}
```

De methode aanspreken in de main-klasse doen we anders in vergelijking met een non-static methode. In de plaats van een object aan te maken en deze aan te spreken gaan we eerder direct de klasse opschrijven, in dit geval 'HotelKamer', en hierop de methode aanspreken.

```java
public static void main(String[] args) {	
	HotelKamer.browsen();
}
```

![image](https://user-images.githubusercontent.com/70543493/125093027-3745b000-e0d2-11eb-80b7-ec7cee04a4d5.png)

## Math

Binnen Java hebben we verschillende bibliotheekklassen. Een bibliotheekklasse voorziet methoden die we tot nu toe al eigenlijk onbewust gebruikt hebben. Specifiek wil ik de klasse Math nog eens toelichten. Deze klasse zal voornamelijk voor wiskundige bewerkingen gebruikt worden.

1. 'abs' zal de absolute waarde teruggeven. 

```java
Math.abs(-7,2); // -> 7.2
```

2. 'ceil' gaat een double afronden naar boven. 'floor' gaat een double afronden naar beneden.

```java
Math.ceil(5.1); // -> 6.0
Math.floor(5.6); // -> 5.0
```

4. 'cos', 'sin' en 'tan' komen van pas als we een eigenschap van een gemeten hoek willen berekenen. Deze drie functies staan respectievelijk voor cosinus, sinus en tangent.

```java
Math.cos(37); //  0.7654140519453434
Math.sin(37); // -0.6435381333569995
Math.tan(37); // -0.8407712554027597
```

5. 'pow' wordt gebruikt voor machtberekening waar je twee parameters meegeeft. Eerst het getal waar je de macht op gaat berekenen en dan het exponent dat je wilt gebruiken.

```java
Math.pow(5.0, 2.0); // 25.0
Math.pow(2.0, 3.0); // 8.0
```

6. 'exp' wordt gebruikt voor machtberekening waar je enkel het exponent meegeeft als parameter. Hier ga je het Euler-getal (of getal 'e') tot de macht van het meegeven exponent gaan berekenen. Bijvoorbeeld als je 2 meegeeft zal dit E^2 zijn ofwel 'E tot de macht 2'. 

```java
Math.exp(2.0); // 7.38905609893065
```

7. 'sqrt' wordt gebruikt om de vierkantswortel van een meegegeven getal te gaan berekenen. Je geeft enkel één parameter mee en dat is het getal waar je de vierkantswortel op gaat berekenen.

```java
Math.sqrt(25.0); // 5.0
Math.sqrt(36.0); // 6.0
```

8. 'min' wordt gebruikt om het kleinste getal van twee meegegeven getallen te gaan berekenen. 'max' gaat het grootste getal van twee meegegeven getallen gaan berekenen.

```java
Math.min(4.2, 6.1); // 4.2
Math.max(4.2, 6.1); // 6.1
```

## Pass-by-value

Bij het gebruik van methodes is het verstandig om te weten dat Java in zijn geheel een taal is die voornamelijk werkt met het **pass-by-value** principe. Dit wilt zeggen dat bij het ingeven van een variabele, als parameter in een methode, dat Java enkel de waarde gaat onthouden. Het omgekeerde van pass-by-value is **pass-by-reference** waarbij je juist een verwijzing naar een variabele gaat opslaan.

De nadruk van dit hoofdstuk ligt vooral bij het begrijpen en inzien hoe Java werkt in vergelijking met andere programmeertalen. Er zijn géén extra methoden of variabelen die gekend moeten worden.

Onderstaande animatie zou het principe duidelijk moeten maken. We spreken een methode aan die het kopje gaat vullen met koffie. Je ziet dat we van beide kopjes een kopie gaan maken, maar bij de linkerkant zie je dat iedere aanpassing aan het variabele ook wordt doorgevoerd naar de originele variabele. Rechts zie je dat dit niet het geval is en dat enkel de kopie wordt veranderd.

![pass-by-reference-vs-pass-by-value-animation](https://user-images.githubusercontent.com/70543493/125106839-682ce180-e0e0-11eb-91a7-33f59e81d0f7.gif)

Een tof weetje om te onthouden. Bij Java is het niet van belang om te weten waar jouw variabelen worden opgeslagen in het geheugen. Bij lower-level programmeertalen zoals C of Assembler is het juist omgekeerd en wel van noodzaak dat je weet waar jouw variabelen zijn opgeslagen in het geheugen. Soms is er de '&'-operator waarbij je de locatie van jouw variabele, die op het geheugen staat, kan achterhalen.

Onderstaand is een extra voorbeeld om het principe nog te verduidelijken. We gaan een kleine methode maken die het geboortejaar berekent van iemand. De enige parameter is de leeftijd van een persoon. In de methode gaan we het geboortejaar gaan berekenen door het huidige jaar (een constante waarde) te gaan verminderen met de meegegeven leeftijd.


```java
public int berekenGeboortejaar(int leeftijd) {
 	return geboorteJaar = CURRENT_YEAR – leeftijd;
}

public static void main(){
	int mijnLeeftijd = 23;
	berekenGeboortejaar(mijnLeeftijd);
}
```

Er zijn hier twee leeftijd-variabelen (leeftijd en mijnLeeftijd), maar omdat we hier werken met pass-by-value worden deze op twee verschillende locaties opgeslagen in het geheugen. Alles wat er gebeurt met 'leeftijd' zal niets veranderen aan 'mijnLeeftijd' ofwel de originele variabele.

Om dit nog te verduidelijken gaan we 'mijnLeeftijd' gaan verhogen met één. 'Leeftijd' zal niet veranderen en zal blijven op 23 in tegenstelling tot 'mijnLeeftijd' die wel degelijk zal verhogen met één en zo de waarde '24' zal hebben. 

```java
public void verhoogLeeftijd(int leeftijd){
	return leeftijd + 1; //23 + 1
}

public static void main(){
	int mijnLeeftijd = 23; //23
	verhoogLeeftijd(mijnLeeftijd); //24
}
```

Dit werkt eveneens ook zo bij objecten. We nemen het voorbeeld van HotelKamer er weer even bij. We gaan via een methode een eigenschap van een gemaakt object gaan aanpassen. Er is maar één parameter bij deze methode en dat is een object van de klasse HotelKamer.

In de methode 'downgrade()' wordt de waarde van de eigenschap 'isLuxueus' verandert naar 'false' bij het meegegeven object. Deze aanpassing wordt direct aangepast aan het originele object.

```java
public static void main(){
	// we maken een object HotelKamer aan
	HotelKamer room343 = new HotelKamer(343, 28, true, true, new String[]{"xbox"}, 56);
	System.out.println(room343.getIsLuxueus()); //true

	// de eigenschap isLuxueus gaan we op false zetten via een methode 'downgrade'
	downgrade(room343);
	System.out.println(room343.getIsLuxueus()); //false
}

// we vragen een object van de klasse HotelKamer op als parameter
// via de setter gaan we de eigenschap 'isLuxueus' gaan vervangen naar 'false'
public void downgrade(HotelKamer hotelkamer){
	hotelkamer.setIsLuxueus(false);
}
```

We kunnen, als laatste deel van pass-by-value, ook arrays meegeven als parameter in een methode.

```java
int[] arrOppervlaktes = {21, 32, 45, 70};
		
wijzigOppervlakte(arrOppervlaktes[2]);
		
wijzigArrOppervlaktes(arrOppervlaktes);
		
//kijken of de oppervlakte van de waarde op index 2 verandert is
System.out.println(arrOppervlaktes[2]);
		
//de gehele array doorlopen
for(int getal : arrOppervlaktes) {
	System.out.println(getal);
}
```

Onze methodes zien er zo uit:

De onderstaande methode ga je een array opvragen. Deze array wordt door de for-lus doorlopen en we gaan iedere oppervlakte gaan uitprinten. Iedere oppervlakte zal gehalveerd zijn.

```java
public static void downsizeArrOppervlakte(int[] arrOppervlakte){
	for(int teller = 0; teller < arrOppervlakte.length; teller++){
		arrOppervlakte[teller]*=2;
	}
}
```
```java
//de gehele array doorlopen
for(int getal : arrOppervlaktes) {
	System.out.println(getal); //oppervlakte gehalveerd
}
```

Nu merk je iets anders op. We geven één element mee uit onze array en gebruiken die als parameter op de methode 'wijzigOppervlakte'. Deze zou normaal gezien gehalveerd moeten worden, maar hier gaat dit niet het geval zijn. We geven namelijk een waarde mee, maar Java weet niet van waar die waarde komt dus dit zal dan ook niet worden aangepast in de oorspronkelijke array.

Het grote verschil is dat je hier een waarde meegeeft uit een array tegenover hierboven waar je bij 'downsizeArrOppervlakte' de gehele array gaat veranderen binnen de methode.

```java
downsizeOppervlakte(arrOppervlaktes[2]);

//kijken of de oppervlakte van de waarde op index 2 verandert is
System.out.println(arrOppervlaktes[2]);
```
```java
public static void downsizeOppervlakte(int element) {
	element *= 0.5; // blijft 45, wordt niet gehalveerd
}
```

Hoe lossen we dit op? We kunnen de array-methode veranderen zodanig dat we enkel het element op index 2 gaan wijzigen. Dat ziet er als volgt uit:

```java
public static void downsizeArrOppervlakte(int[] arrOppervlakte){
	for(int teller = 0; teller < arrOppervlakte.length; teller++){
		if(teller == 2){
			arrOppervlakte[teller]*=2;
		}
	}
}
```

De uitvoer ziet er als volgt uit:

```
21
32
22
70
```

# 7. Pijlers van OO.

## Pijler 1: Inkapseling
Dit is een soort van techniek waarbij je data, ofwel jouw variabelen, en code die op de data gaat reageren, ofwel jouw methoden, gaat inwikkelen tot één bepaalde eenheid. Je wilt met andere woorden dus er voor zorgen dat andere klassen géén toegang hebben tot methoden of variabelen van andere klassen.

Hiervoor gebruik je het 'private' keyword. Al jouw variabelen van een klasse ga je op private zetten zodat enkel binnen de klasse met deze variabelen kunnen gewerkt worden. Dit doen we om ongeauthoriseerd gebruik van andere klassen te voorkomen. 

```
private int kamerNr;
private boolean isLuxueus;
private String[] extras;

private void setKamerNr(int kamerNr){
	this.kamerNr = kamerNr;
}

private void setIsLuxueus(boolean isLuxueus){
	this.IsLuxueus = isLuxueus;
}
```

Als laatste moet je er voor zorgen dat jouw getters wél op publiek staan. Op deze manier kan je vanuit een andere klasse of uit de main-methode toch nog informatie over een object gaan ophalen.

# Pijler 2: Abstractie
Bij abstractie ga je de complexiteit van code eigenlijk gaan maskeren of verbergen en eerder ga je gaan focussen op de functionaliteit voor de gebruiker. Je zorgt er met andere woorden voor dat je enkel de belangrijke zaken gaat tonen aan de gebruiker en alle interne details eigenlijk niet zichtbaar zijn.

Bij het sturen van een Discord-bericht ga je enkel kijken naar het sturen en/of ontvangen, maar je gaat zelf niet stil staan 'hoe' dat dit proces verloopt. De nadruk hier ligt vooral op **wat** een object doet in Object-Oriented ontwikkeling in de plaats van hoe het iets moet doen.

In OOSD2 komen interfaces en abstracte klassen aan bod.

# Pijler 3: Overerving
Overerving is een techniek die vooral de nadruk legt op herbruikbaarheid. Stel dat we twee héél gelijkaardige klassen hebben met één of meerdere verschillen, dan zou het overbodig zijn om zoveel code opnieuw te gaan uittypen. We kunnen eigenlijk gaan werken met een klasse die methoden en variabelen gaat overnemen.

![image](https://user-images.githubusercontent.com/70543493/125122223-60c40300-e0f5-11eb-9a1b-5f985e9e6ec9.png)

Hieronder hebben we drie klassen. De klasse 'Resto' is zogezegd de parent-klasse. Dit betekent dat alle subklassen of klassen onder 'Resto' alles (variabelen en methoden) gaan overnemen zonder dat deze inhoud opnieuw moet geschreven worden. 

Klasse 'Pizzeria' en 'Frituur' gaan dus de drie variabelen (naam, kapitaal en locatie) én de twee methoden (serveerEten en geefRekening) gaan overnemen. Zij hebben wél ook hun eigen methoden die ze aan de al bestaande inhoud gaan toevoegen.

Een object van de klasse 'Pizzeria' heeft alle methoden van de klasse 'Resto', maar ook nog een extra variabele 'diameterGrootstePizza' die kan gebruikt worden. Ook zijn er de methoden throwPizzaInAir, add- en removePineapple.
Een object van de klasse 'Frituur' heeft alle methoden van de klasse 'Resto', maar ook een array van Strings 'soortenDirtyFries' en ook een methode 'bakFrietjes'.

Je kan wel niet met een object van klasse 'Frituur' bijvoorbeeld de methode 'addPineapple' aanspreken. Dit gaat niet lukken omdat dit enkel voor de subklasse 'Pizzeria' werkt. Ook omgekeerd waar een object van 'Pizzeria' bijvoorbeeld niet 'soortenDirtyFries' gaat hebben.

In code ziet het er als volgt uit.

Bij de klasse Resto, of in dit geval de parent-klasse, moeten we eigenlijk niks aanpassen. Hier gebruiken we twee constructors en we voorzien publieke getters en setters. Als laatste voorzien we ook een toString methode. De override is hier noodzakelijk.

```Klasse Resto```
```java
public class Resto {
	
	String naam;
	int kapitaal;
	String locatie;
	
	public Resto(String naam, int kapitaal, String locatie) {
		this.naam = naam;
		this.kapitaal = kapitaal;
		this.locatie = locatie;
	}
	
	public Resto() {
		this.naam = "Example";
		this.kapitaal = 0;
		this.locatie = "";
	}
	
	private void serveerEten() {
		System.out.println("Bestelling is klaar!");
	}
	
	private void geefRekening() {
		System.out.println("");
	}

	public String getNaam() {
		return naam;
	}

	public void setNaam(String naam) {
		this.naam = naam;
	}

	public int getKapitaal() {
		return kapitaal;
	}

	public void setKapitaal(int kapitaal) {
		this.kapitaal = kapitaal;
	}

	public String getLocatie() {
		return locatie;
	}

	public void setLocatie(String locatie) {
		this.locatie = locatie;
	}
	
	@Override
	public String toString() {
		return naam + " heeft een kapitaal van €" + kapitaal + " en is gevestigd te " + locatie + ".";
	}

}
```

Hieronder zie je één van de twee subklassen. Om er voor te zorgen dat we alles over erven van de klasse Resto gaan we bij 'public class Pizzeria' achteraan het keyword 'extends Resto' gaan schrijven. We voegen dus 'extends' gevolgd door de klassenaam van waar we willen overerven toe.

Voor de constructor kunnen we ook makkelijker te werk gaan. We gaan hiervoor werken met 'super()'. In de ronde haakjes gaan we alle parameters opgeven die óók worden gebruikt in de constructor van de parentklasse. Bij een lege constructor hoeven we ook niets in de 'super' methode te plaatsen.

Bij toString hoeven we ook niet alles opnieuw uit te schrijven. We kunnen eigenlijk verdergaan van waar de toString van Resto eindigde. In bepaalde gevallen is het toch beter om vanaf nul terug te beginnen. Dan heb je 'super.toString()' niet meer nodig.

```Klasse Pizzeria```
```java
package domein;

public class Pizzeria extends Resto {

	int diameterGrootstePizza;

	public Pizzeria() {
		super();
		this.diameterGrootstePizza = 0;
	}

	public Pizzeria(String naam, int kapitaal, String locatie, int diameterGrootstePizza) {
		super(naam, kapitaal, locatie);
		this.diameterGrootstePizza = diameterGrootstePizza;
	}
	
	public int getDiameterGrootstePizza() {
		return diameterGrootstePizza;
	}

	public void setDiameterGrootstePizza(int diameterGrootstePizza) {
		this.diameterGrootstePizza = diameterGrootstePizza;
	}

	private void throwPizzaInAir() {
		if(Math.random() < 0.5) {
			System.out.println("Nice!");
		} else {
			System.out.println("Oops!");
		}	
	}
	
	private void addPineapple() {
		System.out.println("");
	}
	
	private void removePineapple() {
		System.out.println("");
	}

	@Override
	public String toString() {
		return super.toString() + "\n Deze vestiging heeft een speciale pizza die " + diameterGrootstePizza + " groot is.";
	}
}
```

Bij de tweede subklasse gelden de zelfde regels.

1. 'extends Resto'
2. 'super()' gebruiken bij constructor
3. 'super.toString()' gebruiken indien nuttig bij jouw toString() methode.

```Klasse Frituur```
```java
package domein;

import java.util.ArrayList;
import java.util.List;

public class Frituur extends Resto {
	
	List<String> soortenDirtyFries;

	public Frituur() {
		super();
		this.soortenDirtyFries = new ArrayList<>();
	}

	public Frituur(String naam, int kapitaal, String locatie, List<String> soortenDirtyFries) {
		super(naam, kapitaal, locatie);
		this.soortenDirtyFries = soortenDirtyFries;
	}
	
	private void bakFrietjes() {
		//
	}
	
	@Override
	public String toString() {
		return super.toString() + "\n Als specialiteiten heeft dit etablissement ook: " + this.soortenDirtyFries;
	}
}

```


We kunnen dit eens uittesten door wat dummy-objecten aan te maken.

```java
public static void main(String[] args) {
	List<String> soortenDFries = new ArrayList<>();
	soortenDFries.add("boulaintje");
	soortenDFries.add("romboutje");
	
	Resto bijMoeke = new Resto("Bij Moeke", 100000, "Moedersesteenweg 225");
	Pizzeria alDente = new Pizzeria("Al Dente", 20000, "Dentestraat 24", 50);
	Frituur hetHoekske = new Frituur("Het Hoekske", 50000, "Hoekstraat 1", soortenDFries);
		
	System.out.println(bijMoeke.toString());
	System.out.println(alDente.toString());
	System.out.println(hetHoekske.toString());	
}
```

```Uitvoer:```
```
Bij Moeke heeft een kapitaal van €100000 en is gevestigd te Moedersesteenweg 225.
Al Dente heeft een kapitaal van €20000 en is gevestigd te Dentestraat 24.
 Deze vestiging heeft een speciale pizza die 50 cm groot is.
Het Hoekske heeft een kapitaal van €50000 en is gevestigd te Hoekstraat 1.
 Als specialiteiten heeft dit etablissement ook: [boulaintje, romboutje]
```

Op het vlak van overerving kan je hier héél ver in gaan. Je kan met andere woorden een oneindig aantal klassen laten overerven van één parentklasse, maar ook een stamboom van klassen creëren die keer op keer gaan overerven van een parent-klasse.


# Pijler 4: Polymorfisme

Bij het ontwerpen van applicaties is het van belang om ook vooruit te denken. Aanpassingen maken aan ons domein zou zo simpel en niet al te omslachtig mogen zijn. Stel dat we een nieuwe subklasse aan de klasse 'Resto' zouden toevoegen, dan zouden we praktisch niet eens aan één van de klassen mogen komen tenzij als die klasse rechtstreeks te maken heeft met de klasse die we willen toevoegen.

We nemen het voorbeeld van daarnet nog eens. We hebben drie objecten: één Resto, één Pizzeria en één Frituur. In principe kunnen we de referentie helemaal vooraan (voor de naam van het object) ook veranderen naar 'Resto' bij alle drie de objecten.  Het is perfect oké om eerst de objecten als een parent-klasse te gaan aanmaken en dan later te gaan specifiëren naar de gekozen subklasse.

In mensentaal: je kan eerst drie restaurants gaan maken en dan later gaan zeggen welk soort restaurant het is.

```java
Resto bijMoeke = new Resto("Bij Moeke", 100000, "Moedersesteenweg 225");
Resto alDente = new Pizzeria("Al Dente", 20000, "Dentestraat 24", 50);
Resto hetHoekske = new Frituur("Het Hoekske", 50000, "Hoekstraat 1", soortenDFries);
```

Stel dat Pizzeria 'Al Dente' opeens een grote verandering in koers wilt nemen. Nu wilt het jarenlange familiebedrijf veranderen naar een frituur waar ze Italiaanse frituursnacks aanbieden. We kunnen het object 'alDente' gaan aanpassen naar een object van een andere klasse.

```java
//voor de verandering
Resto alDente = new Pizzeria("Al Dente", 20000, "Dentestraat 24", 50);

//veranderen naar een andere subklasse
alDente = new Frituur("Al Dente", 20000, "Dentestraat 24", ['Arancini', 'Panzerotti']);
```

Stel dat we nu een specifieke methode gaan aanspreken die enkel en alleen bij de klasse Pizzeria werkt, bijvoorbeeld throwPizzaInAir(), dan krijgen we wél degelijk een compilatiefout. Dit komt omdat er in de subklasse Frituur géén methode is van die naam.

Maar oude tradities verleren die wijze Italianen niet, we willen een manier zoeken om toch nog die methode aan te spreken, zelfs al zitten onze vrienden van de laars met een frituur aan hun been. We kunnen namelijk een object gaan **downcasten**. Dit wil zeggen dat we de klasse van het object behouden (deze blijft een Frituur), máár we veranderen de verwijzing wél.

Hieronder merk je op dat we in de linkerhelft het object gaan maken zoals we gewoon zijn, maar in de rechterhelft nemen wij het object van de klasse Frituur en gaan wij '(Pizzeria)' er voor plaatsen. Zogezegd een soort masker dat we gaan plakken op ons object. Als wij nu de methode aanspreken, dan gaat dit wél lukken.

De linkerhelft is wel degelijk belangrijk. We kunnen niét downcasten als we in de linkerhelft gaan verwijzen naar de klasse Frituur. Dit moet zeker op 'Pizzeria' staan.

```java
alDente = new Frituur("Al Dente", 20000, "Dentestraat 24", ['Arancini', 'Panzerotti']);
Pizzeria alDente = (Pizzeria) alDente;
alDente.throwPizzaInAir();
```

Stel dat we nu een methode willen die vraagt naar een Resto-object en om het even welk object het is, het wil een pizza in de lucht gooien. We moeten dus kunnen achterhalen of een object van de klasse Pizzeria is of niet. Hiervoor kunnen we **instanceof** gebruiken.

We hebben dus de methode 'gooiPizzaInLucht'. Dit gaat eender welk object als parameter gaan oppakken en áls dit een Pizzeria is gaan we direct de methode 'throwPizzaInAir()' gaan aanspreken. Is dit géén object van het type Pizzeria, dan gaan we eerst dit object moeten downcasten zodanig dat we deze methode wél kunnen aanspreken.

```java
public void gooiPizzaInLucht(Resto restoObject){

	if(restoObject instanceof Pizzeria){
		restoObject.throwPizzaInAir();
	} else {
		Pizzeria restoObject = (Pizzeria) restoObject;
		restoObject.throwPizzaInAir();
	}
}
```

# 8. Applicaties testen

## Waarom via Unit-testen?

We kunnen eindeloos applicaties gaan uittesten door deze te laten draaien en vervolgens dan een foute combinatie in te geven om zo een bepaalde fout of error te triggeren. Het nadeel is dat dit proces moeizamer zal verlopen eenmaal we gaan werken aan grote applicaties. Ook voelt het vaak aan door in het wild wat rond te slaan, hopend op een foutmelding of bepaalde exception die wordt gegooid.


Als laatste onderdeel van OOSD1 wordt er gesproken over testen, meer specifiek het testen via JUnit ofwel Unit-testen. Hier gaan we testmethodes gaan opbouwen die ons gaan helpen om het resultaat van een methode te gaan analyseren aan de hand van zelf ingegeven waarden.

We gaan altijd eerst de test schrijven van de methode die we willen uittesten en dan pas de code of _body_ binnenin die methode. Op deze manier kunnen we ook stapgewijs gaan achterhalen wat er nog eventueel ontbreekt in de huidige code qua exceptions, parameters, vergelijking, enz.

# Opbouw

Een testmethode ziet er praktisch gelijkaardig uit als eender welke methode. De naamgeving bestaat uit drie onderdelen:

	1 De naam van de methode die we willen testen. Als je een constructor wilt uittesten, dan kan je gebruik maken van _maak_ gevolgd door de naam van jouw Klasse.
	2 De bewering of _assertion_. Klopt een bepaald scenario, of juist niet, bij een bepaald resultaat.
	3 Het resultaat dat de methode **moet** teruggeven.
	
We bekijken een voorbeeld van een test. Hiervoor werken we met een nieuwe klasse _Frisco_. Dit is een klasse die een object gaat aanmaken dat een ijsje voorstelt. Hier houdewn we de prijs, naam en smaken bij. Zoals je ziet hebben we weinig tot nog géén code ingevoerd in de body. We gaan eerst stapgewijs kijken waar onze applicatie zeker rekening mee moet houden

```java
//gebruikte variabelen
String naam;
double prijs;
String[] smaken = new String[5];

//constructor
public Frisco(String naam, double prijs, String[] smaken){

}


//setter voor de naam
private void setNaam(String naam){
	
}

//setter voor prijs
private void setPrijs(double prijs){
	
}

//setter voor de smaken van een ijsje
private void setSmaken(String[] smaken){
	
}

//deze methode gaan we gebruiken om te kijken of de prijs wél correct is
private boolean controleerPrijs(double prijs){

}

private boolean controleerSmaken(String[] smaken){

}

private boolean controleerPrijs(double prijs){

}

```


## Assertions

We kunnen heel specifiek gaan testen wanneer er een exception wel of niet wordt gegooid binnen ons programma. Hiervoor gaan we assertions gaan gebruiken. Bij een assertion wordt er gevraagd naar een bepaalde boolean als parameter. Als deze boolean niét overeenstemt met de assertion, dan zal er een exception gegooid worden. 

We gebruiken testen specifiek om te zien of er bij een bepaalde waarde of omstandigheid een foutmelding wordt gegeven aan de gebruiker.

Zo kunnen we bijvoorbeeld gaan kijken of een bepaalde waarde bijvoorbeeld null is, denk maar aan het ingeven van de naam voor een object. Of van een vorig voorbeeld, een hotelkamer-object aanmaken met een lege kamernaam. Dit kunnen we voorkomen door bijvoorbeeld een exception in ons programma te schrijven.

Bij het opbouwen van testmethoden gaan we werken met de drie A opdeling. Dit zijn drie deeltjes die je zeker terug moet vinden als je een testmethode opbouwt.



**assertEquals**: Zijn de waarden met elkaar gelijk? Zo ja, dan testen we of er een exception wordt gegooid.

```java
@Test
public void setPrijs_prijsGelijkAanNul_retourneertTrue() {
    
    //Eerste A: We zetten alle benodigdheden klaar voor de test. We hebben sowieso een prijs nodig en ook een object van de klasse Frisco
    Frisco nieuweFrisco = new Frisco("test", 1, [""]);
    double prijs = 0.00;
    
    //Tweede A: We spreken de methode aan die we willen gebruiken. De methode geeft een boolean terug en die gaan we opslaan.
    nieuweFrisco.setPrijs(prijs);
    
    //Derde A: We gebruiken de methode assertTrue om te kijken of dit ook daadwerkelijk zo is. Als de prijs onder nul is, dan zal de test correct zijn.
    assertEquals(prijs, 0);
    
}
```

De nieuwe methode ziet er dan als volgt uit. Als je de test opnieuw doet zal je zien dat je een ander resultaat zal krijgen. Dit komt omdat er wél een error wordt gegooid.

```java
private void setPrijs(double prijs){
	if(prijs == 0)
		throw new IllegalArgumentException("Prijs mag niet nul zijn!");
	else
		this.prijs = prijs;
}
```

**assertArrayEquals**: Komen de arrays met elkaar overeen? Hebben beide arrays dezelfde inhoud en grootte?

```java
@Test
public void setSmaken_arraySmakenIsLeeg_retourneertTrue() {
    //Eerste A
    Frisco nieuweFrisco = new Frisco("test", 1, [""]);
    String[] smaken = new String[1]{""};
    
    //Tweede A
    nieuweFrisco.setSmaken(smaken);
    
    //Derde A
    assertArrayEquals(smaken, new String[1]{""});
}
```

De nieuwe methode ziet er dan als volgt uit:

```java
private void setSmaken(String[] smaken){
	if(smaken == new String[]{""})
		throw new IllegalArgumentException("Je moet minstens één smaak ingeven!");
	else
		this.smaken = smaken;
}
```

**assertNull**: Heeft het object een null-waarde? Is dit een object dat null is? 

```java
@Test
public void controleerNaam_naamIsNull_retourneertTrue() {
    
    //Eerste A
    Frisco nieuweFrisco = new Frisco("test", 1, [""]);
    String naam = null;
    
    //Tweede A
    nieuweFrisco.controleerNaam(naam);
    
    //Derde A
    assertNull(naam);
}
```

De nieuwe methode ziet er dan als volgt uit:

```java
private void setNaam(String naam){

	if(naam == null)
		throw new IllegalArgumentException("Geef iets in!");
	else
		this.naam = naam;
}

```

**assertNotNull** Heeft dit object wél een waarde? Kan gebruikt worden als alternatief voor assertNull.


**assertTrue** en **assertFalse** komen hier heel goed van pas. Bij assertTrue gaat er gekeken worden of de meegegeven boolean op true staat. Bij assertFalse gaat er gekeken worden of de boolean op false staat.

```java
@Test
public void controleerPrijs_prijsOnderNul_retourneertTrue(){
//Eerste A
Frisco nieuweFrisco = new Frisco("test", 1, [""]);
double prijs = -2.34;
	
//Tweede A
boolean result = nieuweFrisco.controleerPrijs(prijs);
	
//Derde A
assertTrue(result);
	
//tweede mogelijke oplossing
//aangezien controleerPrijs een boolean teruggeeft kunnen we deze direct in de assertTrue plaatsen
	assertTrue(nieuweFrisco.controleerPrijs(prijs), "De prijs mag niet kleiner dan nul zijn!")
}
```

```java
private void setPrijs(double prijs){
	if(controleerPrijs == true)
		this.prijs = prijs;
}

private boolean controleerPrijs(double prijs){
	if(prijs == 0){
		throw new IllegalArgumentException("Prijs mag niet gelijk zijn aan nul!");
		return false;
	} elseif(prijs >= 0){
		throw new IllegalArgumentException("Prijs mag niet onder nul zijn!");
		return false;
	} else {
		return true;
	}
	
}
```



We kunnen bij assertTrue/False en assertNull ook nog een stukje tekst meegeven. Deze zal enkel en alleen getoond worden als de stelling fout is.

```java
Frisco nieuweFrisco = new Frisco("test", 1, [""]);
double prijs = -2.34;

//mogelijkheid één:
boolean result = nieuweFrisco.controleerPrijs(prijs);

assertTrue(result, "De prijs mag niet kleiner dan nul zijn!"); //Tekst wordt getoond.
```

 ## Before Each
 Je hebt waarschijnlijk al opgemerkt dat we héél vaak het volgende lijntje gebruiken:
 
 ```java
 Frisco nieuweFrisco = new Frisco("test", 1, [""]);
 ```
 
 Hierin maken we een gewoon dummy-object van de klasse Frisco aan. Dit gebruiken we in iedere testmethode. We kunnen gebruik maken van een **Before Each**. Zoals de naam al deels meegeeft is het een stukje code dat bij iedere testmethode wordt herhaald. Dit betekent dat we dit maar eenmalig moeten meegeven en dat we dit stukje code kunnen weglaten uit onze testklasse.
 
 ```java
 @BeforeEach
 public void before(){
 	Frisco nieuweFrisco = new Frisco("test", 1, [""]);
 }
 
 @Test
public void controleerPrijs_prijsOnderNul_retourneertTrue(){
 	double prijs = -2.34;
	
boolean result = nieuweFrisco.controleerPrijs(prijs);
	
assertTrue(result);
}
```

## Geparameteriseerde testen

Hierboven hebben we telkens maar één parameter meegegeven. We kunnen hier verder op in gaan en er voor zorgen dat we één testmethode hebben waar we meerdere parameters kunnen meegeven.

Om een methode als een geparameteriseerde test te laten herkennen zijn we verplicht om @ParameterizedTest mee te geven. 

@ValueSource is belangrijk bij het geparameteriseerde testen. Alles binnen de array van objecten zijn waarden waar onze testmethode op gaat testen. We krijgen achteraf dan ook een lijst te zien van welke waarden wél en niet door de test zijn geraakt.

Stel dat we ook willen testen op null en/of lege waarden (""), dan kunnen we @NullAndEmptySource mee geven. Dan moeten we dit ook niet meer mee geven bij @ValueSource.

Hieronder zie je een herwerkt voorbeeld voor setNaam. We gaan meerdere parameters mee geven waaronder ook null-waarden en lege velden.

```java
 @BeforeEach
 public void before(){
 	Frisco nieuweFrisco = new Frisco("test", 1, [""]);
 }
 
 @ParameterizedTest
 @NullAndEmptySource
 @ValueSource(strings = {"        ", "a", "A"})
 public void setNaam_ongeldigeParameters_gooitException(String naam){
 	Assertions.assertThrows(IllegalArgumentException.class, () -> {nieuweFrisco.setNaam(naam); } );
 }
 
 
 @ParameterizedTest
 @NullAndEmptySource
 @ValueSource(doubles = {1.00, -2.34, 0.00, -0.01})
 public void setPrijs_ongeldigeParameters_gooitException(double prijs){
 	Assertions.assertThrows(IllegalArgumentException.class, () -> {nieuweFrisco.setPrijs(prijs); } );
 }
```

# OOSD2

Alle leerstof die aan bod komt in OOSD1 werd hierboven besproken. Er zijn bepaalde zaken, waaronder polymorfisme en overerving, die opnieuw aan bod komen in OOSD2. Hieronder wordt er dan ook respectievelijk kort nog eens herhaald wat er werd besproken in die bepaalde hoofdstukken, maar de nadruk ligt vooral op de nieuwe theorie.

# 1. [Overerving: Deel twee]

# Wat vooraf ging:

Bij overerving gaan we dus altijd werken met een soortgelijke klassenhiërarchie. Een subklasse gaat altijd één superklasse hebben, maar kan één tot een oneindig aantal verschillende subklassen hebben.

Om te weten of iets van een bepaalde klasse is kunnen we werken met de operator _instanceof_. Deze geeft een boolean terug afhankelijk of dat een bepaald object van de meegegeven klasse is. De vraag die letterlijk wordt gesteld is: "Is dit object van de klasse [klassenaam]?" Hieronder zie je enkele voorbeelden: 

```java
Auto mercedes = new Auto();
Fiets giant = new Fiets();
Fiets specialized = new MountainBike(); //Mountainbike is een subklasse van Fiets

System.out.println(mercedes instanceof Auto); //Is mercedes een Auto? --> true
System.out.println(giant instanceof Fiets); //Is giant een Fiets? --> true
System.out.println(specialized instanceof Fiets); // Is specialized een fiets? --> true: dit is een object van de klasse Fiets omdat Mountainbike zich onder Fiets bevindt

System.out.println(specialized instanceof Auto); //Is specialized een Auto? --> false: dit is géén object van de klasse Auto
System.out.println(giant instanceof Mountainbike); //Is giant een Mountainbike? --> false: Mountainbike is een subklasse van Fiets, maar het object giant is hier enkel en alleen van de superklasse Fiets
```

# Methodes van Objecten

Bij het hoofdstuk van objecten had je waarschijnlijk al gezien dat er enkele methodes waren die standaard al aangemaakt werden. toString() was hier één van en hebben we dan zelf aangepast. Als we dit niet hadden gedaan, dan kregen we nog steeds een String terug, maar enkel een andere tekst.

Er zijn nog talloze standaard ingebouwde methodes die we kunnen gebruiken en indien nodig ook kunnen aanpassen aan bepaalde noden.


_getClass()_ gaat de klasse gaan teruggeven waartoe het object behoort. 

_.equals()_ gaat twee objecten met elkaar vergelijken op basis van bepaalde criteria. Hiervoor heb je maar één parameter nodig en dat is een object waarmee je een gekozen object wilt gaan vergelijken. Als deze twee objecten gelijk zijn aan elkaar, dan wordt er een boolean (met als waarde: true) teruggegeven. Zijn deze twee objecten niet met elkaar gelijk, dan wordt er false teruggegeven.

Opmerking: Equals is hoofdlettergevoelig.

```java

String begroetingInNederland = "goeiedag";
String begroetingInVlaanderen = "goeiedag";
String begroetingInFrankrijk = "bonjour";

// equals methode: object.equals(objectVergelijken);

System.out.println(begroetingInNederland.equals(begroetingInVlaanderen)); // geeft true terug, want beide objecten hebben de zelfde waarden
System.out.println(begroetingInFrankrijk.equals(begroetingInNederland)); // geeft false terug, want er zijn twee verschillende waarden opgeslagen

//De constructor van de klasse Motorbike vraag twee parameters: de naam van het merk en het modeltype;
Motorbike hayabusa = new Motorbike("Suzuki", "GSX1300R");
Motorbike hayabusaKopie = new Motorbike("Suzuki", "GSX1300R");
Motorbike r1 = new Motorbike("Yamaha", "YZF-R1");

System.out.println(hayabusa.equals(r1)); // false, want de twee objecten hebben verschillende waarden
System.out.println(hayabusa.equals(hayabusaKopie)); // true, want de waarden van de twee objecten komen met elkaar overeen
```

Een methode die kijkt of iets gelijk staat aan een ander object? Waarom zou je dan bijvoorbeeld niet simpelweg gebruik kunnen maken van "==" in plaats van equals?
Het verschil is dat '**equals**' een methode is die de **waarde** van een object gaat vergelijken, terwijl **'=='** eerder een operator is die gaat kijken naar het **adres** van waar dat object is opgeslagen. We keren even terug naar het hoofdstuk van variabelen waar we praatten over het opslaan en onthouden van variabelen. Onderstaand schema is hoe ons geheugen er uit ziet als we de vijf objecten, van bovenstaande code, hebben aangemaakt.

| Plaats  | Waarde |
| ------------- | ------------- |
| 101  |   |
| 102  |   |
| 103  | "goeiedag"  |
| 104  | "goeiedag"  |
| 105  | "bonjour"  |
| 106  |   |
| 107  | ["Suzuki", "GSX1300R"]  |
| 108  | ["Suzuki", "GSX1300R"]  |
| 109  | ["Yamaha", "YZF-R1"]  |


We zien dat alle variabelen op verschillende plaatsen worden opgeslagen desondanks het feit dat de twee Nederlandstalige begroetingen en de twee Hayabusa-motoren toch de zelfde waarde hebben.

Bij equals worden de waarden met elkaar vergeleken (bvb "goeiedag" & "goeiedag" --> true).
Bij "==" worden de adressen met elkaar vergeleken (bvb "goeiedag" (103) == "goeiedag" (104) --> false.

We kunnen eveneens de equals methode ook gaan aanpassen naar een specifiekere waarde. Stel dat we een extra motor van Yamaha gaan toevoegen en willen dat de equals methode gaat vergelijken op merk, dan kunnen we dit ook gaan aanpassen. Hiervoor is opnieuw "@Override" nodig, zoals voordien werd gebruikt bij de toString() methode.

Extra: We maken ook gebruik van de methode _hashCode()_. Deze wordt vaak samen met de equals methode gebruikt. De hashcode methode wordt gebruikt om ieder object, zelfs al zijn ze identiek qua waarden, uniek te gaan representeren. Als we de methode gaan oproepen krijgen we eigenlijk de code terug van waar dit object is opgeslagen in ons geheugen.

```java
Motorbike hayabusa = new Motorbike("Suzuki", "GSX1300R");
Motorbike hayabusaKopie = new Motorbike("Suzuki", "GSX1300R");

System.out.println(hayabusa.hashCode());
System.out.println(hayabusaKopie.hashCode());
```

```java
public class Motorfiets extends Voertuig{

	private String merk;
	private String modelNummer;
	
	public Motorfiets(String merk, String modelNummer){
		super();
		this.merk = merk;
		this.modelNummer = modelNummer;
	}
	
	public String getMerk(){
		return this.merk;
	}
	
	@Override
	public boolean equals(Motorfiets motorFiets){
	
		if(this == motorFiets){
			return true; // zijn deze twee motorfietsen aan elkaar gelijk? equals is true
		}
		
		if(motorFiets == null){
			return false; // is de meegegeven motorfiets een null-object? equals is false
		}
		
		if(getClass() != motorFiets.getClass()){
			return false; // is de klasse van de meegegeven object niet hetzelfde als die van het object waar je mee vergelijkt? (bvb een Racefiets vergelijken met een Motorfiets) equals is false
		}
		
		Motorfiets castMotorFiets = (Motorfiets) motorFiets; // we casten het meegegeven object naar een object van de klasse Motorfiets.
		
		if(this.merk != castMotorFiets.getMerk()){
			return false; // is het merk van de gecastte motorfiets niet gelijk aan het merk van deze motorfiets? equals is false
		} else {
			return true; // is het merk van de gecastte motorfiets wél gelijk aan het merk van deze motorfiets? equals is true
		}
	}
```

# Scope van een declaratie

De scope betekent eigenlijk de ruimte of gebied binnenin de code waarin een variabele toegankelijk is. We maken het onderscheid tussen een scope op klasseniveau en op methodniveau. Het verschil kan als volgt geïllustreerd worden:

Hieronder hebben wij bijvoorbeeld twee variabelen: merk en modelNummer. Dit zijn twee variabelen op klasseniveau.

Bij onze constructor geven wij twee gelijknamige parameters mee. De bedoeling van onze constructor is de twee klassevariabelen gaan initialiseren en ze een waarde gaan toekennen. We moeten dus het onderscheid maken tussen de twee soorten en dat doen we met het keyword **this**.

Bij de setter geldt hetzelfde principe. We willen de klassevariabele gaan overschrijven met de meegegeven parameter, ofwel de methodvariabele. Hier gebruiken we weer bij enkel de klassevariabele het keyword 'this'. We hoeven niets extras toe te voegen bij de methodvariabele.

```java
public class Motorfiets extends Voertuig{

	private String merk;
	private String modelNummer;
	
	public Motorfiets(String merk, String modelNummer){
		super();
		this.merk = merk;
		this.modelNummer = modelNummer;
	} 
	
	private setMerk(String merk){
		this.merk = merk;
	}
	
}
	
```

# Abstracte klassen





# 2. [Polymorfisme]

# 3. [Lambda Expressies]

# 4. [Exception Handling]

# 5. [Verzamelingen]

# 6. [Streams]

# 7. [Strings en regex]

# 8. [Bestandsverwerking]
