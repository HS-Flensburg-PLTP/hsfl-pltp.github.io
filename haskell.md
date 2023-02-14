---
layout: post
title: "Arbeit mit Haskell"
---

Hier werden die Grundlagen erläutert, um mit der Programmiersprache Haskell zu arbeiten.

## Build Tool
Es wird ein Build Tool benötigt, um den Bauprozess zu managen. Es kann ausgewählt werden zwischen Cabal und Stack.

Cabal Dokumentation: [https://cabal.readthedocs.io/en/stable/](https://cabal.readthedocs.io/en/stable/)

Stack Dokumentation: [https://docs.haskellstack.org/en/stable/](https://docs.haskellstack.org/en/stable/)

## Compiler
Um Haskell-Code in Maschinencode zu konvertieren, wird ein Compiler benötigt.
Der am weitesten verbreitete Compiler ist der Glasgow Haskell Compiler (GHC).

GHC Dokumentation: [https://downloads.haskell.org/ghc/latest/docs/users_guide/](https://downloads.haskell.org/ghc/latest/docs/users_guide/)

## Installation
Die benötigten Tools, um mit Haskell arbeiten zu können, werden am leichtesten mit GHCup installiert und gemanagt.

Dafür den Schritten auf der Installationsseite folgen. Dort kann auch ein Beispielvideo für die Installation unter Windows gefunden werden.
Installationsseite: [https://www.haskell.org/ghcup/install/](https://www.haskell.org/ghcup/install/)

Nach erfolgreicher Installation kann mit dem Befehl `ghcup list` überprüft werden welche Versionen der einzelnen tools installiert sind.

Weitere Informationen zum Gebrauch von GHCup kann im offiziellen User Guide gefunden werden.
GHCup Guide: [https://www.haskell.org/ghcup/guide/](https://www.haskell.org/ghcup/guide/)

## Haskell Language Server
Der Haskell Language Server (HLS) ist ein optionales Tool, das in eine IDE eingebunden werden muss und Funktionen bereitstellt wie Code completion, lint suggestions, partial compilation.
HLS kann mit dem Befehl `ghcup install hls` installiert werden, falls dies bei der initial Installation von GHCup nicht getan wurde.

## VSCode Erweiterung / HLS Integration
Es gibt eine VSCode Erweiterung namens Haskell von den Entwicklern des HLS um diesen in VSCode zu integrieren.
Dafür den folgenden Schritten folgen:
1. Sicherstellen HLS ist installiert, falls dies nicht zutrifft, dies mit `GHCup install hls` nachholen.
2. Erweiterung installieren, dazu in VSCode `Ctrl + P` und dann `ext install haskell.haskell`

## Ormolu
Ormolu ist ein Formatierer für Haskell Quellcode. Ormolu dient dem Einhalten eines einheitlichen Formatierungsstil.

HLS hat eine eingebaute Unterstützung für Ormolu. Wird die VSCode Erweiterung genutzt, kann über die Standard-Tastenkonfiguration `Shift + Alt + F` Haskell Code mit Ormolu formatiert werden.

Ormolu kann getrennt von der Erweiterung genutzt werden. Dazu muss es mit Cabal oder Stack installiert werden mit dem Befehl `cabal install ormolu` oder `stack install ormolu`.

Der Befehl `ormolu Beispiel.hs` gibt den formatierten Output in dem Konsolenfenster aus.

Der Befehl `ormolu --mode inplace Beispiel.hs` ersetzt den Inhalt der Input-Datei mit dem formatierten Output.

Weitere Informationen können auf der Github Seite von Ormolu gefunden werden.
https://github.com/tweag/ormolu

## HLint
HLint ist ein Tool zum Vorschlagen von Code-Verbesserungen für Haskell.

Unterstützung für HLint ist im HLS enthalten, dadurch kann HLint in VSCode mittels der VSCode Erweiterung genutzt werden, ohne es separat installieren zu müssen. 

In VSCode werden betroffene Stellen durch farbliche Unterstreichung markiert. Sie werden auch unter Probleme aufgelistet.

Die Vorschläge können auf 3 Weisen in VSCode umgesetzt werden.
1. Über die betroffene Stelle im Code hovern. Es öffnet sich ein Dialog, der das Problem zeigt. Auf schnelle Problembehandlung klicken. Den gewünschten Vorschlag auswählen.
2. An die betroffene Stelle im Code klicken. Es erscheint ein Icon am linken Rand, dieses anklicken um eine Liste an Vorschlägen zu öffnen. Einen von diesen auswählen.
3. Unter Probleme den Eintrag auswählen und auf das Glühbirnen Icon klicken und die gewünschte Aktion auswählen.

HLint kann getrennt von der VSCode Erweiterung / HLS genutzt werden.
Dazu muss es mit Cabal oder Stack installiert werden mit dem Befehl `cabal install hlint` oder `stack install hlint`.
Daraufhin kann es in der Konsole verwendet werden.

Der Befehl `hlint source` gibt alle gefunden Probleme und die Vorschläge zu den Problemen aus, wobei `source` entweder eine Haskell-Datei oder ein Verzeichnis ist.

Weitere Informationen können auf der Github Seite von HLint gefunden werden.
https://github.com/ndmitchell/hlint