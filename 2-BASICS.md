# Grundlagen

## Das erste Programm

Das erste Programm ist ein einfaches "Hello World"-Programm, welches die Welt begrüßt.

```cpp
#include <iostream>

int main()
{
    // print "Hello World" on the screen
    std::cout << "Hello World!";
    return 0;
}
```

Wie schon in den ersten Tutorial-Schritten erklärt gibt die Befehlskette `std::cout` alle Zeichen nach den `<<`-Zeichen auf dem Bildschirm aus.
Um die `std::cout`-Funktion nutzen zu können, muss die Funktionalität eingebunden werden.
Dies passiert mit der ersten Zeile dem Einbinden des `iostream`s. Der `iostream` bietet C++-Funktionen für Ein- und Ausgabe (*I*nput und *O*utput).

Funktionen, wie die `main`-Funktion, bestehhen aus folgendem Aufbau:
- Rückgabewert wie `int`, der definiert, welchen Datentyp die Funktion zurückgibt
- den Namen der Funktion, wie `main`, gefolgt von
- den Parametern zwischen den Klammern `(` und `)`, im Beispiel leer
- der Funktionskörper wird zwischen geschweiften Klammern geschrieben `{` und `}`

Kommentare, die bei der Lesbarkeit des Codes helfen, werden mit `//` begonnen. Diese werden vom Compiler ignoriert.

### Namespaces

Beim Funktionsaufruf im Beispiel mit `std::cout` die Funktion `cout` aus dem Namensraum `std` aufgerufen.
Der Namensraum (namespace) wird von der Funktion mit doppelten Doppelpunkt `::` separiert.
Um die `::` zu vermeiden kann der namespace `std` auch direkt in der gesamten Datei genutzt werden.

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello World!";
    return 0;
}
```

## Datentypen und Variablen

Um Daten während eines Programmes zwischenzuspeichern werden Variablen benutzt.
Folgender Code speichert die Werte `5` und `2` auf die Variablen `number1` und `number2`, inkrementiert die Variable `number2` und addiert `number1` und `number2` auf die Variable `sum`.

```cpp
number1 = 5;
number2 = 2;
number1 = number1 + 1;
sum = number1 + number2;
```

Variablen dürfen wild benannt werden. Es dürfen jedoch keine Sonderzeichen vorkommen oder [reservierte Worte](https://en.cppreference.com/w/cpp/keyword) sein.
Außerdem unterscheiden sich Variablen in der Groß- und Kleinschreibweise. Die Variable `sum` speichert andere Werte als die Variable `SUM` oder `Sum`.

### unterschiedliche Datentypen

Der vorhergehende Code funktioniert noch nicht:

```cpp
#include <iostream>

int main()
{
    number1 = 5;
    number2 = 2;
    number1 = number1 + 1;
    sum = number1 + number2;
    return 0;
}
```

Die Fehlermeldung `error: ‘number1’ was not declared in this scope` zeigt, dass `number1` noch nicht definiert ist.
Der Programmcode funktioniert nachdem die Variablen vor der ersten Benutzung deklariert und mit einem Typen definiert werden.

```cpp
#include <iostream>

int main()
{
    int number1, number2, sum;

    number1 = 5;
    number2 = 2;
    number1 = number1 + 1;
    sum = number1 + number2;
    return 0;
}
```

Damit werden in der ersten Zeile der Funktion alle Variablen vom Typen `int` definiert.
`int` ist die Abkürzung für *Integer*, was einer Ganzzahl entspricht.
In die Variablen können Zahlen ohne Komma gespeichert werden.

Folgende Datentypen können deklariert werden.

#### Zeichen

| Typ | Beschreibung |
| --- | --- |
| char | Ein Zeichen, 1 Byte bzw 8 Bit groß. |
| char16_t | Ein Zeichen, 2 Byte bzw 16 Bit groß. |
| char32_t | Ein Zeichen, 4 Byte bzw 32 Bit groß. |
| whar_t | Ein Zeichen, zum Speichern der längstmöglichen Größen. |

#### Ganzzahlen mit Vorzeichen

| Typ | Beschreibung | Größe |
| --- | --- | --- |
| signed char | Eine Zahl, 1 Byte bzw 8 Bit groß. | - 127 bis 127 |
| short | Eine Zahl, maximal 2 Byte bzw 16 Bit groß. | - 32.768 bis 32.768 |
| int | Eine Zahl, maximal 2 Byte bzw 16 Bit groß. | - 32.768 bis 32.768 |
| long | Eine Zahl, maximal 4 Byte bzw 32 Bit groß. | - 2.147.483.648 bis 2.147.483.648 |
| long long | Eine Zahl, maximal 8 Byte bzw 64 Bit groß. | |

#### Ganzzahlen ohne Vorzeichen

Im Gegensatz zu Ganzzahlen mit Vorzeichen können vorzeichenlose Ganzzahlen nur positiv sein.
Damit passen mehr Werte in eine Variable

| Typ | Beschreibung | Größe |
| --- | --- | --- |
| unsigned char | Eine Zahl, 1 Byte bzw 8 Bit groß. | 0 bis 256 |
| unsigned short | Eine Zahl, maximal 2 Byte bzw 16 Bit groß. | 0 bis 65.536 |
| unsigned | Eine Zahl, maximal 2 Byte bzw 16 Bit groß. | 0 bis 65.536 |
| unsigned long | Eine Zahl, maximal 4 Byte bzw 32 Bit groß. | 0 bis 4.294.967.296 |
| unsigned long long | Eine Zahl, maximal 8 Byte bzw 64 Bit groß. | 0 bis 18.446.744.073.709.551.616 |

#### Kommazahlen

| Typ | Beschreibung |
| --- | --- |
| float | Eine Komma-Zahl, 1 Byte bzw 8 Bit groß. |
| double | Eine Komma-Zahl, maximal 2 Byte bzw 16 Bit groß. |
| long double | Eine Komma-Zahl, maximal 2 Byte bzw 16 Bit groß. |

#### weitere Typen

| Typ | Beschreibung |
| --- | --- |
| bool | Wahr oder falsch / true oder false. |
| void | nichts |
| decltype(nullptr) | Null pointer |

### Zeichenketten

In C++ lassen sich auch komplette Zeichenketten aus mehreren Zeichen speichern. Diese Zeichenketten, *string*s, benötigen eine eigenes eingebundes Paket `#include <string>`.

