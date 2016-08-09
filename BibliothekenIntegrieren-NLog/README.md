# C# �bung - NLog via NuGet integrieren und verwenden

**�bungsfokus:** VisualStudio verwenden, NuGet-Pakete suchen, NLog verwenden
**Gesch�tzte �bungsdauer:** ca. 30-60 Minuten

In dieser �bung geht es darum, dass du

 - Eine Konsolenanwendung in VisualStudio erstellst
 - Dir auf [NuGet](https://www.nuget.org) eine Bibliothek suchst die dir beim Logging hilft (z.B. NLog)
 - Schaue dir mindestens 2-3 der Pakete an und bekomme so ein Gef�hl daf�r was die enthaltenen Bibliotheken anbieten und welche Unterschiede es gibt. Dabei solltest du ruhig f�r jedes Paket einmal auf die Projektseite gehen und auch dort suchen ob du schnell erste Beispiele und Dokumentation findest.
 - W�hle dir nun eine Bibliothek die dir gef�llt und die du einmal ausprobieren m�chtest. Installiere diese in deine Anwendung.
 - In der Dokumentation der Bibliothek suchst wie du ein einfaches Beispiel erstellst (z.B. das schreiben einer Log-Nachricht in eine Log-Datei)
 - Das Beispiel in deiner Anwendung umsetzt

Mit dieser �bung trainierst einerseits die praktische Verwendung der f�r dich wichtigen Tools (VisualStudio und NuGet) und �bst wie du dich in eine neue Bibliothek einarbeitest.

**WICHTIG:** Ein ganz elementarer Bestandteil einer jeden �bung (wenigstens, wenn sie dich weiterbringen soll) ist [das Reflektieren](http://clean-code-developer.de/die-grade/roter-grad/#Taeglich_reflektieren). Wenn du die �bung erledigt hast ziehe bitte eine Bilanz was die �bung dir bez�glich deiner F�higkeiten gezeigt hat. So kannst du einfach f�r dich erkunden in welchen Bereichen du noch mehr Aufgaben machen solltest und welche Bereiche du schon gut beherrschst. Du kannst gerne die Ergebnisse deiner Reflexion hier als Kommentar hinterlassen. Dann kann ich dir weitere �bungen empfehlen.

## Erweiterung der �bung f�r Fortgeschrittene

Eine sehr gute Erg�nzung dieser �bung ist die Verwendung von Git. Stelle also nach jedem Schritt sicher, dass deine Anwendung gestartet werden kann (auch wenn sie nichts macht. Wichtig ist nur, dass es keine Fehler/Warnungen vom Kompiler gibt) und mache dann einen Commit. ZUSATZ: Erstelle nicht nur einfach einen Commit, sondern �berlege/recherchiere explizit wie eine gut Commit-Message aussieht und formuliere eine entsprechende Message f�r jeden Commit.

Mit dieser Erg�nzung stellst du sicher, dass du in deiner Entwicklungsumgebung die Versionskontrolle bedienen kannst und das du alle wichtigen Informationen in eine Commit-Message bringst.

## Artikel, Videos & Links zu dieser Aufgabe

Wenn dir noch gar nicht klar ist wof�r du [NuGet](https://www.nuget.org) �berhaupt verwenden kannst, dann solltest du dir das Video [C# Tutorial Deutsch - Warum NuGet](https://youtu.be/WsvhwW2M7AY) anschauen.

Im Video [C# Tutorial Deutsch - Pakete integrieren mit NuGet](https://youtu.be/bsuEqUelxvg) zeige ich dir dann genau wie du ein Paket von NuGet in deine Anwendung integrierst.

Es gibt einige gute Artikel zum Thema was sollte in eine Commit-Message. [Dieser Artikel](https://stories.devacademy.la/how-to-use-github-like-a-proper-human-being-1a9c895c4e13#.hk1ywo6hi) geh�rt dazu. Er geht jedoch noch weiter und zeigt dir welche anderen Teile eines GitHub-Projektes du anpassen solltest, wenn dir professionelles Arbeiten wichtig ist. 

## L�sung

Hast du die Aufgabe umgesetzt, oder willst du nur ein wenig spicken? Mach es dir nicht zu einfach ;-). Du willst schlie�lich was lernen, oder?

F�hre fogende Schritte aus, wenn du keine Idee hast, wie du die �bung angehen kannst:

 - [] Erstelle eine Konsolenanwendung
 - [] Suche auf [nuget.org](https://www.nuget.org) mit dem Stichwort `Log` nach Paketen die dich beim Logging unterst�tzen.
 - [] F�r mich ist zum Beispiel der 2. Eintrag [NLog](https://www.nuget.org/packages/NLog) ansprechend. Dieses habe ich mir genauer angeschaut. (Ich habe beispielsweise [log4net](https://www.nuget.org/packages/log4net/) �bersprungen, weil ich relevante Informationen auf der [Project Site](http://logging.apache.org/log4net/) nicht direkt finden konnte)
  - [] �ber den Link *Project Site* von der [NLog Beschreibungsseite](https://www.nuget.org/packages/NLog) bin ich auf die [NLog-Seite](http://nlog-project.org) gekommen und fand es recht ansprechend.
  - [] Von der NLog-Projektseite bin ich zum [GitHub-Verzeichnis](https://github.com/NLog/NLog/) gekommen und habe dort auch das [Tutorial](https://github.com/NLog/NLog/wiki/Tutorial) gefunden.
  - [] Aus dem [Tutorial](https://github.com/NLog/NLog/wiki/Tutorial) konnte ich sehen wie ich eine Einfache Anwendung mit Logging erstelle und habe mich f�r diese Bibliothek entschieden.
 - [] Zur Installation von NLog gehst du im *Projektmappenexplorer* auf deine *Projektmappe* und w�hlst aus dem Kontextmen� *"NuGet Pakete f�r Projektmappe verwalten ..."* aus
 - [] Im sich �ffnenden Dialog w�hlst du oben links *"Durchsuchen"* aus und suchst dann nach NLog. Bei mir ist das der erste Eintrag.
 - [] Sobald du das passende Paket ausgew�hlt hast, kannst du im mittleren Teil deines Fenster ausw�hlen (Checkbox) f�r welches Projekt in deiner Projektmappe du NLog installieren m�chtest. Hier w�hlst du entweder alle Projekte aus, oder nur die in denen du NLog ben�tigst. Da ich nur ein Projekt in meiner Projektmappe habe was das einfach ;).
 - [] Nun kannst du bei *"Version"* noch eine andere Version ausw�hlen. Bei mir war die *"Aktuelleste Vorabversion"* ausgew�hlt. Diese habe ich getauscht gegen die *"Aktuelleste stabile Version"* und dann *"Installieren"* ausgew�hlt.
 - [] Nach der Installation hast du sowohl eine neue *"packages.config" in deinem Projekt wie auch einen neuen Verweis auf NLog.
 - [] Nun kannst du mit Hilfe des [Tutorials einen `Logger` anlegen](https://github.com/NLog/NLog/wiki/Tutorial#creating-loggers). Dazu brauchst du lediglich die Zeile `private static Logger logger = LogManager.GetCurrentClassLogger();` in deine Klasse `Program` schreiben und per `using` en entsprechenden `Namespace` einbinden.
 - [] Der `Logger` alleine macht jedoch noch nichts. Daher zeigt das [Tutorial im Abschnitt Log-Messages](https://github.com/NLog/NLog/wiki/Tutorial#writing-log-messages) wie das geht.
 - [] Auch jetzt wird allerdings noch immer kein Logfile erzeugt. Das liegt daran, dass NLog [eine Konfiguration ben�tigt](https://github.com/NLog/NLog/wiki/Tutorial#configuration). Dies ist jedoch schlecht im Tutorial beschrieben. Erstelle also eine Datei `NLog.config` �ber *"Hinzuf�gen -> Neues Element ..."* an deinem Projekt und nenne sie `NLog.config`.
 - [] Nun wird es verwirrend, weil trotz der Datei kein Logfile erzeugt wird beim Starten der Anwendung. Dies liegt daran, dass die Datei `NLog.config` im Ausgabeverzeichnis ben�tigt wird, w�hrend die Anwendung ausgef�hrt wird. W�hle also im *Projektmappenexplorer* die Datei `NLog.config` aus und in den Eigenschaften stellst du den Eintrag *"In Ausgabeverzeichnis kopieren"* von `Nicht kopieren` auf `Immer kopieren`.

**ERFOLG!**
Du hast nun eine Anwendung die *NLog* verwendet, ein Logfile erstellt und auch eine Nachricht darein schreibt.

Hast du nicht etwas vergessen? Denke daran, dass du nach der �bung reflektierst was dir die �bung gebracht hat und was du vielleicht beim n�chsten mal besser, anders, ... machen kannst.

Viel Spa� beim weiteren �ben, Lernen, Arbeiten oder auch einfach Feierabend machen

Jan
