# Google Dataset Search: Die perfekte Suchmaschine für Datensätze?
Jeden Tag werden neue Datensätze im Web veröffentlicht. Nicht erst seit der weltweiten [Covid-19](https://en.wikipedia.org/wiki/COVID-19) Pandemie merkt man, wie wichtig diese Datensätze für Unternehmen, Regierungen aber auch den wissenschaftlichen Diskurs sind. Doch wie macht man diese Datensätze im globalen Web sichtbar und für Wissenschaft zitierbar? Für die Literaturrecherche wissenschaftlicher Dokumente wurde 2004 die erfolgreiche Suchmaschine [Google Scholar](https://scholar.google.com/intl/de/scholar/about.html) von Google eingeführt. [Google Dataset Search](https://datasetsearch.research.google.com/) soll diese Funktion in gleicher Weise für Datensätze implementieren. Google selbst bezeichnet ihre neue Suchmaschine als „Google Scholar for data”. Im September 2018 startete die Betaversion von Dataset Search, die das gesamte Web nach Millionen von Datensätzen durchsucht. Dabei wendet Google [schema.org](https://schema.org/) an, um die Metadaten der Datensätze zu strukturieren.

## Schema.org für die Struktur der Metadaten
[Schema.org](https://schema.org/) ist ein Initiative für ein generalisiertes Schema für strukturierte Daten im Web, dabei unterstützt schema.org die Datenformate RDFa, Microdata und JSON-LD. Es wurde in einem Gemeinschaftsprojekt der Suchmaschinenanbieter Google, Microsoft, Yahoo und Yadex entwickelt. Durch dieses Strukturierung werden Daten für Maschinen lesbar und die Semantik wird einheitlich, dadurch kann der Google Algorithmus zum Beispiel den Inhalt des Datensatzes analysieren und einordnen. Schema.org ist hierarchisch aufgebaut. Der oberste Typ ist „Thing“. Er besitzt mehrere Subtypen, wie „Action“ oder „Event“. Diese können wiederum über mehrere Subtypen verfügen. Der Pfad für den Typ „Dataset" ist folgender: „Thing-CreativeWork-Dataset“. Der Typ [schmema.org/Dataset](https://schema.org/Dataset) hat mehre Eigenschaften. Einem Datensatz werden zum Beispiel ein Titel und der Name des Providers hinzugefügt. Jeder Datensatz in dem Korpus von Dataset Search muss einen Titel und eine Beschreibung, welche in den Metadaten gespeichert sind, besitzen.

## Aufbau der Suchmaschine

Die Dataset Search basiert auf dem Konzept, dass die Provider zu ihren Datensätzen in  der von schema.org entwickelten Ontologie Metadaten hinzufügen. Je mehr Metadaten zu einem Datensatz hinzugefügt werden, desto besser wird eine Suchanfragen repliziert. Doch sind die Metadaten der Datensätze häufig unvollständig und vage. Deshalb abstrahiert Google einige Metadaten, wie zum Beispiel die Eigenschaften „publisher“ und „creater“. Sie werden zu „provided by“ zusammengefasst. Häufig existieren die gleichen Datensätze in unterschiedlichen Repositorien. Dataset Search identifiziert die Replikate und fügt sie zu einem Datensatz zusammen. 

<p align = "center"> 
    <img src = image1.png>
</p>

*Source: Burgess, M., & Noy, N. (September, 2018). Building Google Dataset Search and Fostering an Open Data Ecosystem. Google AI Blog.*

### Mit Hilfe von Digital Object Identifier den Datenpool sortieren
Eine Möglichkeit ein Duplikat zu erkennen, ist ein Vergleich über [Digital Object Identifier (DOIs)](https://en.wikipedia.org/wiki/Digital_object_identifier). Ein DOI ist ein eindeutiger Identifikator für digitale Objekte. Anhand des Identifikators kann aus einer zentralen Datenbank der URL, der dem Objekt zugewiesen ist, abgefragt werden. Somit werden Metadaten über das referenzierte Objekt gespeichert und, wodurch das Problem [„link death"](https://en.wikipedia.org/wiki/Link_rot) lösen. 

### Abgleich mit Google Knowledge Graph 
Der [Google Knowledge Graph](https://blog.google/products/search/introducing-knowledge-graph-things-not/) ist ein Wissensgraph mit über fünf Milliarden Entitäten, welcher Informationen verlinkt und Beziehungen zwischen Objekten bildet. Dataset Search verlinkt die Informationen aus den Metadaten der Datensätze mit den Entitäten und Fakten aus dem Wissensgraphen. Dadurch werden Suchanfragen der Nutzer optimiert. Es entsteht beispielsweise ein Cluster von Akronymen und Synonymen bei Suchanfragen.

### Verknüpfung mit Google Scholar
Mit [Google Scholar](https://scholar.google.com/intl/de/scholar/about.html) weiß die Suchmaschine, welche Datensätze in Publikationen referenzierte werden und somit findet Google den Bekanntheitsgrad des jeweiligen Datensatzes heraus. Jedoch werden Datensätze nur sehr selten und uneinheitlich zitiert. 


Die Metadaten aus dem Korpus an Datensätzen werden indexiert. Mit Hilfe der Antworten auf die Suchanfragen von Nutzern eruiert der Algorithmus die passenden Ergebnisse. Der Nutzer muss nur ein Keyword nennen, um eine beliebig große Anzahl an Suchergebnissen zu diversen Themen zu erhalten. Die meistgenannten Suchbegriffe sind „education“, „weather“, „cancer“, „crime“ und „soccer“.

## Wachstum der datenbasierten Suchmaschine 
Der Korpus der Metadaten in Google Dataset Search expandiert stetig. Nach einer zweijährigen Testphase veröffentlichte Google im Januar 2020 die Vollversion. Der Korpus an Datensätzen ist sehr dynamisch. Es werden ständig Daten gelöscht, aktualisiert oder hinzugefügt. Dabei erreichte die Suchmaschine folgende Ziele:
+ Beinhaltet mehr als 31 Millionen Datensätze
+ Datensätze von mehr als 4.600 Domains
+ Mehr als 3 Millionen Datensätze haben DOIs (ca. 11%)
+ 10 Millionen Datensätze wurde innerhalb eines Jahres aktualisiert (ca. 30%)
+ 12 Millionen Datensätze stellen einen Downloadlink zur Verfügung (ca. 44%)

<p align = "center"> 
    <img src = image2.png>
</p>

*Source: Benjelloun, O., Chen, S., & Noy, N. (2020, November). Google dataset search by the numbers. In International Semantic Web Conference (pp. 667-682). Springer, Cham.*

## Keine perfekte Suchmaschine
Dataset Search soll die Zukunft der Datensuche revolutionieren, doch weist sie noch einige Probleme auf. Damit Suchanfragen möglichst viele und genaue Treffer ergeben, müssen die Datensätze viele Metadaten in dem Format von schema.org besitzen. Allerdings veröffentlichen viele Provider kaum Metadaten zu ihren Datensätzen. Eine gute Darstellung des Datensatzes in den Metadaten ist essenziel für die Auffindbarkeit. Eine Beschreibung (Property :: [description](https://schema.org/description)) und Titel (Property :: [name](https://schema.org/name)) ist in dem Korpus von Google Dataset Search erforderlich. Die Eigenschaft vom Datendownload werden in der Ontologie von schema.org mit dem Schlüsselwort [„distribution“](https://schema.org/distribution) angegeben. Dabei fällt auf, dass nur 44 % der Datensätze einen Download bereitstellt. Ein weiteres Problem der Suchmaschine sind die fehlenden Lizenzinformationen. Ohne eine Lizenz können die Nutzer die Datensätze nicht oder nur eingeschränkt nutzen. Weniger als 1 % der Datensätze kommen aus dem [Semantic Web](https://en.wikipedia.org/wiki/Semantic_Web). Dabei ist nicht das Problem, dass es zu wenig Datensätze gibt, sondern die Datensätze werden in der Ontologie von  schema.org nicht beschrieben.

<p align = "center"> 
    <img src = image3.png>
</p>
Table: Percentage of datasets with specific properties. Column 2 lists the source predicates for each property (schema.org namespace as so# and the DCAT namespace as dct#).


*Source: Benjelloun, O., Chen, S., & Noy, N. (2020, November). Google dataset search by the numbers. In International Semantic Web Conference (pp. 667-682). Springer, Cham.*


## Wie man Dataset Search verbessert
Die Tabelle visualisiert das große Problem von fehlenden Metadaten zu vielen Eigenschaften der Datensätze, unter anderem zu „data download" und „license". Es ist die Aufgabe von Google diese Lücke zu schließen um eine bessere Suche zu realisieren. In dem Paper „[Google Dataset Search by the Numbers](https://research.google/pubs/pub49385/)" werden zur Lösung folgende Optionen erläutert:

- Verbesserung der Technik zu automatisierter Bereinigung, Normalisierung und Abstimmung von Metadaten
- Einsetzen von Google-Tools, wie die [Search Console](https://search.google.com/search-console/about), welche den Provider über die Unvollständigkeit von Metadaten informiert
- Entwicklung interaktiver Tools zur Erstellung und Validierung von Metadaten, die in gängigen [Content Management Systemen](https://en.wikipedia.org/wiki/Content_management_system) zur Verwaltung von Datensätzen oder in Hosting-Plattformen      integriert werden
- [Crowdsourcing](https://en.wikipedia.org/wiki/Crowdsourcing): Die Nutzer korrigieren oder weisen selbst auf die fehlenden Metadaten hin
  -  Funktion könnte Dataset Search zur Verfügung stellen und an den Herausgeber des Datensatzes weiterleiten

Viele Datensätze im Web sind Duplikate. Duplikate sind jedoch ein Problem für eine Suchmaschine, da sich Suchergebnisse doppeln. Mit data cleaning versucht Google dieses Problem zu lösen. Wie kann man das System verbessern? Die Einführung von Digital Object Identifier für Datensätze löst mehrere Probleme. Durch DOIs werden die Datensätze für WissenschaftlerIn zitierbar und Duplikate werden erkannt. Google sollte die Vergabe von DOIs für Datensätze stärker unterstützen und die Provider motivieren ihre Datensätze von Organisation, wie [DataCite](https://datacite.org/value.html), registrieren zu lassen.

## Fazit
Datensätze sollen ein erstklassiger Bestandteil des wissenschaftlichen Diskurses werden. Eine Suchmaschine für Datensätze ist deshalb längst überfällig. Dataset Search nutzt die internen Systeme, wie zum Beispiel den Google Knowledge Graph, um die Suche für die Nutzer zu optimieren. Dennoch sind viele Metadaten von Datensätzen unvollständig deshalb ist es die Aufgabe von Google weitere Werkzeuge zu entwickeln, die die Bereitstellung von Metadaten und die Nutzung von persistenten Identifikatoren der Provider förderen. Ergänzend sollte die Gemeinschaft des Semantik Webs ihren Datensätzen semantische Metadaten hinzufügen.
