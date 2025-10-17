# Templates
Es gibt sowohl den Basis-Plugin **Templates** als auch den Community-Plugin **Templater** - Diese sollten genutzt werden um wichtige Eckdaten am Anfang aller Notizen einheitlich zu strukturieren.

Wichtige Templates, die standardmäßig durch `alt + N` aufgerufen werden, sind:
- [[Vorlesungsnotizen]] für Live-Mitschriften aus Vorlesungen
	- `date` mit dem Datum der Vorlesung ausfüllen
	- `tags` ist entweder `TI` , `AFI` , `DS` oder `PROGRA` d.h. das Modul
	- `status` ist bedeutet, ob die Notiz schon zu Lernzetteln verarbeitet wurde. `rot`= noch gar nicht ; `gelb` = so halb ; `grün` = vollständig
	- `Vorlesungsfolien` verweißt als Obsidian Link auf das `.pdf` mit den Vorlesungsfolien inkl. Seitenangaben: z.B. [[I1_Organisation.pdf#page=8]]
	- `Skriptfolien` funktioniert genau wie `Vorlesungsfolien`, nur dass hier auf die relevanten Seiten des Vorlesungsskripts verwiesen wird. (DS hat z.B. beides.)
- [[Lernzettel]] für Aufbereitete Übersichten zu einzelnen Inhalten
	- `tags` können ***beliebig viele*** der Modulabkürzungen sein - Einfach alle Module auflisten, in denen das Thema behandelt wurde.
	- `status` ist wieder `rot`, `gelb` oder `grün` je nachdem wie vollständig / gut / übersichtlich / fertig der Lernzettel schon ist

# Definitionen
Definitionen von neuen Begriffen, Konzepten und Co. werden mit einem "Callout" als Block markiert.

Syntax dafür:
```
> [!def] Mensch
> Ein Mensch ist ein federloser Zweibeiner.
> lorem ipsum
```

Dies erzeugt:
> [!def] Mensch
> Ein Mensch ist ein federloser Zweibeiner.
> lorem ipsum


