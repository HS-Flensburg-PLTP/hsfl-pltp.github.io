---
layout: post
title: Abschlussarbeiten/Projekte
date: 2023-07-10
---

Die hier aufgeführten Bachelor- und Masterarbeiten können in Absprache auch in Form von Bachelor- bzw. Masterprojekten bearbeitet werden.
Dabei wird ggf. der Umfang des Projektes an die Gegebenheiten des Projektes angepasst.
Falls Sie sich für andere Themen aus den Bereichen moderne Methoden der Softwareentwicklung, Compilerbau, Programmiersprachen, Algorithmen oder Sicherheit interessieren, wenden Sie sich bitte einfach per Mail an [mich](mailto:jan.christiansen@hs-flensburg.de).


## Design und Implementierung von Programmiersprachen


### Freie Theoreme in Java

Ein [freies Theorem](http://www.cs.sfu.ca/CourseCentral/831/burton/Notes/July14/free.pdf) ist eine Aussage über eine Funktion/Methode, die allein an Hand des Typs der Funktion/Methode getroffen werden kann.
Als Beispiel betrachten wir die Signatur der folgenden Haskellfunktion.

```haskell
foo :: [a] -> [a]
```

Obwohl wir nur den Typ der Funktion kennen und nicht die konkrete Implementierung, muss diese Funktion sich an gewissen Regeln halten.
Das freie Theorem für diese Funktion sagt aus, dass für jede Liste `list` gilt, dass `map f (foo list)` das gleiche Ergebnis liefert wie der Aufruf `foo (map f list)`.
Das heißt, es macht keinen Unterschied, ob wir `map` auf das Argument der Funktion oder das Ergebnis der Funktion anwenden.
Gesetze dieser Art kann man für jede polymorphe Funktion herleiten.
Während die Gesetzmäßigkeit für `foo` recht einfach wirkt, kann man bei komplexeren Typen erstaunlich komplexe Aussagen über eine Funktion ableiten.

Diese Form der Gesetzmäßigkeit gilt nicht nur in Sprachen wie Haskell, sondern auch in anderen Programmiersprachen die Polymorphismus/Generics zur Verfügung stellen.
Eine Einführung zu freien Theoremen im Kontext von Java bietet zum Beispiel [dieser Vortrag](http://data.tmorris.net/talks/yow-west-2016/1d388b6263e7cbeedfbea224997648daa1d7862d/parametricity.pdf).
Freie Theoreme basieren auf der Grundidee, dass man keinen Wert von einem polymorphen Typ erfinden kann.
Die Funktion `foo` kann in der Ergebnisliste zum Beispiel kein neues Element hinzufügen, die Funktion kann eigentlich nur die Elemente der Argumentliste verwenden, um die Ergebnisliste zu konstruieren.

Je nach dem, welche Sprachkonstrukte eine Programmiersprache zur Verfügung stellt, sind freie Theoreme nur noch in eingeschränkter Form gültig.
So können zum Beispiel Sprachfeatures wie Typumwandlung oder Typprüfung dafür sorgen, dass freie Theoreme nur mit Einschränkungen gültig sind.
In dieser Arbeit soll eine Fallstudie über Sprachfeatures in Java gemacht werden.
Dabei soll untersucht werden, bei der Verwendung von welchen Sprachfeatures in Java freie Theoreme nur noch unter Einschränkungen gültig sind.

**Voraussetzungen:** gute Kenntnisse der Programmiersprache Java, Grundkenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit


### Programmierstil in Elm

In dieser Arbeit soll der Programmierstil analysiert werden, der in Elm-Projekten bei GitHub verwendet wird.
Es existiert bereits eine Haskell-Anwendung, die Elm-Projekte bei GitHub sammelt und Kennwerte für diese Anwendungen erhebt, zum Beispiel die Anzahl der Module oder die durchschnittliche Anzahl an Definitionen pro Modul.
In diesem Projekt sollen Eigenschaften der Projekte analysiert werden, die sehr Elm-spezifisch sind.
Zum Beispiel kann überprüft werden, wie die Projekte _underscore pattern_ einsetzen und ob Funktionen immer eta-reduziert sind.
Oder es kann überprüft werden, in welcher Reihenfolge die Definitionen in einem Modul sortiert sind, also zum Beispiel zuerst alle Datentypdefinitionen und dann alle Funktionsdefinitionen oder gemischt.
Es kann aber auch geprüft werden, in welcher Reihenfolge das _Pattern Matching_ der `update`-Funktion durchgeführt wird, also zuerst _Pattern Matching_ auf `Model` und anschließend auf `Msg` oder andersherum.
Oder es kann überprüft werden, wie Funktionen genannt werden, die eine `Html`-Struktur liefern, also aus `view` heraus aufgerufen werden.

Im ersten Schritt muss in dieser Arbeit definiert werden, welche Eigenschaften evaluiert werden sollen und wie diese Eigenschaften bewertet, gruppiert werden.
Danach muss die jeweilige Analyse in das Bestehende Tool integriert werden.

**Voraussetzungen:** gute Kenntnisse in Elm  
**Geeignet als:** Bachelor- oder Masterarbeit


### Bezeichner in PureScript

In dieser Arbeit sollen Projekte von GitHub gesammelt werden, welche die Sprache [PureScript](https://www.purescript.org) nutzen.
Anschließend soll analysiert werden, welche Bezeichner für Funktionen und Variablen in PureScript genutzt werden.
Hierzu wird zum Beispiel analysiert, wie lang diese Bezeichner in PureScript sind und welche Einbuchstabenbezeichner (also `a`, `b`, `c`, etc.) in PureScript genutzt werden.

In einer zuvor durchgeführten Abschlussarbeit wurde eine entsprechende Analyse für Bezeichner in Haskell-Projekten durchgeführt.
Im ersten Schritt muss die bestehende Anwendung so erweitert werden, dass sie in der Lage ist, PureScript-Projekte zu sammeln und zu analysieren.
Nach der Erweiterung soll es möglich sein, die Analyse für Haskell-Projekte als auch für PureScript-Projekte durchzuführen.

Zur Analyse der PureScript-Projekte muss der PureScript-Code verarbeitet werden.
Dazu soll ein Teil des [PureScript-Compilers](https://github.com/purescript/purescript) werden.
Der PureScript-Compiler ist in Haskell geschrieben und stellt einen Parser für PureScript zur Verfügung.
Dieser Parser kann genutzt werden, um ein PureScript-Modul in einen AST (_Abstract Syntax Tree_) umzuwandeln und den AST anschließend zu analysieren.

**Voraussetzungen:** Grundkenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit


## Künstliche Intelligenz im _Software Engineering_

### Generieren von Funktionsnamen aus Funktionsdefinitionen

In dieser Arbeit soll eine bestehende Technik zum Lernen von Methodennamen aus Methodendefinitionen mit Hilfe eines neuronalen Netzes auf die Programmiersprache Haskell angewendet werden.
[CODE2VEC](https://code2vec.org) ist eine Technik, mit der Programme in Vektoren mit Zahlen umgewandelt werden können.
Diese Vektoren können dann genutzt werden, um neuronale Netze zu trainieren, die Programme verarbeiten können.
In einer ersten Anwendung wurde diese Technik verwendet, um für eine gegebene Java-Methode einen möglichst gut passenden Namen zu generieren.
In dieser Arbeit soll genau diese Technik auf Funktionen in der Programmiersprache Haskell angewendet werden.
In einer Vorarbeit wurde eine Haskell-Anwendung entwickelt, die ein Haskell-Modul einliest und daraus die entsprechenden Vektoren erzeugt.

Im ersten Schritt müssen in dieser Arbeit Haskell-Module gesammelt werden, zum Beispiel von GitHub.
Diese Module werden dann mit Hilfe der bestehenden Anwendung in Vektoren umgewandelt.
Mit Hilfe der auf diese Weise generierten Trainingsdaten muss dann ein neuronales Netz trainiert werden.
Dazu muss eine Python-Anwendung, die für das Training mit den Java-Programmen genutzt wird, entsprechend angepasst werden.
Es ist zu erwarten, dass die Haskell-Anwendung zur Generierung der Vektoren aus Haskell-Modulen noch angepasst werden muss.

**Voraussetzungen:** Grundkenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit
