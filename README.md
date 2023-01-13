# Der Bachelor-/Masterarbeiten-Guide

**Dieser Guide beinhaltet lediglich Ideen und Best-Practices. Es besteht kein Anspruch auf Vollständigkeit und Korrektheit. Er dient lediglich zur Inspiration und als ungefähre Richtlinie. Nur weil Dinge hier stehen, heißt das nicht, dass sie immer gelten und stets richtig sind.** 

## Allgemein

Verwenden Sie LaTeX (nicht Word, etc.; außer Sie wissen ganz genau, was Sie da tun!)



## Zitieren

#### IEEE-Zitationsstil

In der Informatik wird oft der *IEEE-Zitationsstil* [1] verwendet. Quellen werden im Literaturverzeichnis einfach durchnummeriert. Im Text steht diese Zahl in eckigen Klammern. [2] Es ist auch möglich mehrere Quellen auf einmal zu zitieren [3,4,5]. In LaTeX erfolgt das Zitieren mittels `\cite{bibtexid}` bzw. `\cite{eine_id,eine_andere_id} ` . 

#### Geschütztes Leerzeichen vor `\cite` 

Vor einem Zitat ist ein *geschütztes Leerzeichen* sinnvoll. Dies macht man in LaTeX mit `~` und es sorgt dafür, dass an dieser Stelle kein Zeilenumbruch erfolgt. `Ein Beispiel~\cite{beispiel} könnte so aussehen. `

#### BibTeX

Literaturquellen können in einer *BibTeX*-Datei `literature.bib` verwaltet werden. Die entsprechenden Einträge lassen sich beispielsweise direkt aus Google Scholar erzeugen: Zitieren / BibTeX.

#### Zitieren von Webseiten / Fußnoten

Merkregel: Könnte eine Webseite auch ein Zeitschriftenartikel oder ein Buch sein? Wenn ja, dann gehört sie ins Literaturverzeichnis, z. B. ein Blog-Artikel, eine Dokumentation, eine Readme. Ist eine Webseite aber kein Artikel, man möchte einfach nur so drauf verweisen, ergibt es oft mehr Sinn, auf sie in einer Fußnote zu verweisen: `\footnote{\url{http://www.example.com}}` 



## Textformatierung

#### `\texttt` - Kommandos in Monospace-Schrift

Kommen im Fließtext Kommandos oder Keywords einer Programmier- oder Anfragesprache vor, werden diese in `\texttt{Monospace"=Schrift}` geschrieben.  

#### `\enquote` - Anführungszeichen

„Im Deutschen gibt es Anführungszeichen unten und Anführungszeichen oben.“ Eine Möglichkeit, diese Anführungszeichen zu verwenden, bietet das Paket `enquote`, ein Beispiel: `\enquote{Hallo!}` 

#### `\emph` - Wort hervorheben

Wird ein wichtiger *Begriff* erstmalig erwähnt, lässt er sich mittels `\emph{Begriff}` kursiv darstellen und somit dezent hervorheben.

#### Silbentrennung in Bindestrich"=Wörtern

LaTeX führt automatisch eine Silbentrennung in Wörtern durch, wenn diese am Ende einer Zeilen stehen und sofern die Sprache des Dokuments korrekt eingestellt wurde. Beinhaltet ein Wort aber einen Binde-strich, sollte man statt des Binde-striches lieber ein Anführungs"=zeichen und ein Gleichheits"=zeichen verwenden, um LaTeX zu erlauben, auch an anderen Stellen als nur beim Bindestrich selbst die Wörter zu trennen. `Text-Beispiel` würde nur in `Text-` und `Beispiel` getrennt werden; `Text"=Beispiel` würde getrennt werden in `Text-`, `Bei-` und `spiel`.

#### Silbentrennung in unbekannten Wörtern

Sollte LaTeX es nicht hinbekommen, die Silbentrennung in einem Wort korrekt durchzuführen, kann man selbst festlegen, wo das Wort getrennt werden darf: `Cal\-gon\-te`. Backslash-Bindestrich verschwindet in der Ausgabe, im Text steht also einfach: Calgonte. Aber sollte innerhalb dieses Wortes eine Silbentrennung gemacht werden, weiß LaTeX nun wo es erlaubt ist und wo nicht.   



