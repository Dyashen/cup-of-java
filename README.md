# Cup Of Java
Hallo! Ik ben Dylan Cluyse. Washed-up student van de lerarenopleiding en nu student aan Hogeschool Gent. In deze Github repo wil ik vooral de basis voorleggen van programmeren met Java. Deze leerinhoud is gebaseerd op basis van het curriculum 2020-2021. Tijdens je eerste jaar zal je in het vak OOSD1 ook een deel ontwerpen krijgen. Dit komt aan bod in een andere repository.

Bij "Cup of Java" wil ik jullie vooral een andere inkijk geven in het vak, andere voorbeelden tonen en ook een mogelijke cheatsheet geven voor wanneer je de inhoud moet toepassen in een praktijkgebonden opdracht.

No time to waste! Welcome to Java, take a seat, turn on your lo-fi/tech/drum&bass playlist and don't forget your cup of coffee! 
(I prefer tea 🍵)

# 1. [Introductie] You don't forget your first line of code. 

Voor het programmeren in Java heb je verschillende IDE's. Een IDE is een editor die wordt gebruikt om code op te bouwen en later te kunnen uitvoeren. Een functie bij de meeste IDE's is om te zien of je fouten hebt gemaakt in je code. Deze worden dan rood onderstreept en is vergelijkbaar met spellingsfouten bij het programma Word.

Vooraleer we kijken naar de code moeten we eerst een structuur opbouwen in onze compiler. Hiervoor maken we gebruik van packages waar we onze klassen/interfaces/enums gaan opslaan. Een klasse is een soortgelijk sjabloon waarin we later meer gebruik van gaan maken eenmaal we ons gaan focussen op object-geörienteerd programmeren. Een package maak je als volgend aan: Eerst selecteer je de source map, daarna maak je iets nieuws aan en dat nieuwe onderdeel is een package. Je geeft je een package een bijpassende naam, maar zoals je misschien al weet moeten we ons houden aan het verplichte drielagenmodel.

* Domein: Alle domeinklassen komen hier in. Later zal je zien dat dit alle klassen zullen zijn die we in het DCD hebben opgesteld.
* Persistentie: Dit zijn de klassen die een rechtstreekse verbinding gaan maken met een persistente bron. Dit is een bron die zijn inhoud niet gaat verliezen eenmaal we het programma afsluiten in tegenstelling tot het domein waarin de ingegeven inhoud verloren raakt eenmaal je je programma afsluit. 
* CUI: In het begin van programmeren gaan we voornamelijk werken met de CUI ofwel de commandline-based interface of console van je IDE.
* GUI: Vanaf het tweede semester zal je een GUI opbouwen. Hierin ga je alle klassen gaan bewaren die code bevatten van JavaFX of dergelijke grafische structuren afhankelijk van de IDE die je gebruikt.
* Main: Dit is de package waar je voornamelijk maar één klasse gaat hebben en dat is de StartUp klasse. Dit is de klasse die de eerste CUI/GUI klasse gaat aanspreken van je programma en is essentieel voor een goed werkend programma. 

