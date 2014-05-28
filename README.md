Presentation
============

#Informationen
Nähere Informationen über das Projekt, dessen Stärken und Konzepte können der Präsentation entnommen werden: http://philippschramm.github.io/Presentation
Die Agenda der Präsentation besteht aus folgenden Teilen:
* Was ist Handlebars.js?
* Was kann Handlebars.js?
* Einführungs-Beispiel
* Verwendung von TAGs
* Aufbau
* Beispiel
* Vor- und Nachteile
 

#Voraussetzungen und Wissenswertes
Handlebars benötigt die Einbindung des JQuery.js Frameworks und ist eine Erweiterung von Mustache. Des Weiteren dient Handlebars zur Nutzung von “Templates”. Diese sollen flexibel die jeweiligen Werte annehmen und können dank der sogenannten “Helper”, wie beispielsweise #each, #if, etc., auch Schleifen und Anweisungen darstellen.

#Vorgehensweise bei der Erstellung der Präsenation
Zunächst wurde eine Internet-Recherche betrieben. Die Internetseite http://handlebarsjs.com/ gab zunächst umfassende Anleitung, sowie weitere Informationen über das gegebene Framework. Die Verbindung zu Mustache konnte durch http://mustache.github.io/ evaluiert werden. Die praktischen Beispiele konnten auf der Webseite http://tryhandlebarsjs.com/ ausporbiert werden.

#Einbinden von Handlebars
Handlebars wird im <HEAD>-Teil des HTML-Codes eingebunden. Ein ausführlicheres Beispiel befindet sich hier: https://github.com/PhilippSchramm/Presentation/blob/gh-pages/Demo.html.

```
<script type='text/javascript' src="jquery-1.9.1.js"></script>
<script type='text/javascript' src="handlebars-v1.3.0.js"></script>
```

#Allgemeines Handlebars Aufbau-Beispiel
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

#Ein Beispiel, wie man es in der Praxis finden könnte:
Aus Gründen der Übersichtlichkeit und des Platzes soll hier auf die Präsentation verwiesen werden, indem ein größeres Beispiel zu finden ist:
http://philippschramm.github.io/Presentation
