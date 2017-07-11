# git und GitHub Grundwissen

## Ziele
* Installiertes git
* Grundwissen git
  * Was ist ein Repository?
  * Was ist ein Branch?
  * Was ist ein Commit?
  * Wie committed man?
  * Wie l�st man einen Konflikt?
  * Wie poliert man bereits bestehende Commits?
  * Was ist `git rebase -i`?
  * Was bedeutet "Amend Last Commit?"
  * Was sind die Probleme bei einer Polierung?
  * Wie halte ich mein lokales Repository aktuell?
  * Was ist ein "hard reset"?
  * Was ist ein "push -f"?
  * Was kann `git gui` grunds�tzlich?
  * Was kann `gitk` grunds�tzlich?
* Grundwissen GitHub
  * Was ist ein Fork?
  * Was ist ein Pull-Request?
  * Was bedeutet `[WIP]`?
  * Wie kommentiert man einen Pull-Request?
  * Wie reagiert man auf Review-Kommentare?
  * Wie erstellt man einen neuen Branch?
  * Wie kommt man an einen Branch von jemand anderem?
  * Was bedeutet "rebase"?
  * Was ist Markdown?
  * Wie referenziere ich Commits, Issues oder Pull-Requests?
  * Wie r�ume ich einen Pull-Request auf?

## Aufgaben