![Package aanmaken in Eclipse.](https://i.imgur.com/kSac0T8.png)

Nu kunnen we klassen aanmaken binnenin één van de packages. Later gaan we ook zien dat we ook enums en interfaces kunnen aanmaken, maar dat komt pas later aan bod. We volgen de zelfde stappen, maar selecteren "Class" in plaats van "Package". 

Eenmaal onze structuur is opgebouwd kunnen we beginnen met ons allereerste lijntje code te schrijven. Ter illustratie heb ik een kort code-blokje opgesteld om de essentials nog eens te doorlopen van wat er allemaal terecht moet komen in een klasse. 

1. Je klasse gaat altijd beginnen met een "**package** x": Dit is een verwijzing naar de package waarin jouw klasse zich bevind. In dit geval zit onze klasse in de package CUI.
2. **"Import"** verwijst naar bepaalde methodes/functies die onze IDE moet invoeren om diezelfde functies te kunnen uitvoeren bij het compilen. Als dit niet gebeurt zal je een foutmelding krijgen bij het compilen. Hier voeren wij bijvoorbeeld de Scanner functie in om zo invoer te kunnen vragen van de gebruiker.
3. WillekeurigGetal is een **klasse** die we hebben opgebouwd. Hierin kunnen we meerdere methodes aanmaken waarin we bepaalde zaken kunnen uitvoeren of aanpassen. Hier hebben we enkel en alleen onze "main" methode in staan.
4. De **main** methode zit binnen in onze klasse. Deze gaat worden gebruikt om het programma op te kunnen starten. Extra info: args bevat de meegegeven command-line argumenten die worden opgeslagen in een array van String-objecten. Hier moet je vooral geen rekening mee houden en dit gaan we ook niet veranderen want anders gaat ons programma niet meer goed functioneren.
5. We willen een variabele **declareren** en hier een waarde aan toewijzen. De Scanner komt later aan bod, maar voor de uitleg van declareren ga ik het voorbeeld van het willekeurigGetal gaan gebruiken. Als we binnen Java iets willen declareren MOETEN we eerst meegeven van welk primitief datatype deze variabele is. Binnen Java werken we met 
* integers (int = reële getallen die we gebruiken voor op te tellen)
* strings (String => enkel tekst + hoofdlettergevoelig!)
* double (Double => ook rekenen en wordt gebruikt voor kommagetallen)
* booleaanse waarden (Boolean => enkel true/false)
* float (float => uitbreiding op Double en wordt gebruikt voor kommagetallen met grotere waarden na de komma)
6. Als we iets willen uitprinten in onze console maken we gebruik van "System.out.println()" met tussenin de twee ronde haakjes tekst. De tekst begin en eindig je met een dubbele aanhalingsteken. We kunnen echter géén variabele meegeven zoals bij JavaScript waar we gebruik maken van ${variabeleNaam}. Hier moeten we een ander soort functie gaan gebruiken en die noemt System.out.printf(). Tussen de haakjes zijn we verplicht om minstens twee argumenten mee te geven. 
* Het eerste is de tekst die we willen dat ons programmaatje uit print. In dit geval willen we dat ons programma zegt "Jouw ingegeven getal is 'x'" waarbij x het getal is dat de gebruiker daarnet heeft ingegeven. Voor iedere variabele gebruiken we %s. 
* Onze volgende argument(en) zijn de variabelen die we willen meegeven. We gebruiken de naam van de variabele die we willen uitprinten. Als je meerdere variabelen wilt gebruiken (zoals verder in de code) kan je ze opsommen. Hou rekening met de volgorde waarin je de argumenten aanspreekt.
7. We hebben als laatste een controlestructuur. De bedoeling van if() is een vergelijking maken tussen twee waarden. Als deze voldoet gaan we een bepaalde operatie uitvoeren, als dit niet zo is gaan we een andere operatie uitvoeren. Hier gaan we in het volgende hoofdstuk verder op in.


```
package cui;

import java.util.Scanner;

public class WillekeurigGetal {

	public static void main(String[] args) {
		
		Scanner invoerVanGebruiker = new Scanner(System.in);
		
		System.out.println("Waag een gokje!");
		
		int getalGebruiker = invoerVanGebruiker.nextInt();
		invoerVanGebruiker.close();
		
		double willekeurigGetal = Math.floor(Math.random());
		
		System.out.printf("%s", getalGebruiker);
		
		if(willekeurigGetal == getalGebruiker) {
			System.out.printf("Goed gegokt!");
		} else {
			System.out.printf("Je gokte %s en het juiste antwoord was %s", getalGebruiker, willekeurigGetal);
		}

	}

}
```
# 1.5. [Scanner] Commandline customer service.

Bij programmeren met een command-line interface ga je praktisch altijd een Scanner nodig hebben. Een Scanner is zogezegd een object binnen Java die de waarde gaat bijhouden van hetgeen wat de gebruiker ingeeft. Let op: dit is géén primitief datatype. We kunnen dus niet de waarde van een scanner direct gaan gebruiken voor bijvoorbeeld een integer of een String te gaan declareren. Hiervoor moeten wij een extra methode gebruiken. Ik licht de Scanner even toe in onderstaand voorbeeld, lijntje per lijntje :

```
Scanner invoerVanGebruiker = new Scanner(System.in);
		
System.out.println("Geef een getal in: ");
		
int getalVanGebruiker = invoer.nextInt();
		
System.out.printf("Je hebt het getal %s ingegeven.");
		
```

1. Je ziet dat we eerst een Scanner-object aanmaken met een duidelijke naam. Als je een nieuw object van iets aanmaakt declareer je de variabele in de linkerhelft en gebruik je "new Scanner()" in de rechterhelft. We spreken over objecten in een later hoofdstuk, maar hier spreek je de constructor aan van Scanner die een object voor jou gaat aanmaken, later hier meer over (3. Objecten).
2. Nu gaan we een lijn uitprinten die voor de gebruiker een boodschap gaat tonen. Op deze boodschap wordt een reactie verwacht. Als je jouw programma draait zal je zien dat je opeens kan typen in de console. Je kan nu bijvoorbeeld een getal in typen en dan op enter klikken.
3. Het Scanner-object houdt nu een waarde bij. Dit is nog niet bruikbaar voor ons dus moeten we de waarde gaan ophalen vanuit dit Scanner-object. Dit doen we door in de linkerhelft ons variabele te declareren en in de rechterhelft de naam van het Scanner-object in te geven, gevolgd door ".next". Wil je heel specifiek zijn over welk datatype dat je wilt moet je bijvoorbeeld ".nextInt()" gebruiken voor een integer of ".nextLine()" voor een String.
4. Uiteindelijk kunnen we de waarde gaan uitprinten dat de gebruiker daarnet heeft ingegeven. Je kan de waarde ook direct gaan ophalen door volgende code te gebruiken: 

```
System.out.printf("Je hebt het getal %s ingegeven.", invoer.nextInt());
```

Op deze manier bespaar je ook een variabele. Let wel op dat we hier géén foutcontrole hebben toegepast. Ons programma is met andere woorden niet robuust want als de gebruiker in dit geval een stuk tekst gaat ingeven (of met andere woorden alles behalve een getal), dan gaat onze CUI-applicatie crashen en een foutmelding gaan geven. Hiervoor kunnen we een controlestructuur gebruiken om zo de gebruiker in een lus te zetten zodat hij enkel en alleen de applicatie kan afsluiten wanneer de persoon een correcte waarde heeft ingegeven.

# 2. [Controlestructuren] Loup de la loop. 

Bij Java hebben wij drie soorten structuren: sequentie- , selectie- en herhalingsstructuren.

Een **sequentiestructuur** kan je eigenlijk niet actief toepassen. Dit wordt al passief gedaan door jouw IDE. Met andere woorden gaat jouw programma in de juiste volgorde lijn per lijn het programma uitvoeren. Het programma stopt ook onmiddelijk eenmaal er een fout wordt getroffen in de code. 

**Korte opfrisser in verband met operatoren en prioriteitsregels**

Voor dit stuk ga je voornamelijk voorwaarden moeten opbouwen. Iets kan gelijk zijn, groter dan of kleiner dan zijn. Logischerwijs typen we dit niet voluit, maar gaan we gebruik maken van volgende operatoren:

'>' : groter dan + '>=' : groter dan of gelijk aan
'<' : kleiner dan + '<=' : kleiner dan of gelijk aan
'==' : is gelijk aan
'!=' : is niet gelijk aan

De prioriteitsregels zijn ook belangrijk bij het opbouwen van deze voorwaarden. De volgende prioriteit moet je weten (van boven naar onder betekent eerst gedaan -> laatst gedaan): 

> haakjes
> vermenigvuldiging, delen en modulo (rest)
> optelling en aftrekking
> operatoren groter dan en kleiner dan
> operatoren gelijk aan
> een enkel gelijkheidsteken (-> wordt binnen Java niet gebruikt als operator maar eerder om een variabele te declareren.)

**Selectiestructuren** gaan ons helpen om bepaalde paden in ons programma te gaan filteren. Zo kan je bijvoorbeeld een bepaalde actie gaan toepassen als de gebruiker een waarde in heeft gegeven die overeenstemt met of groter/kleiner is dan een andere waarde. De meest essentiële structuur is de if/else structuur. 

Bij If/Else ga je één voorwaarde meegeven. Voldoet een variabele niet aan een bepaalde voorwaarde, dan gaat het programma over gaan naar het "Else" deel. Hieronder zie je dat we bijvoorbeeld twee variabelen hebben. De variabele snelheidWagen en snelheidBeperking. In onze If-lus kijken we of de snelheid van de wagen sneller was dan de beperking. Als dit zo is dan geven we aan de gebruiker mee dat hij/zij een boete krijgt en gaan we met andere woorden alle code gaan uitvoeren die tussen de accolades staat. Is dit niet zo, dan krijgt de gebruiker het lijntje "no problemo" te zien en opnieuw ook alle code uitvoeren die tussen de accolades staan. 
Let op: we kunnen maar één keer een else gebruiken. We kunnen ons wel nog verdiepen binnen de If-lus.

Extra opmerking: Je bent niet verplicht om een else toe te voegen. Als je geen else uitvoerd zal er vanzelfsprekend wel géén alternatief worden aangeboden. In de meeste gevallen zal het wel handig zijn om toch een Else op te bouwen. 

```
int snelheidWagen = 45;
		
		final int snelheidBeperking = 50;
		
		if(snelheidWagen >= snelheidBeperking) {
			System.out.println("Je reed te snel. Hier is je boete.");
		} else {
			System.out.println("No problemo.");
		}
		
```

Stel dat we willen dat de snelheid van de wagen tussen 50 en 70 ligt, dan kunnen we onze eerste voorwaarde als volgt aanpassen:

```
		if(snelheidWagen >= 50 && snelheidWagen <= 70) {
			System.out.println("Je reed te snel. Hier is je boete.");
		} else {
			System.out.println("No problemo.");
		}
		
```

Twee '&&' tekens betekent een EN-vergelijking. Deze twee voorwaarden (>= 50 EN <= 70) moeten voldoen om een boete te kunnen meegeven. Stel dat de snelheid 75 zou zijn, dan zitten we met het probleem dat ons programma "no problemo" gaat zeggen omdat het getal wél groter is dan 50, maar niet kleiner dan 70. Stel dat je deze EN-vergelijking wilt veranderen naar een OF-vergelijking, dan moet je gebruik maken van '||'. Ons programma is nu wel onlogisch dus we moeten een voorwaarde toevoegen die gaat kijken om een operatie uit te voeren als we met een waarde zitten die groter is dan 70. Hiervoor gebruiken we een Else-If.

We voegen een extra toe aan onze huidige code. Je ziet dat er tussen onze if en onze else een extra lijn is gekomen. Else-If kijkt, net zoals de voorafgaande If, of een waarde voldoet aan de gegeven voorwaarde. Is dit zo? Dan gaat hij, net zoals de If, de code tussen de accolades gaan uitvoeren. Is dit niet zo? Dan gaan we, net zoals de If, rechtstreeks naar de Else.

```
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

```

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

De eerste die ik wil toelichten is While. Letterlijk vertaald is dit een operatie die code gaat uitvoeren zolang een voorwaarde voldaan is. Is de voorwaarde niet voldaan dan gaat de code niet uitgevoerd worden. We starten met het while keyword gevolgd door ronde haakjes met daarin de voorwaarde, daarna ga je dan twee accolades gebruiken met daartussen de code die je wilt uitvoeren in de lus.



De tweede is heel gelijkaardig aan de While en noemt Do-While. Het verschil hier in is dat je eerst sowieso de code gaat uitvoeren vooraleer je de voorwaarde gaat controleren. Dit in tegenstelling met de While die eerst kijkt of de voorwaarde voldaan is. De structuur is ook logischerwijs anders opgebouwd dan de While-lus. Eerst ga je het do-keyword gebruiken, gevolgd door de accolades met daartussen je code. Na het sluiten van de lus ga je de while-voorwaarde schrijven.



De laatste is de for-lus. Deze is wat complexer, maar laat wel enkele mogelijkheden toe. Bij de for-lus gaan we werken met drie parameters: de teller, voorwaarde en wat er veranderd nadat een lus is doorlopen. In dit voorbeeld zie je dat we een variabele 'teller' maken die we op 0 plaatsen. De teller moet kleiner zijn dan tien om de lus te doorlopen en nadat de lus is afgerond gaan we de teller verhogen met één. 





In het hoofdstuk over arrays ga je dit vaak gebruiken om de inhoud van een array te doorlopen.


# 3. [Objecten] What is an object? A miserable little pile of secrets. 

# 4. [Arrays] Programmer May Cry.


Array aanmaken + items toevoegen

Hoe een array uitladen --> For-lus + length van array

# 5. [Methodes] By all accounts, it doesn't make any sense.

# 6. [Pijlers van OO] The end of the beginning.

# 7. [Testen] Testing out the magic.

# 8. [Overerving] Baby Yoda joke

# 9. [Polymorfisme en interfaces] 

# 10. [Lambda] You mean the Half-Life symbol?

# 11. [Exception Handling] More like throwing your computer out of the window.

# 12. [GUI] Goo-ee

# 13. [Collecties] 

# 14. [Streams] Dark Souls music starts playing

# 15. [Strings] Does anyone even read the title anymore?

# 16. [Bestandverwerking] Programmer May Cry 2
