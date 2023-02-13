---
layout: post
title: "Arbeit mit Haskell"
---

Hier werden die Grundlagen erläutert, um mit der Programmiersprache Haskell zuarbeiten.

## Build Tool
Es wird ein build tool benötigt, um den build process zu managen. Es kann ausgewählt werden zwischen Cabal und Stack.
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

Nach erfolgreicher Installation kann mit dem Befehl `ghcup list` angezeigt werden welche Versionen der einzelnen tools installiert sind.

Weitere Informationen zum Gebrauch von GHCup kann im offiziellen User Guide gefunden werden.GHCup Guide: [https://www.haskell.org/ghcup/guide/](https://www.haskell.org/ghcup/guide/)

## Haskell Language Server
Der Haskell Language Server (HLS) ist ein Tool, das in eine IDE eingebunden werden kann und Funktionen bereitstellt wie code-completion, lint-suggestions, partial-compilation.
HLS kann mittels GHCup installiert werden.

## HLS VSCode integration
Es gibt eine VSCode Erweiterung von den Entwicklern des HLS um diesen in VSCode zu integrieren. 
Dafür den folgenden Schritten folgen:
1. Sicherstellen HLS ist installiert, falls dies nicht zutrifft, dies mit `GHCup install hls` nachholen.
2. Erweiterung installieren (in VSCode Ctrl + P und dann ext install haskell.haskell)
