


# PRG04 opdracht 

Object Oriented Game Design in Typescript - inleveropdracht

## Deadline: Week 9 - 30 juni - 10:00 uur

Voor dit vak werk je wekelijks aan je typescript game. Deze reposistory bevat je wekelijkse updates. **Let op de deadline! Hierna kan je geen werk meer inleveren**

Je werk wordt beoordeeld volgens de cursushandleiding. Je krijgt punten voor onderstaande criteria, door elk punt individueel te *beschrijven in dit inleverdocument* én *toe te passen in je code*.

---

<br>
<br>
<Br>

## Gameplay

Toelichting gameplay
  
Je speelt Ryujin, de Mythische drakengod van de zee. De koning van het vaste land vind jou een grote bedreiging dus heeft zijn schepen op pad gestuurd jou neer te halen. Je vliegt op een vaste X waarde en kan met de pijltjestoetsen de draak van y waarde (hoogte) veranderen. De schepen komen recht op je af gevaren en nemen jou onder vuur met hun Drakenpijlen. Verder vliegen er ook magische creatures op jou af die je op kan eten. Door het eten van deze creatures word je groter en veranderd je kleur naar rood. Je bent nu groter en hebt dus een grotere hitbox waardoor het makkelijker word om schepen te raken. Word je geraakt door een van de pijlen, dan verdwijnen de magische krachten en zal je dus weer een nieuw creature moeten eten om groot en rood te worden. Boven in je scherm word op een timer aangegeven hoeveel speeltijd er nog over is. Ook word hier bijgehouden hoeveel schepen je hebt laten zinken. 
Het doel van de game is dus om in een minuut tijd zoveel mogelijk schepen te laten zinken en pijlen te ontwijken om je superkrachten te behouden. 


  

## Encapsulation

- In al je classes is encapsulation benoemd. Het is minimaal 1x gelukt om een getter en/of setter toe te passen en 
er ook gebruik van te maken. Deze toepassing heeft nut voor de uitwerking van je game.
- Je legt dit goed uit in je inleverdocument
  
  In alle classes van mijn game is encapsulation genoemd. Alle private property's/functies zijn alleen toegankelijk in de class waarin ze zijn aangemaakt. Public properties/functies zijn ook toegankelijk vanuit andere classes. De private properties die ik in mijn gameobject had staan zijn nu protected, zodat ze wel toegankelijk zijn voor de classes waaraan Gameobject word ge-extend maar niet voor de andere classes. Verder heb ik een aantal keer getters gebuikt, dit zal ik hieronder benoemen: 
  in mijn Clock class gebruik ik een getter voor de property "timer". in de Property timer laat ik namelijk een timer aflopen die je speeltijd bepaald. De reden dat ik dit heb gendaan is zodat ik in mijn gamescreen kan checken of de waarde van mijn timer kleiner is als 1 en het Eindscherm laten verschijnen zodra dit gebeurt. 
  
  Ook heb ik in mijn Ship class een getter gebruikt voor zowel de X waarde als de Y waarde. Op deze manier kan ik deze X en Y waarde ook meegeven aan de X en Y van mijn arrows in de Arrow class om mijn arrows uit de schepen te laten komen.  
  

## Composition

- Je hebt composition op een nuttige manier toegepast in je game. 
- Je legt dit goed uit in je inleverdocument.
  
  Ik heb composition goed toegepast in mijn game, zo heeft de class Game bijvoorbeeld drie objecten; het StartScreen, GamenScreen en Endscreen. Maar Gamescreen heeft op zijn plaats ook weer een hoop objecten, zo heeft gamescreen een Dragon, Creature, Ship, Arrow, Score en Clock.
  voorbeeld: in de class Game maak ik een new Gamescreen(). In de class Gamescreen maak ik een new Dragon().
  
  Dit zie je goed terug in mijn klassendiagram: 
  
  ![klassendiagram ](https://user-images.githubusercontent.com/74660474/123876734-2069c580-d93c-11eb-8c4e-6dedf6718880.png)

## Inheritance

- In je game heb je minimaal 1 x op een juiste wijze overerving toegepast. Deze toepassing heeft nut voor de 
uitwerking van je game
- Je legt dit goed uit in je inleverdocument.
  
  Inheritance gebruik je om herhaling te voorkomen. 
  Zo heb ik in mijn game bijvoorbeeld de objecten: draak, Creature, Ship en een pijl. Deze 4 hebben een aantal dingen gemeen, maar verschillen ook grotendeels. Op de gebieden waar ze overeen komen gebruiken ze alle vier dezelfde variabele en functies. Voor deze code heb ik een aparte class aangemaakt, namelijk de class: GameObject.
  De classes die deze code willen overerven extend ik dan ook naar het gameobject door bij het exporten van de class ook "extends GameObject" toe te voegen. 
  Gameobject bevat een variabele voor de x, y en een div. Ook bevat het een constructor waar het object word aangemaakt, een hitbox en een update en remove functie.
  Deze code hoef ik nu dus niet vier keer te herhalen in elke class, maar staat nu netjes in zijn eigen class en word gebruikt door deze 4 classes. 

## Game development techieken
- Je hebt alle 6 basis game development techieken toegepast in je game: HTML+CSS Basics, Game Loop, Collision 
Detection, Besturing, Timer, Object pool.
- Je benoemt elk punt kort en duidelijk in je inleverdocument.
  
  Ik heb een index.HTML bestand gemaakt waarin ik in de <game></game> met javascript mijn game maak. Het HTML bestand is dan ook wat uiteindelijk zichtbaar is op het beeldscherm. 
  Ook heb ik een .css bestand waarin ik de objecten uit mijn game styling geef. 
  Verder heb ik een Game Loop gebruikt. In de gameloop worden frames gerequest en mijn scherm geupdate bij elke nieuwe frame.
  Ook heb ik de dragon class besturing gegeven door eventlisteners toetevoegen aan de up en down keys. 
  Verder gebruik ik een Timer om aan te geven hoelang de speler nog heeft voor de game is afgelopen.
  Tot slot heb ik ook object pools gebuikt om op dezemaknier performance te verbeteren en minder oplag in beslag te nemen. 
