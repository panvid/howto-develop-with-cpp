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