## Grafiken

#### Vektorgrafiken

Rastergrafiken (PNG, JPEG, GIF, ...) haben den Nachteil, dass die eine begrenzte Auflösung haben und somit beim Vergrößern verpixeln. Außerdem lässt sich Text, der sich in diesen Grafiken befindet nicht durchsuchen oder markieren. Daher sollten bevorzugt *Vektorgrafiken* erstellt und verwendet werden.

Vektorgrafiken lassen sich mit vielen Softwareprogrammen erstellen: PowerPoint, Libreoffice Draw, Microsoft Visio, draw.io, Canva, Adobe Illustrator, Gravit Designer, Inkscape, ...

Wichtig ist, dass man die Datei als *PDF* exportiert. Die Grafik im PDF-Format lässt sich in LaTeX genau so einfügen wie JPG- oder PNG-Bilder.

Sollte die Grafik nach dem PDF-Export nicht die richtige Leinwandgröße haben (weiße Fläche links, rechts, oben, unten), kann mit einer PDF-Crop-Software (z. B. `krop` für Linux) der gewünschte Bildbereich ausgeschnitten werden.

#### Abbildungen nummerieren und Titel geben

Jede Abbildung erhält eine Nummer und einen Abbildungstitel. Im Text lässt sich mittels `Abbildung \ref{fig:uml_diagramm}` auf die Abbildung verweisen. Es bietet sich an, Abbildungen ein `label{fig:...}` zu geben, um auf sie verweisen zu können. Analog kann auch auf Kapitel, Abschnitte, usw. verwiesen werden, hier bietet sich `\label{sec:...}` an.

#### Farbe vs. Schwarz-Weiß

Was auch genau so gut in Schwarz-Weiß geht und gut aussieht, kann man ruhig in Schwarz-Weiß machen. Dann müssen die entsprechenden Seiten nicht farbig ausgedruckt werden.



## Programmcode

#### Code nicht als Screenshots

Programmcode gehört nicht in Grafiken. Programmcode kann mittels Listings in LaTeX eingefügt werden. Hier ist meist eine `Monospace-Formatierung` sinnvoll. Das Paket `minted` ist ein bisschen nervig einzurichten, bietet aber sogar Syntax-Highlighting. Für die Abschlussarbeit bietet sich der Stil `bw` an (Black-White), damit sie nicht farbig gedruckt werden muss.



## Schreibstil

#### Keine direkten Fragen stellen

Was ist daran schlecht? Naja, das ist nicht der Stil, in der man eine Abschlussarbeit schreibt. Keine Fragezeichen? Ja, keine Fragezeichen.

#### Kein Du, kein Sie

In einer Abschlussarbeit redest du nicht direkt mit dem Leser. Weder Siezen Sie ihn noch bist du mit ihm per-Du. 

#### Kein Ich

Ich weise darauf hin, dass man die erste Person Singular vermeiden sollte. Wir haben uns dafür entschieden, im Notfall die erste Person Plural zu verwenden. Meist geht es aber auch komplett ohne Ich und Wir.



## Typische Fehler im Deutschen

#### Komma vor zu + Infinitiv

Vielen fällt es schwer, Kommas korrekt *zu* setzen. Anstatt einfach *zu* raten, ist hier ein Tipp: Wenn der eine Teil des Satzes "zu" und ein Verb im Infinitiv beinhaltet, werden die beiden Satzteil mit einem Komma getrennt.

#### Bindestriche

Wörter stehen im Deutschen nicht einfach so hintereinander, getrennt mit Leer Zeichen. Sie werden entweder aneinander geschrieben oder man verwendet den Bindestrich: Leerzeichen, Browser-Plugin, E-Mail-Programm, Grundlagen-Kapitel, Grundlagenkapitel, Katzenvideos, Handy-Anwendung, Datenbank-Verbindung, Datenbankverbindung, Datenbank-Management-System, Datenbankmanagementsystem.

Merkregel: Werden zwei Nomen mit einem Leerzeichen getrennt, betont man das zweite Wort ("Audi *Quattro*"), trennt man sie mit Bindestrich, betont man das erste Wort ("*Audi*-Werkstatt").

#### Englische Wörter im deutschen Text

