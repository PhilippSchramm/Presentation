Presentation handlebars.js
==========================

##Agenda
Die Agenda der Dokumentation besteht aus folgenden Teilen:
* Vorgehensweise bei der Erstellung der Präsentation
* Voraussetzungen und Wissenswertes
* Einbinden von Handlebars
* Verwendung von TAGs
* Allgemeines Handlebars Aufbau-Beispiel
* Praxisbeispiel für Handebars 
* Informationen zur Präsentation

##Vorgehensweise bei der Erstellung der Präsentation
Zunächst wurde eine Internet-Recherche betrieben. Die Internetseite http://handlebarsjs.com/ gab zunächst umfassende Anleitung, sowie weitere Informationen über das gegebene Framework. Die Verbindung zu Mustache konnte durch http://mustache.github.io/ evaluiert werden. Die praktischen Beispiele konnten auf der Webseite http://tryhandlebarsjs.com/ ausprobiert werden.
 

##Voraussetzungen und Wissenswertes
Handlebars benötigt die Einbindung des JQuery.js Frameworks und ist eine Erweiterung von Mustache. Des Weiteren dient Handlebars zur Nutzung von “Templates”, die flexibel die jeweiligen Werte annehmen und dank sogenannter “Helper”, wie beispielsweise #each, #if, etc., auch Schleifen oder Anweisungen darstellen. Außerdem kann Handlebars für HTML, Konfigurationsdateien und Quellcode verwendet werden. Handlebars steht unter der MIT-Lizenz und ist somit für Software, deren Quelltext frei einsehbar ist, als auch für Software, deren Quelltext nicht frei einsehbar ist, verwendbar. 
Darüber hinaus kann Handlebars im Browser zum Generieren von statischen und dynamischen Seiten genutzt
oder mit Node.js auf Serverseite kompiliert werden. Auch ein Verweis mit JSON-Objekten ist möglich.


##Einbinden von Handlebars
Handlebars wird im ```<HEAD>```-Teil des HTML-Codes eingebunden. 
```
<script type='text/javascript' src="jquery-1.9.1.js"></script>
<script type='text/javascript' src="handlebars-v1.3.0.js"></script>
```

##Verwendung von TAGs
* {{ Person }} referenziert auf den Schlüssel "Person" im aktuellen Kontext
* Wenn der Schlüssel nicht gefunden wird, wird rekursiv im übergeordneten Kontext gesucht
* Durch eine dritte geschweifte Klammer wird {{{ Person }}} "HTML-escaped"
* Bei Fehlern, fehlenden Variablen oder nicht gefundenen Werten wird i.d.R. ein leerer String zurückgegeben


##Allgemeines Handlebars Aufbau-Beispiel
Die Sterne (*) im folgenden Beispiel dienen der Zeilen-Darstellung um die Leer-Zeile im Output zu verdeutlichen.
```
HTML-Template:
* {{ name }}
* {{ age }}
* {{{ company }}}

JSON:
{
"name": "Christoph",
"company": "<b>IBM</b>"
}

Output:
* Christoph
*
* IBM
```

##Praxisbeispiel für Handebars 

Im Folgenden ist der Code eines ausführlicheren Beispiels zu sehen. Hier soll mit Hilfe von Tags und und der Helper eine testweise Übersicht der Studenten der DHBW Mannheim angezeigt werden:

```
<html>
  <head>
    <meta name="author" content="Christoph Bey und Philipp Schramm">
    <title>Handlebars Demo</title>
    <!--  -->
    <!-- Integrate jQuery and Handlebars -->
	<script type='text/javascript' src="jquery-1.9.1.js"></script>
    <script type='text/javascript' src="handlebars-v1.3.0.js"></script>
  </head>
  <body>
	<div id="contentgoeshere"></div>
    
	<!-- Beginning of Handlebar-Script -> Here you can place your content! -->
    <script id="some-template" type="text/x-handlebars-template">
   	 
	 <!-- Heading with variable reference to Jason-Object -->
	 {{#university}}
   		 <h2>People from {{ this.name }} in {{ this.city }}</h2>
   	 {{/university}}
   	 
   	 <ul>
	 
	 <!-- Using the "each"-block helper -->
   	 {{#each people}}
			
			<!-- With "this." there's a reference to the properties of the current object (e.g.: name of people) -->
   			 <li><span style="font-weight:bold">{{ this.name }} </span></li>
   			 <ul>
   				 <li>Age: {{ this.age }} years</li>
   				 <li>Hometown: {{ this.city }}</li>
   				 <li><a href="http://www.facebook.com/{{ this.facebook }}">Facebook</a></li>
   			 </ul>
   	 {{/each}}
   	 </ul>
	</script>

	<!--  Beginning of Javascript! -->
	<script type="text/javascript" charset="utf-8">
  	
	<!-- Jason-Object ! -->
	var data = { people: [
      {name: "Philipp Schramm",age:"23",city:"Plankstadt",facebook:"a"},
      {name: "Christoph Bey",age:"23",city:"Olpe",facebook:"b"}],
      university:[{name:"DHBW",city:"Mannheim"}] };
 	 
	 <!-- Compiling Handlebars -->
      var source = $("#some-template").html();
	  var template = Handlebars.compile(source);
  	$("#contentgoeshere").html(template(data));
	</script>
    
  </body>
</html>
```

Wird diese HTML-Datei im Browser angezeigt, sieht dies wie folgt aus:

<img src="https://cloud.githubusercontent.com/assets/7722245/3298403/40199fc0-f601-11e3-9022-3484a5c25cc9.png" border="4" />

##Informationen zur Präsentation
Nähere Informationen über das Projekt, dessen Stärken und Konzepte können der Präsentation entnommen werden: http://philippschramm.github.io/Presentation
Die Agenda der Präsentation besteht aus folgenden Teilen:
* Was ist Handlebars.js?
* Was kann Handlebars.js?
* Einführungs-Beispiel
* Verwendung von TAGs
* Aufbau
* Beispiel
* Vor- und Nachteile
