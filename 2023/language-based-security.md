---
layout: post
title: "Language-based Security"
date: 2023-04-14
---


<!-- ## Vorlesungen -->

<!-- Die Vorlesung gibt eine Einführung in den Bereich der [Language-based Security](https://en.wikipedia.org/wiki/Language-based_security).

Im [github-Projekt](https://github.com/jan-christiansen/Language-based-Security) gibt es die Coq-Quelldateien aus der Vorlesung. -->


## Vorlesungen

Unter <https://github.com/HS-Flensburg-LBS/Language-based-Security> finden Sie die Coq-Skripte, die wir in der Vorlesung zusammen entwickelt haben.


### 1. Vorlesung

Inhalte der Abschnitte [_Preface_](https://softwarefoundations.cis.upenn.edu/lf-current/Preface.html) und [_Data and Functions_](https://softwarefoundations.cis.upenn.edu/lf-current/Basics.html#lab20) des Buchs [_Software Foundations - Volume 1_](https://softwarefoundations.cis.upenn.edu/current/lf-current/index.html)

### 2. Vorlesung

Inhalte der Abschnitte [_Proof by Simplification_](https://softwarefoundations.cis.upenn.edu/lf-current/Basics.html#lab34), [_Proof by Rewriting_](https://softwarefoundations.cis.upenn.edu/lf-current/Basics.html#lab35), [_Proof by Case Analysis_](https://softwarefoundations.cis.upenn.edu/lf-current/Basics.html#lab38) und [_Unfolding Definitions_](https://softwarefoundations.cis.upenn.edu/lf-current/Tactics.html#lab172)

### 3. Vorlesung

Inhalte der Abschnitte [_Proof by Induction_](https://softwarefoundations.cis.upenn.edu/lf-current/Induction.html#lab61), [_Lists of Numbers_](https://softwarefoundations.cis.upenn.edu/lf-current/Lists.html#lab85) und [_Reasoning About Lists_](https://softwarefoundations.cis.upenn.edu/lf-current/Lists.html#lab97)


## Verwendung von Coq

In diesem Abschnitt werden technische Aspekte bei der Verwendung von Coq erklärt.

### Übersetzung eines Projektes

Ab der dritten Aufgabe besteht das Coq-Projekt aus mehreren Coq-Dateien.
Um eine Coq-Datei in einer anderen Coq-Datei importieren zu können, müssen die Dateien zuerst übersetzt werden.
Coq verwendet hierfür ein `Makefile`.
Mit dem folgenden Kommando kann dieses `Makefile` erstellt werden.

```console
coq_makefile -f _CoqProject *.v -o Makefile
```

Mit dem folgenden Kommando wird das `Makefile` ausgeführt und die Coq-Dateien im Verzeichnis übersetzt.

```console
make
```

Unter MacOS und Linux steht das `make`-Kommando standardmäßig zur Verfügung.
Unter Windows muss das Kommando erst einmal installiert werden.
Der folgende Abschnitt gibt Hinweise, wie `make` unter Windows installiert werden kann.


### Installation von `make` unter Windows

Wenn ihr unter Windows arbeitet, muss `make` zuerst installiert werden.
Dafür gibt es recht viele verschiedene Optionen.
Hier wird eine mögliche Option illustriert.

- Laden Sie die Datei `make-4.4.1-without-guile-w32-bin.zip` von der Seite https://sourceforge.net/projects/ezwinports/files/ herunter.
- Erstellen Sie im Ordner `C:\Benutzer\NUTZERNAME` einen Ordner `bin` (`NUTZERNAME` dabei durch den eigenen Nutzernamen ersetzen).
- Entpacken Sie das Zip, indem Sie die Datei `make-4.4.1-without-guile-w32-bin.zip` im _Windows Explorer_ öffnen.
- Kopieren Sie die Datei `make.exe` aus der entpackten ZIP-Datei in den Ordner `C:\Benutzer\NUTZERNAME\bin`.
- Fügen Sie Coq zum Windows-Pfad hinzu:
  - Suchen Sie in der Windows-Suche "Umgebungsvariablen für dieses Konto bearbeiten".
  - Wählen Sie die unter den `Benutzervariablen` die Variable mit dem Namen `Path`.
  - Drücken Sie `Bearbeiten...` und fügen Sie das Verzeichnis, in dem Coq installiert ist, hinzu, zum Beispiel `C:\Coq-Platform~8.16~2022.09\bin`.

Um `make` jetzt zu nutzen, erstellen Sie eine neue Git-Bash im Aufgabenordner.
In der Git-Bash sollten jetzt die Befehle `coq_makefile` und `make` funktionieren.
