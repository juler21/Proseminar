# Google Dataset Search: Die perfekte Suchmaschine für Datensätze?
Jeden Tag werden neue Datensätze im Web veröffentlicht. Nicht erst seit der weltweiten [Covid-19](https://en.wikipedia.org/wiki/COVID-19) Pandemie merkt man, wie wichtig diese Datensätze für Unternehmen, Regierungen aber auch WissenschaftlerIn sind. Doch wie macht man diese Datensätze im globalen Web sichtbar und für WissenschaftlerIn zitierbar. Für die Literaturrecherche wissenschaftlicher Dokumente wurde von Google im Jahr 2004 die erfolgreiche Suchmaschine [Google Scholar](https://scholar.google.com/intl/de/scholar/about.html) eingeführt. [Google Dataset Search](https://datasetsearch.research.google.com/) soll diese Funktion ex aequo für Datensätze implementieren. Google selbst bezeichnet ihre neue Suchmaschine als „Google Scholar for data”. Im September 2018 startete die Betaversion von Dataset Search, die das gesamte Web nach Millionen von Datensätzen durchsucht. Dabei benutzt Google [schema.org](https://schema.org/) um die Metadaten der Datensätze zu strukturieren.

## Schema.org für die Struktur der Metadaten
[Schema.org](https://schema.org/) ist eine mark-up language für die Gliederung und Formatierung von Daten auf Websites, dabei unterstützt schema.org die Datenformate RDFa, Microdata und JSON-LD. Es wurde in einem Gemeinschaftsprojekt der Suchmaschinenanbieter Google, Microsoft, Yahoo und Yadex entwickelt. Dadurch werden Daten für Maschinen lesbar und die Semantik wird einheitlich, so kann der Google Algorithmus zum Beispiel erkennen, dass es sich bei dem Datensatz zum Beispiel um eine Veranstaltung handelt. Schema.org ist hierarchisch aufgebaut. Der oberste Typ ist „Thing“. Er besitzt mehrere Subtypen, wie „Action“ oder „Event“. Dies können wiederum mehrere Subtypen haben. Der Pfad für ein Musikkonzert wäre zum Beispiel folgender: „Thing-Event-MusicEvent“. Der Typ [schmema.org/Dataset](https://schema.org/Dataset) hat mehre Eigenschaften, so werden in schema.org einem Datensatz zum Beispiel einen Titel und der Name des Providers hinzugefügt. Jeder Datensatz in Dataset Search hat einen Titel und eine Beschreibung in den Metadaten gespeichert.

## Aufbau der Suchmaschine

Die Dataset Search basiert auf dem Konzept, dass die Provider zu ihren Datensätzen in schema.org Metadateneigenschaften hinzufügen. Je mehr Metadaten ein Datensatz hat, desto besser kann er bei Suchanfragen gefunden werden. Doch sind die Metadaten zu den Datensätzen oft unvollständig und vage. Deshalb abstrahiert Google einige Metadaten, so werden zum Beispiel die Eigenschaften „publisher“ und „creater“ zu „provided by“ zusammengefasst. Häufig existieren die gleichen Datensätze in unterschiedlichen Repositorien. Dataset Search identifiziert die Replica und fügt sie zu einem Datensatz zusammen. 

<p align = "center"> 
    <img src = image1.png>
</p>

*Source: Burgess, M., & Noy, N. (September, 2018). Building Google Dataset Search and Fostering an Open Data Ecosystem. Google AI Blog.*

### Mit Hilfe von Digital Object Identifier den Datenpool sortieren
Eine Möglichkeit ein Duplikat zu erkennen, ist ein Vergleich über [Digital Object Identifier (DOI)](https://en.wikipedia.org/wiki/Digital_object_identifier). Ein DOI ist ein eindeutiger Identifikator für digitale Objekte. Anhand des Identifikators kann aus einer zentralen Datenbank der URL, der dem Objekt zugewiesen ist, abgefragt werden. Somit werden Metadaten über das referenzierte Objekt gespeichert und dadurch soll das Problem [„link death"](https://en.wikipedia.org/wiki/Link_rot) lösen. 

### Abgleich mit Google Knowledge Graph 
Der [Google Knowledge Graph](https://blog.google/products/search/introducing-knowledge-graph-things-not/) ist ein Wissensgraph mit über fünf Milliarden Entitäten, welcher Informationen verlinkt und Beziehungen zwischen Objekten bildet. Dataset Search verlinkt die Informationen aus den Metadaten der Datensätze mit den Entitäten und Fakten aus dem Wissensgraphen. Dadurch werden Suchanfragen der Nutzer optimiert, so entsteht beispielsweise ein Cluster von Akronymen und Synonymen bei Suchanfragen.

### Verknüpfung mit Google Scholar
Mit [Google Scholar](https://en.wikipedia.org/wiki/Google_Scholar) weiß die Suchmaschine, welche Datensätze in Publikationen referenzierte werden und somit findet Google den Bekanntheitsgrad des jeweiligen Datensatzes heraus. Jedoch werden Datensätze nur sehr selten zitiert und uneinheitlich zitiert. 


Die Metadaten aus dem Korpus an Datensätzen werden indexiert. Mit den Antworten auf die Suchanfragen der Nutzer findet der Algorithmus heraus, welche Ergebnisse am besten passen. Der Nutzer muss nur ein Keyword nennen und er findet Suchergebnisse zu allen möglichen Themen. Die meistgenannten Suchbegriffe sind zum Beispiel „education“, „weather“, „cancer“, „crime“ und „soccer“.

## Wachstum der datenbasierten Suchmaschinen 
Der Korpus der Metadaten in Google Dataset Search expandiert stetig. Nach einer zweijährigen Testphase veröffentlichte Google im Januar 2020 die Vollversion. Dabei erreichte die Suchmaschine folgende Ziele:
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
Dataset Search soll die Zukunft der Datensuche revolutionieren, doch weist sie noch einige Probleme auf. Damit Suchanfragen erfolgreich sind und möglichst viele und genauer Treffer ergeben, müssen die Datensätze viele Metadaten in schema.org haben. Viele Provider veröffentlichen jedoch wenig Metadaten zu ihren Datensätzen. Eine gute Darstellung des Datensatzes in den Metadaten ist elementar für die Auffindbarkeit. Nur eine Beschreibung (Property :: [description](https://schema.org/description) und Titel (Property :: [name](https://schema.org/name)) muss jeder Datensatz in der Google Dataset Search haben. Die Eigenschaft vom Datendownload werden in schema.org mit dem Schlüsselwort [„distribution“](https://schema.org/distribution) angegeben. Dabei fällt auf, dass nur etwa 44 % der Datensätze einen Download bereitstellt. Ein weiteres Problem der Suchmaschine sind die fehlenden Lizenzinformationen. Ohne eine Lizenz können die Nutzer die Datensätze nicht oder nur eingeschränkt nutzen. Weniger als 1 % in dem Korpus sind Datensätze kommt aus dem [Semantic Web](https://en.wikipedia.org/wiki/Semantic_Web). Dabei ist nicht das Problem, dass es zu wenig Datensätze gibt, sondern die Datensätze werden in schema.org nicht beschrieben.

<p align = "center"> 
    <img src = image3.png>
</p>
Table: Percentage of datasets with specific properties. Column 2 lists the source predicates for each property (schema.org namespace as so# and the DCAT namespace as dct#).


*Source: Benjelloun, O., Chen, S., & Noy, N. (2020, November). Google dataset search by the numbers. In International Semantic Web Conference (pp. 667-682). Springer, Cham.*


## Wie man Dataset Search verbessert
-	Verbesserung der Technik zu automatisierter Bereinigung, Normalisierung und Abstimmung von Metadaten.
-	Man kann die Eigentümer von Datensätzen wissen lassen, dass ihre Datensatz-Metadaten verbessert werden können. Google-Tools, wie die Search Console und das Tool  zum Testen strukturierter Daten zeigen bereits einige dieser Probleme auf.
-	Man könnte auch die Entwicklung interaktiver Tools zur Erstellung und Validierung von Metadaten zu erstellen und zu validieren, die in gängige CMS zur Verwaltung von Datensätzen oder in Hosting-Plattformen integriert werden könnten.
-	Crowdsourcing Die Nutzer von Datensätze korrigiere oder weisen selbst auf die fehlenden Metadaten hin. Diese Funktion könnte Dataset Search zur Verfügung stellen und an den Herausgeber des Datensatzes weiterleiten.

Viele Datensätze sind Duplikate oder von anderen Datensätzen abgeleitet. Abgeleitete Datensätze sind vergleichbar mit Zitaten von Arbeiten. Schema.org bietet Eigenschaften zum Beschreiben dieser Abhängigkeiten so#sameAS oder so#isBasedOn. Nur werden diese kaum genutzt. Wie kann man das verbessern: 

-	Duplikate werden bereits erkannt.
-	Es wäre ein großer Nutzen die Verwendung von schema.org bei der Zitierung von Datensätzen vorzuschreiben.

## Conclusio
Dennoch lassen die Metadaten noch viel zu wünschen übrig, wenn die Daten wirklich zu einem erstklassigen Bestandteil des wissenschaftlichen Diskurses werden sollen: Wir brauchen Werkzeuge, die sicherstellen, dass die Metadaten und Mechanismen, die die Verwendung von Lizenzinformationen für Daten und persistente Identifikatoren zu fördern. Und die Semantic-Web-Gemeinschaft muss ihr eigenes Hundefutter essen, indem sie ihren Datensätzen semantische Metadaten hinzufügt.


