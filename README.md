# Cup Of Java
Hallo! Ik ben Dylan Cluyse. Momenteel student aan Hogeschool Gent. In deze Github repo wil ik vooral de basis voorleggen van programmeren met Java. Deze leerinhoud is gebaseerd op basis van het curriculum 2020-2021. Tijdens je eerste jaar zal je in het vak OOSD1 ook een deel ontwerpen krijgen. Dit komt aan bod in een andere repository.

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

# 2. [Controlestructuren] Loup de la loop. 

# 3. [Objecten] What is an object? A miserable little pile of secrets. 

# 4. [Arrays] Programmer May Cry.

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
