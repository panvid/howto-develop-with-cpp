# Konzepte von C++

## Compiler

C++ ist eine Programmiersprache, die kompiliert werden muss. Dabei werden Code-Zeilen, die menschenlesbar sind, in Maschinencode umgewandelt.

Aus dem lesbaren C++-Code
```cpp
int a, b, sum;

cin >> a;
cin >> b;

sum = a + b;
cout << sum << endl;
```

wird beim [Kompilieren](https://de.wikipedia.org/wiki/Compiler) beispielsweise der Maschinencode:

```
00000 10011110
00001 11110100
00010 10011110
00011 11010100
00100 10111111
00101 00000000
```

Dies passiert mit *CLion* beim Ausführen des Programmes mit dem Klick auf den grünen Pfeil.

## Unterschiede zu nicht-compilierbaren Sprachen

Nicht alle Programmiersprachen müssen kompiliert werden. Einige führen auch direkt den menschenlesbaren Code aus [Interpreter](https://de.wikipedia.org/wiki/Interpreter). Dazu gehören die Skriptsprachen.

Vorteil des Compilers: Wenn Programmcode kompiliert wird werden Programm-Fehler direkt beim Umwandeln in den Maschinencode gefunden und angezeigt. Weiterhin wird der Code für das Betriebssystem, auf dem kompiliert wird, optimiert.