### Vorbereitung
* Umgebungsvariable `LANG` auf `en` stellen.
* Install [chocolatey](https://chocolatey.org/)
* `choco install git`
* `choco install conemu clink`
* Installiere die [AutoHotKeyScripts](https://github.com/koppor/autohotkey-scripts) installieren - insbesondere Windows+`v` f�r Konsole
* F�r Repository https://github.com/koppor/git-demonstration Schreibrecht holen

### Schritte: Grundwissen git

Szenario: Mehrere Entwickler arbeiten an einem gemeinsamen Repository

1. Auf GitHub einloggen
2. Repository https://github.com/koppor/git-demonstration forken
3. Repository lokal klonen
3. Stand mit `gitk` ansehen (`gitk --all`)
  * Lernziel: "local and remote repository" erreicht
  * Lernziel: "branch" erreicht
4. In README.md eine neue �berschrift `�berschrift` und darunter eine Zeile `Test123` einf�gen
5. Commit erstellen (`git gui`)
  * Datei dem Commit hinzuf�gen
  * Erl�uterung: Damit �ndert man den [Index] ("Staging Area")
  * Commit-Nachricht erstellen
  * Committen
  * Lernziel "Was kann `git gui` grunds�tzlich?" erreicht
6. Mit `gitk` aktuellen Stand ansehen  (`SHIFT+F5` in `gitk`)
  * Lernziel "commit" erreicht
7. Commit pushen (In `git gui` auf `Push` klicken)
7. Commit mit `gitk` ansehen (<kbd>Shift</kbd>+<kbd>F5</kbd> in `gitk`)
  * Lernziel "Was kann `gitk` grunds�tzlich?" erreicht
8. Weitere Zeile `Test 456` anf�gen
9. Commmit erstellen
10. Warten, dass jemand anderes auch in der Datei etwas ge�ndert hat (an anderer Stelle)
11. Commit pushen. Schl�gt fehl.
12. Pullen
13. Mit `gitk` aktuellen Stand ansehen  (`SHIFT+F5` in `gitk`)
14. Pushen (mit `git push`)
15. Mit `gitk` aktuellen Stand ansehen  (`SHIFT+F5` in `gitk`)
16. Zeile `Test 678` anf�gen
17. Warten, dass jemand anderes auch in der Datei etwas ge�ndert hat (an der selben Stelle)
18. Commit pushen. Schl�gt fehl.
19. Pullen
20. Es entsteht ein Konflikt: `<<<<<<< HEAD`, `=======` und `>>>>>>> b51b4334ea7dbcd39ff9d34afe6c6f0299a5b22e`
21. Mit `gitk` ansehen
22. Konflikt l�sen
  - "H�ndisch"
  - [In IntelliJ](https://www.jetbrains.com/help/idea/resolving-conflicts.html)
23. Committen
24. Pushen
  * Lernziel "Wie l�st man einen Konflikt?" erreicht
5. Ergebnis mit `gitk` ansehen
5. Neue Zeile einf�gen
5. Committen
5. Neue Zeile einf�gen
5. Committen
5. `git rebase -i`
5. Zweites `pick` durch "Squash" ersetzen
5. Speichern
5. Ergebnis mit `gitk` ansehen
  * Lernziel: "Wie poliert man bereits bestehende Commits?" erreicht
  * Lernziel: "Was ist `git rebase -i`?" erreicht
5. Pushen
1. Diskussion: Was sind die Probleme bei einer Polierung?
2. Neue Zeile einf�gen
2. Committen
2. Neue Zeile einf�gen
2. In `git gui` "Amend Last Commit" ausw�hlen
2. Zeile hinzuf�gen
2. Committen
2. Pushen
  * Lernziel "Was bedeutet "Amend Last Commit?"" erreicht
3. Pullen
  * Lernziel "Wie halte ich mein lokales Repository aktuell?" erreicht
4. In gitk auf ersten Commit gehen
4. Rechte Maustaste "Rest master branch to here"
  * `HARD` ausw�hlen
4. Datei `README.md` ansehen
  * Lernziel "Was ist ein "hard reset"?" erreicht
4. Pushen. Schl�gt fehl.
4. "force overwrite" ausw�hlen (�quivalent: `git push -f`)
  * Lernziel "Was ist ein "push -f"?" erreicht
99. Lokalen Ordner `git-demonstration` l�schen

### Schritte: Grundwissen GitHub
1. Fork von https://github.com/koppor/git-demonstration erstellen
1. Auf GitHub ansehen
  * Lernziel "Was ist ein Fork?" erreicht
1. Lokal klonen
1. `git checkout -b `generic-improvements` - neuen Branch "generic-improvements" erstellen
1. Zeile in README.md erstellen
1. Committen
1. `git push -u origin generic-improvements` - neuen Branch `generic-improvements` im `origin` erstellen, incl. [automatischem tracking](http://stackoverflow.com/q/5697750/873282).
1. Auf GitHub: Pull-Request erstellen.
  * `[WIP]` im Titel verwenden
1. (Jemand kommentiert pull request)
  * Lernziel: "Wie referenziere ich Commits, Issues oder Pull-Requests?" erreicht
1. Neue Zeile hinzuf�gen, committen und pushen
  * Lernziel: "Wie reagiert man auf Review-Kommentare?" erreicht
1. In GitHub pull request ansehen
1. `[WIP]` entfernen
1. Ggf. Pull-Request aufr�umen
  - `git rebase -i` --> alle commits zu einem zusammen fassen
  - Nicht notwendig, da Committer squashen kann
1. (Jemand akzeptiert pull request)
  - Unterschiede merge / rebase / squash erl�utern
1. In GitHub pull request ansehen
  * Lernziel "Was ist ein Pull-Request?" erreicht
  * Lernziel "Was bedeutet [WIP]?" erreicht
  * Lernziel: "Wie kommentiert man einen Pull-Request?" erreicht
  * Lernziel: "Was ist Markdown?" erreicht

(ggf. erneute Demonstration von `git rebase -i` und `git push -f`)

Folgend weitere Stichw�rter:

1. `git remote add koppor  https://github.com/koppor/git-demonstration`
1. `git fetch koppor`
  * So holt man sich alles vom Repository `koppor` lokal
  * Lernziel "Wie kommt man an einen Branch von jemand anderem?" erreicht
1. `gitk --all`
1. `git merge koppor/master`
  * So h�lt man lokalen Branch mit aktuellen �nderungen bei `koppor` aktuell
1. Alternativ: `git rebase koppor/master`
  * Lernziel "Was bedeutet "rebase"?" erreicht

  [Index]: http://www.gitguys.com/topics/whats-the-deal-with-the-git-index/
