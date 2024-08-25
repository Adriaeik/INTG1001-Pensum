
---

#### 1. [Table of Contents](#Table-of-Contents)

1. [Uttrykk i Python](#Uttrykk-i-Python)
2. [Variable og tilordning](#Variable-og-tilordning)
3. [Datatyper](#Datatyper)
4. [Tallrepresentasjon og avrundingsfeil](#Tallrepresentasjon-og-avrundingsfeil)
5. [Repetisjonsspørsmål](#Repetisjonsspørsmål)

---

### 2. [Main Content](#Main-Content)

---

### Uttrykk i Python

#### Forskjell på navn, beskyttede ord, verdier og operatorer

- Navn er symboler vi definerer for å referere til verdier, som variabelnavn.
- Beskyttede ord (reserved words) er ord som ikke kan brukes som variabelnavn fordi de har spesifikke funksjoner i Python (for eksempel `if`, `for`, `while`).
- Verdier er dataene som variabler holder, for eksempel heltall `5` eller flyttall `3.14`.
- Operatorer er symboler som representerer operasjoner, som addisjon `+` og subtraksjon `-`.

#### De vanlige aritmetiske operatorene

Her er en oversikt over vanlige aritmetiske operatorer i Python:

- `+` : Addisjon
- `-` : Subtraksjon
- `*` : Multiplikasjon
- `/` : Divisjon
- `//` : Heltallsdivisjon
- `%` : Modulo (rest ved divisjon)
- `**` : Eksponentiering

**Eksempel**
```python
a = 10
b = 3
print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.3333333333333335
print(a // b)  # 3
print(a % b)   # 1
print(a ** b)  # 1000
```

#### Logiske operatorer

De viktigste logiske operatorene er:

- `>` : Større enn
- `>=` : Større enn eller lik
- `<` : Mindre enn
- `<=` : Mindre enn eller lik
- `==` : Lik
- `!=` : Ulik
- `is` : Identisk med
- `in` : Inneholder
- `not in` : Inneholder ikke
- `and` : Og
- `or` : Eller
- `not` : Ikke

**Eksempel**
```python
x = 5
y = 10
print(x > y)       # False
print(x < y)       # True
print(x == 5 and y == 10)  # True
print(x != 5 or y == 10)   # True
```

#### Operatorpresedens og parentesbruk

Operatorer har en bestemt rekkefølge de evalueres i, kalt presedens. For eksempel, multiplikasjon `*` har høyere presedens enn addisjon `+`. Parenteser kan brukes til å overstyre denne rekkefølgen.

**Eksempel**
```python
resultat = 3 + 5 * 2  # Evaluert som 3 + (5 * 2), resultat = 13
resultat = (3 + 5) * 2  # Evaluert som (3 + 5) * 2, resultat = 16
```

---

### Variable og tilordning

#### Tilordningsoperatoren `=`

- Den brukes for å gi en variabel en verdi.

**Eksempel**
```python
x = 5
y = 10
```

#### Sammensatt tilordning

Sammensatte operatorer kombinerer en operasjon med tilordning.

- `+=` : Addisjon og tilordning
- `-=` : Subtraksjon og tilordning
- `*=` : Multiplikasjon og tilordning
- `/=` : Divisjon og tilordning
- `//=` : Heltallsdivisjon og tilordning
- `%=` : Modulo og tilordning
- `**=` : Eksponentiering og tilordning

**Eksempel**
```python
x = 5
x += 3  # x = x + 3
print(x)  # 8
```

#### Tilordninger: samme objekt vs. ulikt objekt

Ved tilordning av mutable typer (list, dict, etc.), kan variabler referere til samme objekt eller ulike objekter.

**Eksempel**
```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)  # [1, 2, 3, 4]
```

Her refererer `b` til samme objekt som `a`.

---

### Datatyper

#### Elementære typer: int, float, bool, string

- `int` : Heltall
- `float` : Flyttall (desimaltall)
- `bool` : Boolean (True eller False)
- `string` : Tekststrenger

#### Verdier med spesifikk betydning

- `True` : Sann (bool)
- `False` : Usann (bool)
- `None` : Ingen verdi
- `inf` : Uendelig

#### Sammensatte typer

- `tuple` : Uforanderlig samling av elementer
- `list` : Foranderlig samling av elementer
- `numpy.array` : N-dimensjonal array (brukes ofte i numeriske beregninger)
- `set` : Uordnede og unike elementer
- `dict` : Nøkkel-verdi-par

#### Typerelaterte standardfunksjoner

- `type()` : Returnerer typen til et objekt.
- `int()`, `float()`, `str()`, `bool()`, `tuple()`, `list()`, `set()`, `numpy.array()` : Konverterer til ulike typer.

**Eksempel**
```python
x = 10
print(type(x))  # <class 'int'>
y = float(x)
print(type(y))  # <class 'float'>
```

#### Forskjell på muterbare og immuterbare datatyper

- **Muterbare** : list, dict, set
- **Immuterbare** : int, float, bool, string, tuple

For mutable typer, kan `copy()` og `deepcopy()` brukes for å kopiere innhold.

**Eksempel**
```python
import copy

original = [1, 2, 3]
kopi = copy.deepcopy(original)
kopi.append(4)
print(original)  # [1, 2, 3]
print(kopi)  # [1, 2, 3, 4]
```

---

### Tallrepresentasjon og avrundingsfeil

#### Avrundingsfeil

Representasjonen av flyttall i datamaskiner kan føre til avrundingsfeil fordi ikke alle desimaltall kan representeres eksakt.

**Eksempel**
```python
print(0.1 + 0.2)  # 0.30000000000000004
```

#### Metoden `float.as_integer_ratio()`

Denne metoden viser hvordan et flyttall kan representeres som en brøk av to heltall.

**Eksempel**
```python
print((0.1).as_integer_ratio())  # (3602879701896397, 36028797018963968)
```

#### Typiske feller med avrundingsfeil

- Addisjon av tall med svært ulik størrelsesorden
- Subtraksjon av nesten like tall

**Eksempel**
```python
stor = 1e16
liten = 1.0
print(stor + liten - stor)  # 0.0 (feil)
```

#### Overflyt og underflyt

- **Overflyt** : Når et tall blir for stort for datamaskinen å håndtere.
- **Underflyt** : Når et tall blir for lite til å representeres.

Regnerekkefølgen kan ha stor betydning for om vi får over- eller underflyt.

**Eksempel**
```python
import math
stor_faktor = 1e308
resultat = stor_faktor * 2  # Overflyt: inf
```

---

### 3. [Lecture Summary](#Lecture-Summary)

For eksamen er det viktig å ha en solid forståelse av grunnleggende konsepter i Python, spesielt når det gjelder uttrykk, variabler og tilordning. Vær oppmerksom på de ulike datatypene og deres egenskaper, og hvordan tallrepresentasjon kan påvirke beregninger, inkludert potensielle avrundingsfeil. Kjenn til bruken av logiske og aritmetiske operatorer, og forstå forskjellene mellom mutable og immutable datatyper. Nøyaktig numerisk representasjon er avgjørende for å unngå feil i programmering, så sørg for å mestre disse aspektene godt. Disse temaene er sentrale og kan ofte være grunnlaget for oppgaver på eksamen.

---

### 4. [Repetisjonsspørsmål](#Repetisjonsspørsmål)

<details>
    <summary>1. Hva er forskjellen mellom mutable og immutable datatyper?</summary>
    Mutable datatyper kan endres etter opprettelse, mens immutable datatyper ikke kan endres.
</details>

<details>
    <summary>2. Hva vil `3 + 5 * 2` resultere i og hvorfor?</summary>
    13, fordi multiplikasjon har høyere presedens enn addisjon.
</details>

<details>
    <summary>3. Hva gjør `b = a.copy()` når `a` er en liste?</summary>
    Lager en kopi av listen `a` slik at `b` ikke refererer til samme objekt som `a`.
</details>

<details>
    <summary>4. Hva er resultatet av `0.1 + 0.2` i Python, og hvorfor?</summary>
    0.30000000000000004, på grunn av avrundingsfeil i flyttallsrepresentasjon.
</details>

<details>
    <summary>5. Hva gjør `int('123')` i Python?</summary>
    Konverterer strengen '123' til heltallet 123.
</details>

<details>
    <summary>6. Hvorfor er det nødvendig å bruke `copy()` eller `deepcopy()` med mutable datatyper?</summary>
    For å sikre at man ikke utilsiktet endrer originaldataen.
</details>

<details>
    <summary>7. Hva er en potensielle problemer med subtraksjon av nesten like tall?</summary>
    Det kan føre til betydelige avrundingsfeil.
</details>

<details>
    <summary>8. Hva er betydningen av operatoren `//` i Python?</summary>
    Heltallsdivisjon som returnerer bare heltallsdelen av divisjonen.
</details>

---
