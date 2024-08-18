# Uke 34: Uttrykk og Variable i Python

## Innholdsfortegnelse
1. [Uttrykk i Python](#uttrykk-i-python)
    1. [Navn, Beskyttede Ord, Verdier og Operatorer](#navn-beskyttede-ord-verdier-og-operatorer)
    2. [Aritmetiske Operatorer](#aritmetiske-operatorer)
    3. [Logiske Operatorer](#logiske-operatorer)
    4. [Operatorpresedens og Parentesbruk](#operatorpresedens-og-parentesbruk)
2. [Variable og Tilordning](#variable-og-tilordning)
    1. [Tilordningsoperatoren](#tilordningsoperatoren)
    2. [Sammensatt Tilordning](#sammensatt-tilordning)
    3. [Tilordninger til Samme vs. Ulike Objekt](#tilordninger-til-samme-vs-ulike-objekt)
3. [Datatyper](#datatyper)
    1. [Elementære Typer](#elementære-typer)
    2. [Verdier med Spesifikk Betydning](#verdier-med-spesifikk-betydning)
    3. [Sammensatte Typer](#sammensatte-typer)
    4. [Typerelaterte Standardfunksjoner](#typerelaterte-standardfunksjoner)
    5. [Forskjell på Muterbare og Immuterbare Datatyper](#forskjell-på-muterbare-og-immuterbare-datatyper)
4. [Tallrepresentasjon og Avrundingsfeil](#tallrepresentasjon-og-avrundingsfeil)
    1. [Avrundingsfeil](#avrundingsfeil)
    2. [Eksempler på Avrundingsfeil](#eksempler-på-avrundingsfeil)
    3. [Overflyt og Underflyt](#overflyt-og-underflyt)
5. [Oppsummering av Forelesning](#oppsummering-av-forelesning)
6. [Repetisjonsspørsmål](#repetisjonsspørsmål)
7. [Svar på Repetisjonsspørsmål](#svar-på-repetisjonsspørsmål)

## Uttrykk i Python

### Navn, Beskyttede Ord, Verdier og Operatorer

**Navn:** Identifikatorer brukt for å referere til variabler, funksjoner osv. De må starte med en bokstav eller understrek `_`, etterfulgt av bokstaver, tall eller understrek.

**Beskyttede Ord:** Python-reserverte ord som ikke kan brukes som variabelnavn, f.eks. `if`, `else`, og `while`. Bruker du et beskyttet ord som variabelnavn vil du få en syntaksfeil:

```python
if = 10  # Feil!
```

**Verdier:** Konstantene eller dataene som variabler kan peke til, f.eks. `42`, `3.14`, `"Hei"`.

**Operatorer:** Symboler som utfører operasjoner på verdier, f.eks. `+`, `-`, `*`, `/`.

### Aritmetiske Operatorer

- `+` : Legger sammen to verdier.
- `-` : Subtraherer én verdi fra en annen.
- `*` : Multipliserer to verdier.
- `/` : Dividerer én verdi med en annen.
- `//` : Heltallsdivisjon som runder ned til nærmeste heltall.
- `%` : Modulus-operasjon, rest av divisjon.
- `**` : Eksponentiering.

Eksempel:
```python
a = 5 + 3   # a blir 8
b = 10 - 2  # b blir 8
c = 4 * 2   # c blir 8
d = 8 / 2   # d blir 4.0
e = 7 // 3  # e blir 2
f = 7 % 3   # f blir 1
g = 2 ** 3  # g blir 8
```

### Logiske Operatorer

- `>` : Større enn.
- `>=` : Større enn eller lik.
- `<` : Mindre enn.
- `<=` : Mindre enn eller lik.
- `==` : Lik.
- `!=` : Ulik.
- `is` : Samme objekt-identitet.
- `in` : Medlemskap i en sekvens.
- `not in` : Ikke medlem i en sekvens.
- `and` : Logisk AND.
- `or` : Logisk OR.
- `not` : Logisk NOT.

Eksempel:
```python
print(3 > 2)    # True
print(3 >= 3)   # True
print(3 < 4)    # True
print(3 <= 3)   # True
print(3 == 3)   # True
print(3 != 4)   # True
print(3 is 3)   # True
print(3 in [1, 2, 3])  # True
print(3 not in [4, 5]) # True
print(True and False)  # False
print(True or False)   # True
print(not False)       # True
```

### Operatorpresedens og Parentesbruk

Operasjoner utføres i følgende rekkefølge:
1. Parenteser `()`
2. Eksponentiering `**`
3. Negasjon og bitvis NOT `-` og `~`
4. Multiplikasjon, divisjon, etc `*`, `/`, `//`, `%`
5. Addisjon og subtraksjon `+`, `-`
6. Skift `<<`, `>>`
7. Bitvis AND, XOR, OR `&`, `^`, `|`
8. Komparasjoner `<`, `<=`, `>`, `>=`, `==`, `!=`
9. Logiske NOT, AND, OR `not`, `and`, `or`

Eksempel:
```python
# Uten parenteser
result = 3 + 4 * 2  # result blir 11, ikke 14

# Med parenteser
result_parens = (3 + 4) * 2  # result_parens blir 14
```

## Variable og Tilordning

### Tilordningsoperatoren

Variabler tildeles verdier ved bruk av likhetstegnet `=`:
```python
x = 10
```

### Sammensatt Tilordning

De sammensatte tilordningsoperatorene kombinerer en aritmetisk operasjon med tilordning:
- `+=` : Legger til og tildeler.
- `-=` : Trekker fra og tildeler.
- `*=` : Multipliserer og tildeler.
- `/=` : Dividerer og tildeler.
- `//=` : Heltallsdividerer og tildeler.
- `%=` : Moduler og tildeler.
- `**=` : Eksponentierer og tildeler.

Eksempel:
```python
x = 5
x += 3  # x blir 8
x -= 2  # x blir 6
x *= 4  # x blir 24
x /= 6  # x blir 4.0
x //= 2 # x blir 2.0
x %= 2  # x blir 0.0
x **= 3 # x blir 0.0
```

### Tilordninger til Samme vs. Ulike Objekt

Når to variable peker til samme objekt, og objektet er muterbart, vil endringer i én variabel reflektere i den andre.

Eksempel:
```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)  # [1, 2, 3, 4]
```

For å unngå dette kan man bruke `copy()` eller `deepcopy()`:
```python
from copy import deepcopy
a = [1, 2, 3]
b = deepcopy(a)
b.append(4)
print(a)  # [1, 2, 3]
```

## Datatyper

### Elementære Typer

- `int` : Heltall, f.eks. `1`, `2`.
- `float` : Flyttall, f.eks. `3.14`, `2.71`.
- `bool` : Boolean, enten `True` eller `False`.
- `str` : Streng, f.eks. `"Hei"`.

### Verdier med Spesifikk Betydning

- `True` : Sann verdi.
- `False` : Usann verdi.
- `None` : Ingen verdi.
- `inf` : Uendelighet, kan fås via `float('inf')`.

### Sammensatte Typer

- `tuple` : Uforanderlig sekvens av verdier, f.eks. `(1, 2, 3)`.
- `list` : Foranderlig sekvens av verdier, f.eks. `[1, 2, 3]`.
- `numpy.array` : N-dimensjonale matriser, fra biblioteket NumPy.
- `set` : Uordnet samling av unike verdier, f.eks. `{1, 2, 3}`.
- `dict` : Nøkkel-verdi par, f.eks. `{'a': 1, 'b': 2}`.

### Typerelaterte Standardfunksjoner

- `type()` : Returnerer typen til en verdi.
- `int()`, `float()`, `str()`, `bool()`, `tuple()`, `list()`, `set()`, `numpy.array()` : Konverterer verdier til andre typer.

Eksempel:
```python
x = 3.14
print(type(x))  # <class 'float'>
y = int(x)
print(y)  # 3
```

### Forskjell på Muterbare og Immuterbare Datatyper

Muterbare typer kan endres etter opprettelse, f.eks. `list` og `dict`.
Immuterbare typer kan ikke endres etter opprettelse, f.eks. `tuple` og `string`.

Eksempel:
```python
my_list = [1, 2, 3]
my_list[0] = 9  # Endrer første element til 9

my_tuple = (1, 2, 3)
try:
    my_tuple[0] = 9  # Feil! Kan ikke endre innholdet i en tuple
except TypeError as e:
    print(e)
```

Bruk av `copy()` and `deepcopy()` for muterbare data:
```python
from copy import deepcopy

original_list = [1, 2, [3, 4]]
shallow_copy = original_list.copy()
deep_copy = deepcopy(original_list)

shallow_copy[2].append(5)
print(original_list)  # [1, 2, [3, 4, 5]]
print(deep_copy)  # [1, 2, [3, 4]]
```

## Tallrepresentasjon og Avrundingsfeil

### Avrundingsfeil

Flyttall representeres med en begrenset presisjon, noe som fører til avrundingsfeil. Dette er et resultat av at flyttall er lagret som binære brøker.

### Eksempler på Avrundingsfeil

Når man adderer eller subtraherer tall med svært forskjellige størrelsesordener, kan man miste presisjon:

```python
x = 1.0000001
y = 1.0000002
print(y - x)  # Forventet: 1e-07, faktiske: 1.0000000005838672e-07

# Addisjon av tall med forskjellige størrelsesordener
print(1.0 + 1e-16)  # Forventet 1.0000000000000001, faktiske: 1.0
```

Unngåelse av avrundingsfeil ved å omorganisere beregningene:
```python
a = 1e16
b = 1.0
c = -1e16
result = (a + b) + c  # Kan resultere i tap av presisjon
result = a + (b + c)  # Bedre rekkefølge
```

### Overflyt og Underflyt

Overflyt inntreffer når et tall er for stort til å representeres av typen:
```python
import math
try:
    result = math.exp(1000)  # Vil gi OverflowError
except OverflowError as e:
    print(e)
```

Underflyt skjer når et tall er for nært null:
```python
underflow_result = 1e-308 / 1e308
print(underflow_result)  # 0.0
```

For å unngå over- og underflyt, kan man skalere problemløsningen slik at operasjonene utføres innenfor representerbare områder.

## Oppsummering av Forelesning
I denne uken har vi gjennomgått uttrykk og variable i Python. Vi har sett på forskjellige typer operatorer og hvordan de brukes, inkludert aritmetiske og logiske operatorer. Vi har også diskutert variabeltilordning, både med enkel og sammensatt tilordning, og sett forskjellen mellom muterbare og immuterbare datatyper samt deres bruk med shallow og deep copy. Avslutningsvis undersøkte vi flyttallsrepresentasjon, avrundingsfeil, og problemene knyttet til overflyt og underflyt.

## Repetisjonsspørsmål
1. Hva er et beskyttet ord i Python?
2. Hvordan fungerer heltallsdivisjon i Python, og hvilken operator brukes?
3. Forklar forskjellen mellom `is` og `==`.
4. Hva er operatorpresedens, og hvorfor er det viktig?
5. Hvordan kan man unngå avrundingsfeil ved manipulering av flyttall?
6. Forklar forskjellen mellom muterbare og immuterbare datatyper.
7. Nevn to eksempler på sammensatte tilordningsoperatorer og hvordan de brukes.
8. Hva mener vi med overflyt og underflyt i numeriske beregninger?

## Svar på Repetisjonsspørsmål
1. Et beskyttet ord er et reserverte ord i Python som ikke kan brukes som variabelnavn, f.eks. `while`, `for`, `if`.
2. Heltallsdivisjon deler én verdi med en annen og runder ned til nærmeste heltall; operatoren er `//`.
3. `is` sjekker om to variabler refererer til samme objekt, mens `==` sjekker om verdiene til variablene er like.
4. Operatorpresedens bestemmer rekkefølgen operasjoner utføres i et uttrykk. Det er viktig for å unngå feilaktige beregninger.
5. Avrundingsfeil kan unngås ved å omorganisere beregningene eller bruke numeriske metoder som intervalleanalyse.
6. Muterbare datatyper kan endres etter at de er opprettet (f.eks. `list`), mens immuterbare typer ikke kan endres (f.eks. `tuple`).
7. To eksempler på sammensatte tilordningsoperatorer er `+=` (x += 2) og `*=` (x *= 2).
8. Overflyt skjer når et tall er for stort til å representeres av typen, mens underflyt skjer når et tall er for nært null for å kunne representeres nøyaktig.

# Antall Token
Totalt brukt cirka: 1300 tokens