Wenn english Words im deutschen Text vorkommen, ist das kein Problem. Es ist nicht nötig, jeden Term ins Deutsche zu übersetzen, wenn das englische Keyword das Gebräuchlichere ist. Wichtig ist nur, dass diese fremdsprachigen Wörter dann trotzdem der deutschen Grammatik folgen: Nomen groß, Verben und Adjektive klein, Bindestriche setzen, usw.

#### n und m

I**n** diese**m** Satz stehen zwei Wörter, die auf n und m enden und wir verwenden den Dativ: In wem oder was? In diesem Satz. I**n** diese**m** Beispiel ist es so, i**m** andere**n** Beispiel andersrum.

#### Wörterbuch und Google

Ein Nachschlagen im Wörterbuch, z. B. Wiktionary hilft, um die korrekte Schreibweise und die richtigen Grammatikformen von Wörtern zu erfahren. Auch über Google-Suchen erfährt man oft korrekte Schreibweisen, dabei landet man oft auf Seiten wie korrekturen.de, die die falsche und richtige Schreibweise gegenüberstellen.

#### Satz beenden, bevor der Nebensatz losgeht

Man könnte den Satz auch, nachdem der Nebensatz losgeht, beenden. Es ist jedoch besser lesbar, den Nebensatz erst zu beginnen, wenn der Hauptsatz zuende ist. Andernfalls müsste man den Hauptsatz, der in diesem Fall viel kürzer ist als der Nebensatz, zerstückeln. 

#### Abkürzungen

Abkürzungen sollten am besten nur verwendet werden, wenn man in der Praxis viel öfters von der Abkürzung redet als von dem ausgeschriebenen Begriff. Manche Abkürzungen sollte man in Klammern beim ersten Auftreten einmal ausschreiben: Das verwendete Format ist JSON (Javascript Object Notation). Andersrum geht auch: Die Javascript Object Notation (JSON) wird dafür verwendet. Manche Abkürzungen muss man nicht erklären und kann sie einfach so stehen lassen: DVD, PDF, JPEG, PNG, GIF, JDBC, PHP, ...

Wenn der Begriff hinter der Abkürzung noch nicht zuernde ist, kommen die Klammern erst nach dem gesammten Begriff: JSON-Format (Javascript Object Notation), ETL-Prozess (Extract, Transform, Load).

#### z. B. und d. h. mit geschütztem Leerzeichen

Abkürzungen, die mehrere Wörter abkürzen beinhalten in der Regel im Deutschen ein Leerzeichen, z. B. das hier. D. h., dass hinter dem Punkt nicht einfach der nächste Buchstabe kommt. Am besten sollte man sowieso soweit es geht auf die Abkürzungen verzichten und sie ausschreiben. Wenn man sie aber doch verwendet, ist auf das Leerzeichen zu achten. Dieses Leerzeichen sollte ein geschütztes Leerzeichen sein, damit ein Zeilenumbruch nicht zwischen "z." und "B." unternommen wird: `z.~B.` 



## Typical Mistakes in English Texts

#### Comma after introductory subordinate clauses

As this in an introductory subordinate clause, it is separated from the main clause by a comma. In the previous section, basic concepts were introduced. In Figure 4, the black dot stands for the client. Hence, you now know one comma rule. E.g., here also is a comma.

#### Hyphens

When you have more than two nouns, the default connection is from right to left. "Big data file" is a data file which is big. If you want a different meaning, use hyphens: "big-data file" is a file that contains big data.

The same holds for other words than nouns: "long-running query" is a query that is long running. "large file size" is a file size which is large. "large-file size" is the size of a large file (in this case you would better write: the size of a large file ;-))

#### Heading Capitalization

Section headings and titles of figures which are no full sentences (e.g., Figure 1 - Sushi Restaurant) follow the rules of hading capitalization: nouns, pronouns, verbs, adectives and adverbs are capitalized. The first word is always capitalized: Transforming Data Rows into Graph Nodes and Edges

#### Capitalize Names

Names of people, cities, and countries are capitalized: Peter, Berlin, Germany. But also names of figures, tables, and sections are capitalized: In Section 5, we evaluated our approach. Figure 2 shows a dolphin. 

#### Oxford Comma

Apples, Banana, and Strawberries. Use the oxford comma before the words "and" and "or" when your list contains more than two elements. 





   





  

 

