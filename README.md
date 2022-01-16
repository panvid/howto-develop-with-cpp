# HowTo: Entwickeln mit C++

Diese Repository ist eine kleine Einführung in die Software-Entwicklung mit C++. Sie ist unvollständig und wird ständig erweitert.

## Programmierumgebung

Es gibt zahlreiche Möglichkeiten um C++-Code auszuführen. Dieses HowTo nutzt [CLion](https://www.jetbrains.com/de-de/clion/) als *IDE*, welches platformübergreifend und für 30 Tage kostenlos testbar ist.

## Das erste Projekt

Nach dem Start von *CLion* wird das erste Projekt erstellt. Es kann aus folgenden Typen gewählt werden:
- **C++ Executable**: eigenständiges C++-Programm
- **C++ Library**: C++-Programmbibliothek, welche nicht alleine ausfühbar ist
- **C Executable**: eigenständiges C-Programm
- **C Library**: C-Programmbibliothek, welche nicht alleine ausfühbar ist
- **CUDA Executable**: eigenständiges Programm, auf NVIDIA-Grafikkarten ausgeführt
- **CUDA Library**: Bibliothek, auf NVIDIA-Grafikkarten ausgeführt, welche nicht alleine ausfühbar ist
- **Qt Console Executable**: Qt-Programm, in der Console ausgeführt
- **Qt Widget Excecutable**: Qt-Programm, in Fenstern und UI ausgeführt
- **STM32CubeMX**: Programm für STM32 Mikrocontroller

Nachdem **C++ Executable** für ein eigenständiges C++-Programm gewählt wird kann die C++-Version ausgwählt werden. Es gibt folgende Unterschiede:
- **C++98**: 1998 fertig gestellte C++-Version
- **C++11**: Version von [2011](https://de.wikipedia.org/wiki/C%2B%2B#C++11), mit Funktionalitäten wie *anonyme Funktionen*, *Enums* und *automatische Typen*
- **C++14**: Version von 2014
- **C++17**: Version von 2017
- **C++20**: [aktuellste Version](https://de.wikipedia.org/wiki/C%2B%2B#C++20) von C++, mit Funktionalitäten wie *Koroutinen*, *Concepts* und *bestimmte Initializer*
- **C++23**: Noch in Entwicklung befindliche C++-Version, mit Funktionalitäten wie *Reflections* und *Pattern Matching*

Es wird ein Projektordner ausgewählt sowie die letzte aktuelle Version von C++, **C++20**.

## Aufbau von CLion

![Leeres neues Projekt](https://raw.githubusercontent.com/panvid/howto-develop-with-cpp/main/img/new-project.png)

Der Standard-Aufbau von CLion ist übersichtlich:
- Im **linken** Bereich sind alle *Projektdateien* dieses Projektes sichtbar. Daneben werden auch *Externe Libraries* angezeigt, die aufgerufen, aber nicht geändert werden können.
- Im **oberen** Bereich lässt sich das Projekt ausführen, bauen und Tests ausführen.
- Im **unteren** Bereich gibt es, aufklappbar, wichtige Tools wie *Problems* zur Anzeige von Problemen, *Terminal* zur Ausführung von Befehlen.
- Im **rechten** bzw **mittleren** Bereich kann der Projekt-Code eingegeben werden.

## Der erste Code

Beim Start istsind bereits 6 Zeilen Code eingegeben:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

Der Beispiel-Code kann mit dem Klick auf den grünen Pfeil vor der `main`-Funktion ausgeführt werden (**Run first project**). Dabei öffnet sich der **Run**-Tabulator unterhalb und gibt folgendes aus:
```sh
/home/david/cpp/first-project/cmake-build-debug/first_project
Hello, World!

Process finished with exit code 0
```

Die Code-Zeilen werden hier erklärt:
- `int main() { ... }` definiert die Hauptfunktion, die beim Programmstart geladen wird
- `std::cout << "Hello, World!" << std.endl;` (Standard-C-Out) schreibe auf die Console alles was nach `<<` erscheint. Mehrere Zeichen können mit weiteren `<<` verbunden werden. `std.endl` fügt einen Zeilenumbruch ein.
- `return 0` beendet die `main`-Funktion und gibt den Wert `0` zurück. Dabei ist `0` die Information, dass alles planmäßig verlaufen ist. Der Code `1` würde darauf hinweisen, dass ein Fehler passiert ist.
