
## Innhald
1. [If-setningar](#if-setningar)
    - If
    - If-else
    - If-elif...-else
    - Nøstede if-setningar
2. [Løkker](#løkker)
    - while-løkker
    - For-løkker
    - Iterering av sekvenser per element
    - Iterering av sekvenser på indeks
    - break i løkker
    - Nøstede løkker
3. [Variable og Tilordning](#variable-og-tilordning)
    - Tilordningsoperatoren
    - Sammensatt tilordning
    - Tilordninger til same objekt vs. ulike objekt
4. [Datatyper](#datatyper)
    - Elementære typer
    - Verdier med spesifikk betydning
    - Sammensatte typer
    - Typerelaterte standardfunksjoner
    - Forskjell på muterbare og immuterbare datatyper
5. [Tallrepresentasjon og avrundingsfeil](#tallrepresentasjon-og-avrundingsfeil)
    - Avrundingsfeil
    - float.as_integer_ratio()
    - Typiske feller og unngåing
    - Overflyt og underflyt
  
## Hovudinnhald

### If-setningar

#### If
```python
a = 10
if a > 5:
    print("A er større enn 5")
```
**Output**:
```
A er større enn 5
```

#### If-else
```python
b = 3
if b > 5:
    print("B er større enn 5")
else:
    print("B er mindre eller lik 5")
```
**Output**:
```
B er mindre eller lik 5
```

#### If-elif...-else
```python
c = 7
if c > 10:
    print("C er større enn 10")
elif 5 < c <= 10:
    print("C er mellom 6 og 10")
else:
    print("C er 5 eller mindre")
```
**Output**:
```
C er mellom 6 og 10
```

#### Nøstede if-setningar
```python
d = 10
if d > 5:
    if d == 10:
        print("D er lik 10")
    else:
        print("D er større enn 5 men ikkje 10")
else:
    print("D er 5 eller mindre")
```
**Output**:
```
D er lik 10
```

### Løkker

#### While-løkker
```python
i = 0
while i < 5:
    print(i)
    i += 1
```
**Output**:
```
0
1
2
3
4
```

#### For-løkker
```python
for i in range(5):
    print(i)
```
**Output**:
```
0
1
2
3
4
```

#### Iterering av sekvenser per element
```python
frukt = ["eple", "banan", "kirsebær"]
for f in frukt:
    print(f)
```
**Output**:
```
eple
banan
kirsebær
```

#### Iterering av sekvenser på indeks
```python
frukt = ["eple", "banan", "kirsebær"]
for i in range(len(frukt)):
    print(frukt[i])
```
**Output**:
```
eple
banan
kirsebær
```

#### Break i løkker
```python
for i in range(10):
    if i == 5:
        break
    print(i)
```
**Output**:
```
0
1
2
3
4
```

#### Nøstede løkker
```python
for i in range(3):
    for j in range(3):
        print(f"(i, j): ({i}, {j})")
```
**Output**:
```
(i, j): (0, 0)
(i, j): (0, 1)
(i, j): (0, 2)
(i, j): (1, 0)
(i, j): (1, 1)
(i, j): (1, 2)
(i, j): (2, 0)
(i, j): (2, 1)
(i, j): (2, 2)
```

### Variable og Tilordning

#### Tilordningsoperatoren
```python
x = 5
print(x)
```
**Output**:
```
5
```

#### Sammensatt tilordning
```python
x = 10
x += 5  # Tilsvarar x = x + 5
print(x)
```
**Output**:
```
15
```

#### Tilordninger til same objekt vs. ulike objekt

**Same objekt**:
```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)
```
**Output**:
```
[1, 2, 3, 4]
```

**Ulike objekt**:
```python
c = [1, 2, 3]
d = c.copy()
d.append(4)
print(c)
```
**Output**:
```
[1, 2, 3]
```

### Datatyper

#### Elementære typer
```python
heiltal = 5  # int
flyttal = 3.14  # float
boolsk = True  # bool
tekst = "Hei"  # string
```

### Verdier med spesifikk betydning
```python
print(True, False, None, float('inf'))
```

### Sammensatte typer

I Python finst det fleire samansette datatypar som kan lagre fleire element saman. Desse typane kan brukast til ulike føremål, avhengig av om elementa skal vere ordna, endrbare, eller unike. Her er nokre vanlege samansette typar:

```python
import numpy as np

tu = (1, 2)  # tuple: Ein ordna og uforanderleg sekvens av element. Nyttig når du treng ei gruppe verdier som ikkje skal endrast.
li = [1, 2, 3]  # list: Ein ordna og muterbar sekvens av element. Vanlegvis brukt når du treng ei samling som kan endrast dynamisk.
ar = np.array([1, 2, 3])  # numpy.array: Ein array frå NumPy-biblioteket, spesielt brukt for numeriske operasjonar og handsaming av store datamengder.
se = {1, 2, 3}  # set: Ei uordna samling av unike element. Perfekt når du vil sikre at ingen element blir gjenteke.
di = {'ein': 1, 'to': 2}  # dict: Eit ordbok-liknande datastruktur der kvar nøkkel er knytt til ein bestemt verdi. Praktisk når du treng rask tilgang til verdiar basert på nøklar.
```

- **tuple (`tu`)**: Kan ikkje endrast etter at dei er oppretta, noko som gjer dei nyttige for å lagre faste samlingar av data.
- **list (`li`)**: Veldig fleksible, med støtte for innsetjing, sletting og endring av element. Ofte brukt i Python-programmering.
- **numpy.array (`ar`)**: Gir høg yting for numeriske operasjonar og er ofte brukt i vitskapelege berekningar.
- **set (`se`)**: Automatiserer fjerning av duplikat og gir rask testing av medlemsskap.
- **dict (`di`)**: Effektiv måte å lagre og slå opp data basert på unike nøklar.

### Typerelaterte standardfunksjoner

Python har eit sett med innebygde funksjonar for å sjekke typen av eit objekt og for å konvertere mellom ulike typar. Her er nokre døme:

```python
print(type(3.14))  # <class 'float'>
```
- **`type()`**: Brukt for å finne ut kva type ein verdi eller variabel har. I dette tilfellet viser `type(3.14)` at `3.14` er av typen `float`.

```python
print(int("10"))  # 10
```
- **`int()`**: Konverterer ei streng som representerer eit heiltal til ein `int`. I dette tilfellet blir strengen `"10"` konvertert til heiltalet `10`.

```python
print(float(3))  # 3.0
```
- **`float()`**: Konverterer eit heiltal eller annan numerisk verdi til ein `float`. Her blir heiltalet `3` konvertert til flyttalet `3.0`.

```python
print(str(3.14))  # '3.14'
```
- **`str()`**: Konverterer ein verdi til ein streng. Flyttalet `3.14` blir konvertert til strengen `'3.14'`.

```python
print(bool(0))  # False
```
- **`bool()`**: Konverterer ein verdi til ein `bool`. I Python er `0`, `None`, og tomme sekvensar som `[]` og `""` rekna som `False`, medan alle andre verdiar er `True`. Her gir `bool(0)` verdien `False`.

```python
print(tuple([1, 2]))  # (1, 2)
```
- **`tuple()`**: Konverterer ei liste eller annan sekvens til ein `tuple`. Her blir lista `[1, 2]` konvertert til `tuple`-en `(1, 2)`.

```python
print(list((1, 2)))  # [1, 2]
```
- **`list()`**: Konverterer ein `tuple` eller annan sekvens til ei `list`. I dette tilfellet blir `tuple`-en `(1, 2)` konvertert til lista `[1, 2]`.

```python
print(set([1, 2, 1]))  # {1, 2}
```
- **`set()`**: Konverterer ei liste eller annan sekvens til eit `set`, der alle elementa er unike. Her blir lista `[1, 2, 1]` konvertert til `set`-et `{1, 2}`, der duplikat blir fjerna.

```python
print(np.array([1, 2, 3]))  # array([1, 2, 3])
```
- **`np.array()`**: Opprettar ein NumPy-array frå ei liste. Dette er nyttig for effektiv numerisk handsaming og operasjonar.

### Forskjell på muterbare og immuterbare datatyper

Python skil mellom muterbare (endrebare) og immuterbare (ikkje endrebare) datatypar:

```python
# Muterbare: list, dict, set, numpy.array
li = [1, 2, 3]
li.append(4)
print(li)  # [1, 2, 3, 4]
```
- **Muterbare typar**: Datatypar som kan endrast etter at dei er oppretta. Til dømes kan du legge til eller fjerne element frå ei `list`, oppdatere verdiar i ein `dict`, eller endre innhaldet i ein `numpy.array`.

```python
# Immuterbare: int, float, bool, string, tuple
tu = (1, 2)
# tu.append(3) # Gir feil
```
- **Immuterbare typar**: Datatypar som ikkje kan endrast etter at dei er oppretta. Til dømes kan ikkje ein `tuple` eller `string` endrast. Å prøve å modifisere desse typar direkte vil resultere i ein feil.

### Bruk av `copy()` og `deepcopy()` for muterbare data

Når ein arbeider med muterbare objekt, er det viktig å forstå forskjellen mellom ein "shallow copy" og ein "deep copy":

```python
import copy

li = [1, 2, [3, 4]]
shallow_copy = copy.copy(li)
deep_copy = copy.deepcopy(li)

shallow_copy[2].append(5)
print(li)  # [1, 2, [3, 4, 5]]
print(shallow_copy)  # [1, 2, [3, 4, 5]]
print(deep_copy)  # [1, 2, [3, 4]]
```
- **`copy.copy()`**: Lag ein "shallow copy" av eit objekt. Dette betyr at den nye kopien inneheld referansar til dei same objekta som den originale, ikkje kloning av dei indre objekta. I eksempelet ovanfor, når du endrar den innstøypte lista i `shallow_copy`, blir også den originale lista `li` påverka.

- **`copy.deepcopy()`**: Lag ein "deep copy" av eit objekt. Dette betyr at alle nivå av det muterbare objektet blir klona, slik at endringar i den kopierte lista ikkje påverkar den originale lista. I eksempelet ovanfor, når du endrar den innstøypte lista i `deep_copy`, blir ikkje den originale lista `li` påverka.

Dette er spesielt viktig når du arbeider med komplekse datastrukturar som inneheld muterbare objekt inne i andre muterbare objekt.

### Tallrepresentasjon og avrundingsfeil

I Python, som i mange andre programmeringsspråk, blir flyttal representert ved hjelp av IEEE 754-standarden for flyttalsrepresentasjon. Denne standarden gjer det mogleg å representere svært store og svært små tal, men det kjem med nokre utfordringar knytt til nøyaktigheit og representasjon av visse verdiar. 

#### Avrundingsfeil

Flyttalsrepresentasjon i datamaskinar kan ikkje alltid nøyaktig representere alle tal. Dette kjem av at flyttal er lagra som ein kombinasjon av eit mantisse og ein eksponent i binært format. Sidan ikkje alle desimaltal har ein eksakt binær representasjon, kan dette føre til små feil når tal blir lagra og rekna med.

Til dømes vil tal som \(0.1\) ikkje ha ein eksakt binær representasjon, noko som gjer at slike tal blir avrunda til nærmaste representerbare verdi. Dette kan føre til at rekneoperasjonar gir resultat som er litt unøyaktige.

#### `float.as_integer_ratio()`
Python har ein innebygd metode som kan hjelpe med å forstå korleis eit flyttal blir representert som ein brøk av to heiltal. Metoden `as_integer_ratio()` returnerer to heiltal som representerer flyttalet som ein brøk.

```python
x = 0.125
print(x.as_integer_ratio())  # (1, 8)
```

**Forklaring**:
- Tallet \(0.125\) kan eksakt representerast som brøken \( \frac{1}{8} \). Derfor returnerer `x.as_integer_ratio()` tuple `(1, 8)`, som betyr at \(0.125 = \frac{1}{8}\).

#### Typiske feller og unngåing

Når ein jobbar med flyttal i programmering, kan ein støte på fleire typiske feller. Ein av desse er at når ein utfører addisjon eller subtraksjon med svært store eller svært små tal, kan nøyaktigheita gå tapt.

```python
# Feil grunna addisjon/subtraksjon
a = 1e20
b = 1
c = 1e20 + 1 - 1e20
print(c)  # 0, ikkje 1
```

**Forklaring**:
- I uttrykket `1e20 + 1`, er `1e20` så mykje større enn `1` at når dei blir lagt saman, er den faktiske verdien av `1` for liten til å påverke resultatet. Når du deretter trekker frå `1e20`, blir talet `1` "borte", og resultatet blir `0` i staden for `1`.

**Løysing**:
- Ein måte å unngå dette problemet på er å endre rekkefølga av operasjonane, slik at operasjonar med tal av liknande størrelsesorden blir utført først.

```python
# Unngå gjennom rangerekkefølge:
d = (1e20 - 1e20) + 1
print(d)  # 1
```

**Forklaring**:
- Her blir `1e20` trekt frå `1e20` først, som gir `0`. Deretter blir `1` lagt til, noko som gir det korrekte resultatet `1`.

#### Overflyt og underflyt

Overflyt og underflyt er fenomen som kan oppstå når eit tall blir for stort eller for lite til å kunne representerast i flyttalsformat.

- **Overflyt** skjer når eit tal blir større enn det største talet som kan representerast av datamaskinen i flyttalsformat.
- **Underflyt** skjer når eit tal blir så nært null at det ikkje lenger kan representerast nøyaktig og derfor blir avrunda til null.

```python
import sys
print(sys.float_info.max)  # Største representable flyttal
print(sys.float_info.min)  # Minste positive representable flyttal
```

**Forklaring**:
- `sys.float_info.max` gir det største flyttalet som kan representerast i Python. Hvis eit rekneuttrykk gir eit resultat som er større enn dette talet, vil overflyt skje, og Python vil typisk returnere `inf` (uendelegheit).
- `sys.float_info.min` gir den minste positive flyttalsverdien som kan representerast. Tal mindre enn dette vil resultere i underflyt, der resultatet blir avrunda til null.

**Eksempel på overflyt**:
```python
x = 1e308 * 10  # For stort tal for standard float
print(x)  # inf
```

**Eksempel på underflyt**:
```python
y = 1e-324 / 10  # For lite tal for standard float
print(y)  # 0.0
```

Dette gjer det viktig å vere oppmerksam på dei fysiske grensene for talrepresentasjon i flyttalsformat, spesielt når ein jobbar med ekstreme tal.


## Gjennomgangsspørsmål:

<details>
    <summary>1. Kva er forskjellen på `if`, `if-else` og `if-elif-else` setningar?</summary>
    
    `if`-setningar blir brukt til å utføre ein blokk med kode dersom ein bestemt betingelse er sann.  
    `if-else`-setningar legg til ein alternativ blokk med kode som skal utførast dersom betingelsen ikkje er sann.  
    `if-elif-else`-setningar gir moglegheit til å sjekke fleire betingelsar i rekkefølge, og utføre ulike blokker med kode avhengig av kva betingelse som er sann.
</details>

<details>
    <summary>2. Korleis fungerer ein `while`-løkke samanlikna med ein `for`-løkke?</summary>
    
    Ein `while`-løkke køyrer så lenge ein gitt betingelse er sann. Han er nyttig når du ikkje på førehand veit kor mange gonger løkka skal køyrast.  
    Ein `for`-løkke itererer over ein sekvens (som ei liste, eit strengt objekt, eller ein rekke med tal) eit bestemt antal gonger.
</details>

<details>
    <summary>3. Forklar forskjellen på muterbare og immuterbare datatyper.</summary>
    
    Muterbare datatyper, som lister og ordbøker, kan endrast etter at dei er oppretta.  
    Immuterbare datatyper, som strenger og tuplar, kan ikkje endrast etter at dei er oppretta.
</details>

<details>
    <summary>4. Kva skjer når du brukar `+=` operatoren på ei liste?</summary>
    
    Når du brukar `+=` på ei liste, legg du til elementa frå høgresida av uttrykket til slutten av lista.  
    Dette kan vere eit einskilt element eller fleire element (som i ein annan liste).
</details>

<details>
    <summary>5. Vis korleis du kan iterere gjennom ein liste både per element og per indeks.</summary>
    
    Iterere per element:
    ```python
    for element in lista:
        print(element)
    ```

    Iterere per indeks:
    ```python
    for i in range(len(lista)):
        print(lista[i])
    ```
</details>

<details>
    <summary>6. Kva er avrundingsfeil, og kvifor oppstår dei?</summary>
    
    Avrundingsfeil oppstår fordi flyttal ikkje alltid kan representerast nøyaktig i binært format. Dette fører til små unøyaktigheiter i rekneoperasjonar.
</details>

<details>
    <summary>7. Gi eit døme på overflyt og underflyt.</summary>
    
    Overflyt skjer når eit tal blir for stort til å representerast og resulterer i uendelegheit (`inf`).  
    Underflyt skjer når eit tal er for lite og blir avrunda til null.

    Eksempel på overflyt:
    ```python
    x = 1e308 * 10  # For stort tal for standard float
    print(x)  # inf
    ```

    Eksempel på underflyt:
    ```python
    y = 1e-324 / 10  # For lite tal for standard float
    print(y)  # 0.0
    ```
</details>

<details>
    <summary>8. Forklar korleis `copy()` og `deepcopy()` fungerer i Python.</summary>
    
    `copy()` lagar ein grunn kopi (shallow copy) av eit objekt, noko som betyr at berre sjølve objektet blir kopiert, men ikkje dei objekta det refererer til.  
    `deepcopy()` lagar ein dyp kopi (deep copy), der alle nivå av referansar blir kopiert, noko som resulterer i ein heilt uavhengig kopi.
</details>

<details>
    <summary>9. Kva er ein tuple, og kva er fordelen med å bruke ein tuple i staden for ei liste?</summary>
    
    Ein tuple er ein uforanderleg (immutable) sekvens av element. Fordelen med å bruke ein tuple i staden for ei liste er at han er uforanderleg, noko som kan beskytte data frå utilsikta endringar og kan vere litt meir effektivt i minnebruk.
</details>

<details>
    <summary>10. Kva er forskjellen på ein `set` og ei liste i Python?</summary>
    
    Ein `set` er ei uordna samling av unike element, medan ei liste er ein ordna sekvens av element som kan innehalde duplikat. Set er spesielt nyttige når du treng å sikre at alle elementa er unike, eller når du treng rask testing av medlemskap.
</details>

<details>
    <summary>11. Forklar korleis `range()` funksjonen fungerer i ein for-løkke.</summary>
    
    `range()` funksjonen genererer ein sekvens av tal som kan brukast til å iterere eit bestemt antal gonger i ein for-løkke. Du kan spesifisere startverdi, stop-verdi og stegstorleik. Standard verdiane er start = 0, og stegstorleik = 1.
</details>

<details>
    <summary>12. Kva er `None` i Python, og kva er typiske bruksområder for `None`?</summary>
    
    `None` representerer mangelen på ein verdi eller ei tom verdi i Python. Han blir ofte brukt som standardverdi i funksjonsargument, eller for å indikere at ei variabel ikkje har fått tildelt ein verdi enno.
</details>

<details>
    <summary>13. Korleis kan du sjekke om eit objekt er av ein bestemt datatype i Python?</summary>
    
    Du kan bruke `isinstance(obj, datatype)` funksjonen for å sjekke om eit objekt er av ein bestemt datatype. Til dømes, `isinstance(5, int)` vil returnere `True` fordi 5 er eit heiltal (`int`).
</details>

<details>
    <summary>14. Forklar kva som skjer når du utfører `a = b` der både `a` og `b` er lister.</summary>
    
    Når du utfører `a = b`, vil `a` peike til same objekt som `b` i minnet. Endringar gjort på `a` vil også reflektere seg i `b` og omvendt, sidan dei refererer til same liste.
</details>

<details>
    <summary>15. Korleis kan du unngå avrundingsfeil når du jobbar med monetære verdiar i Python?</summary>
    
    For å unngå avrundingsfeil når du jobbar med monetære verdiar, kan du bruke `decimal`-modulen i Python, som gir meir nøyaktig flyttalsrekning ved å tillate deg å spesifisere nøyaktigheit.
</details>

<details>
    <summary>16. Kva er sys.float_info i Python, og kva informasjon gir det deg?</summary>
    
    `sys.float_info` gir deg informasjon om eigenskapane til flyttalsrepresentasjon i Python, som den største og minste representable verdien (`max` og `min`), epsilon-verdien (`epsilon`), og fleire andre eigenskapar relatert til flyttalsberekningar.
</details>

---