```cpp
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string myString;
    myString = "Das ist eine Zeichenkette.";
    cout << myString;

    return 0;
}
```

## Konstanten

Wenn Variablen dauerhaft einen unveränderlichen Wert definiert haben heißen diese Konstanten. Sie werden durch das Schlüsselwort `const` deklariert.

```cpp
#include <iostream>

using namespace std;

const double pi = 3.14159;
const char linebreak = '\n';

int main()
{
    double radius = 5.0;
    double circle;

    circle = 2 * pi * radius;
    cout << circle;
    cout << linebreak;

    return 0;
}
```

## Operatoren

Auf Werte und Variablen lassen sich Operatoren anwenden. Diese sind in folgender Tabelle definiert.

| Typus | Beispiel | Beschreibung |
| --- | --- | --- |
| Zuweisung | `x = 5;` | Wert wird gespeichert |
| Addition | `sum = a + 3;` | Werte werden addiert |
| Substraktion | `sub = a - 3;` | Werte werden substrahiert |
| Multiplikation | `mul = a * 3;` | Werte werden multipliziert |
| Division | `div = a / 3;` | Werte werden dividiert |
| Modulo | `mod = a % 3;` | Werte werden dividiert, der Rest wird gespeichert |
| Addition & Zuweisung | `sum += 3;` | Wert wird mit anderen Wert addiert und auf denselben Wert gespeichert: `sum = sum + 3;` |
| Substraktion & Zuweisung | `sub -= 3;` | Wert wird mit anderen Wert subtrahiert und auf denselben Wert gespeichert: `sub = sub - 3;` |
| Multiplikation & Zuweisung | `mul *= 3;` | Wert wird mit anderen Wert mulipliziert und auf denselben Wert gespeichert: `mul = mul * 3;` |
| Division & Zuweisung | `div /= 3;` | Wert wird mit anderen Wert dividiert und auf denselben Wert gespeichert: `div = div / 3;` |
| Modulo & Zuweisung | `mod %= 3;` | Wert wird mit anderen Wert dividiert, der Rest gespeichert, und auf denselben Wert gespeichert: `mod = mod % 3;` |
| Inkrement | `value++;` | Wert wird um 1 erhöht: `value = value + 1;` |
| Dekrement | `value--;` | Wert wird um 1 verringert: `value = value - 1;` |
| Vergleich | `(a == b)` | Werte werden verglichen, es wird `true` oder `false` ersetzt |
| Ungleich | `(a != b)` | Werte werden verglichen, es wird `true` oder `false` ersetzt |
| kleiner als | `(a < b)` | Werte werden verglichen, es wird `true` oder `false` ersetzt |
| größer als | `(a > b)` | Werte werden verglichen, es wird `true` oder `false` ersetzt |
| kleiner oder gleich als | `(a <= b)` | Werte werden verglichen, es wird `true` oder `false` ersetzt |
| größer oder gleich als | `(a >= b)` | Werte werden verglichen, es wird `true` oder `false` ersetzt |
| Negation | `!value` | Wert wird negiert, es wird `true` oder `false` ersetzt |
| UND | `a && b` | Werte werden mit UND vergleichen, es wird `true` oder `false` ersetzt |
| ODER | `a || b` | Werte werden mit ODER vergleichen, es wird `true` oder `false` ersetzt |
| Abfrage-Operator | `result = (operation == 'add') ? a + b : a - b;` | Entscheidungs-Operator, wenn *wahr* dann wird nach `?` genutzt, wenn *falsch* `:` |
| Casting | `ganzzahl = (int) 3.141` | Wandle einen Datentyp in einen anderen um. |
