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

I Python, som i mange andre programmeringsspråk, er det viktig å forstå operatorpresedens for å kunne skrive korrekt kode som utfører operasjonar i den rekkefølga du forventar. Operatorpresedens bestemmer i kva rekkefølge operasjonane i eit uttrykk blir evaluert, spesielt når fleire operatorar er involvert. Dersom du ikkje er bevisst på presedensen, kan koden gi uventa resultat. Du kan alltid bruke parentesar `()` for å tvinge fram ein annan rekkefølge på operasjonane enn det som er bestemt av den innebygde presedensen.

#### Operasjonar blir utført i følgande rekkefølge:

1. **Parenteser `()`**:
   - Uttrykk inne i parentesar blir alltid evaluert først. Dette gir deg moglegheit til å overstyre den innebygde presedensen og tvinge fram ein spesifikk rekkefølge av operasjonar.
   
2. **Eksponentiering `**`**:
   - Eksponentiering blir utført etter parentesar, men før andre aritmetiske operasjonar som multiplikasjon og divisjon.

3. **Negasjon og bitvis NOT `-` og `~`**:
   - Einærs operatorar, som negativ (-) og bitvis NOT (`~`), blir evaluert før binære aritmetiske operatorar.

4. **Multiplikasjon, divisjon, gulvdivisjon, modulus `*`, `/`, `//`, `%`**:
   - Desse operasjonane har høgare presedens enn addisjon og subtraksjon, men lågare enn eksponentiering.

5. **Addisjon og subtraksjon `+`, `-`**:
   - Evaluert etter multiplikasjon og divisjon.

6. **Skiftoperasjonar `<<`, `>>`**:
   - Utfører bitvis forskyving av bitmønster til venstre eller høgre.

7. **Bitvise operatorar AND, XOR, OR `&`, `^`, `|`**:
   - Utfører operasjonar bit for bit, med AND (`&`), XOR (`^`), og OR (`|`) som blir evaluert i denne rekkefølga.

8. **Komparasjonar `<`, `<=`, `>`, `>=`, `==`, `!=`**:
   - Brukt til å samanlikne verdiar, og evaluert etter aritmetiske og bitvise operasjonar.

9. **Logiske NOT, AND, OR `not`, `and`, `or`**:
   - Evaluert til slutt, med `not` som har høgast presedens, etterfulgt av `and`, og deretter `or`.

#### Eksempel:
```python
# Uten parenteser
result = 3 + 4 * 2  # result blir 11, ikkje 14
```
**Forklaring**:
- Her blir multiplikasjonen `4 * 2` utført først, og deretter blir resultatet lagt til `3`, som gir `11`.

```python
# Med parenteser
result_parens = (3 + 4) * 2  # result_parens blir 14
```
**Forklaring**:
- Ved å bruke parentesar, blir `3 + 4` evaluert først, og deretter blir resultatet multiplisert med `2`, som gir `14`.

### Kva skjer utan rett bruk av parentesar?

Feil forståing av operatorpresedens kan føre til feil i programmet som kan vere vanskelege å finne, spesielt i meir komplekse uttrykk. La oss sjå på eit meir avansert eksempel:

```python
x = 2
y = 3
z = 4

result = x + y * z ** 2
```

**Forklaring**:
- Her vil `z ** 2` bli evaluert først (fordi eksponentiering har høgare presedens), deretter `y * (z ** 2)`, og til slutt vil resultatet bli lagt til `x`.
- Dette gir følgande rekkefølge: `2 + 3 * (4 ** 2) = 2 + 3 * 16 = 2 + 48 = 50`.

Men om du ønskar å prioritere addisjonen før multiplikasjonen og eksponentieringa, kan du bruke parentesar:

```python
result_parens = (x + y) * z ** 2
```

**Forklaring**:
- Med parentesar rundt `x + y`, vil denne delen bli evaluert først, deretter vil resultatet bli multiplisert med `z ** 2`.
- Dette gir følgande rekkefølge: `(2 + 3) * (4 ** 2) = 5 * 16 = 80`.

Å forstå og bruke riktig operatorpresedens er essensielt for å unngå logiske feil og sikre at uttrykka dine gir dei forventa resultata.

## Variable og Tilordning

### Tilordningsoperatoren

Variabler tildeles verdier ved bruk av likhetstegnet `=`:
```python
x = 10
```

### Sammensatt Tilordning

Dei samansette tilordningsoperatorane i Python kombinerer ein aritmetisk operasjon med ei tilordning, slik at verdien av ei variabel kan oppdaterast på ein konsis og effektiv måte. Dette kan gjere koden meir kompakt og lettare å lese.

Her er ei oversikt over vanlege samansette tilordningsoperatorar:

- `+=` : Legger til ein verdi og tildeler resultatet tilbake til variabelen.
- `-=` : Trekker frå ein verdi og tildeler resultatet tilbake til variabelen.
- `*=` : Multipliserer med ein verdi og tildeler resultatet tilbake til variabelen.
- `/=` : Dividerer med ein verdi og tildeler resultatet tilbake til variabelen. Resultatet blir eit flyttal (`float`).
- `//=` : Heiltallsdividerer med ein verdi og tildeler resultatet tilbake til variabelen. Resultatet blir heiltalsdelen av divisjonen.
- `%=` : Utfører modulusoperasjon (resten av divisjonen) og tildeler resultatet tilbake til variabelen.
- `**=` : Eksponentierer med ein verdi og tildeler resultatet tilbake til variabelen.

**Eksempel**:

```python
x = 5
x += 3  # x blir 8 (5 + 3)
x -= 2  # x blir 6 (8 - 2)
x *= 4  # x blir 24 (6 * 4)
x /= 6  # x blir 4.0 (24 / 6)
x //= 2 # x blir 2.0 (4.0 // 2) - heiltallsdivisjon, gir resultat som eit flyttal her
x %= 2  # x blir 0.0 (2.0 % 2)
x **= 3 # x blir 0.0 (0.0 ** 3)
```

**Merk**:
- I Python, når du bruker `/=`, vil resultatet alltid vere eit flyttal, sjølv om både operanden og resultatet eigentleg kunne vere heiltal. For eksempel vil `10 /= 2` gi `5.0` og ikkje `5`.
- Når du bruker `//=` med eit heiltal, vil resultatet vere eit heiltal. Men om `x` allereie er eit flyttal før operasjonen, vil resultatet etter `//=` også vere eit flyttal.

Denne typen samansatte tilordningsoperatorar kan også brukast på andre objekt som lister, sett, og strenger, avhengig av kva type operasjon dei støttar. Til dømes kan `+=` operatoren brukast til å legge til element i ei liste:

```python
lista = [1, 2, 3]
lista += [4, 5]  # lista blir [1, 2, 3, 4, 5]
```

Å bruke samansette tilordningsoperatorar kan bidra til meir konsis og lesbar kode, spesielt når du treng å oppdatere verdien av ei variabel basert på seg sjølv.

### Tilordninger til Samme vs. Ulike Objekt

I Python kan to variablar peike til det same objektet i minnet, noko som er viktig å forstå, spesielt når ein jobbar med muterbare objekt som lister, ordbøker, eller sett. Når to variablar refererer til det same muterbare objektet, vil alle endringar som blir gjort gjennom éi variabel, også vere synlege gjennom den andre variabelen.

#### Tilordning til same objekt

Når du tilordnar ein variabel til ein annan variabel som peiker til det same muterbare objektet, vil begge variablane referere til det same objektet i minnet. Dette betyr at endringar i objektet gjennom éi variabel vil reflektere seg i den andre.

**Eksempel**:
```python
a = [1, 2, 3]
b = a  # b peiker til same objekt som a
b.append(4)
print(a)  # [1, 2, 3, 4]
```

**Forklaring**:
- Når `b = a`, blir ingen ny kopi av lista oppretta. I staden peiker `b` til den same lista som `a`. Dermed, når du legg til `4` i lista via `b.append(4)`, vil endringa også vere synleg via `a`, fordi dei begge peiker til den same lista.

#### Tilordning til ulike objekt

For å lage ein uavhengig kopi av eit muterbart objekt, slik at endringar i ein variabel ikkje påverkar den andre, kan du bruke funksjonar som `copy()` for å lage ein grunn kopi, eller `deepcopy()` for å lage ein dyp kopi dersom objektet inneheld andre muterbare objekt.

**Eksempel med `deepcopy()`**:
```python
from copy import deepcopy
a = [1, 2, 3]
b = deepcopy(a)  # b peiker til eit nytt og uavhengig objekt
b.append(4)
print(a)  # [1, 2, 3]
```

**Forklaring**:
- Ved å bruke `deepcopy()`, blir ein fullstendig uavhengig kopi av lista `a` oppretta og tildelt `b`. Dette betyr at endringar gjort i `b` (som å legge til `4`) ikkje påverkar `a`. Dermed forblir `a` uendra, medan `b` inneheld den nye verdien.

**Merk**:
- **Grunn kopi (`copy.copy()`)**: Kopierer berre det ytste nivået av objektet. Hvis objektet inneheld andre muterbare objekt, vil desse ikkje bli kopiert, og endringar i dei vil framleis reflekterast i både originalen og kopien.
- **Dyp kopi (`copy.deepcopy()`)**: Kopierer heile objektet, inkludert alle muterbare objekt det inneheld. Dette gir full separasjon mellom originalen og kopien, slik at endringar i eitt objekt ikkje påverkar det andre.

Å forstå forskjellen mellom tilordning til same objekt og ulike objekt er avgjerande for å unngå utilsikta sideeffektar i koden din, spesielt når du arbeider med komplekse datastrukturar.

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

I Python er det viktig å forstå forskjellen mellom muterbare og immuterbare datatyper, da dette påvirker korleis objekt kan endrast etter at dei er oppretta, og korleis dei oppfører seg når dei blir brukt i tilordningar og funksjonar.

#### Muterbare Datatyper

Muterbare typar er datastrukturar som kan endrast etter oppretting. Dette betyr at du kan oppdatere, legge til, eller fjerne element frå desse objekta utan å måtte opprette eit nytt objekt. Typiske eksempel på muterbare typar inkluderer:

- **`list`**: Ei liste der du kan endre individuelle element, legge til nye element, eller fjerne eksisterande.
- **`dict`**: Ein ordbok der du kan oppdatere eksisterande nøkkel-verdi-par, legge til nye, eller fjerne eksisterande.

**Eksempel på muterbare typar**:
```python
my_list = [1, 2, 3]
my_list[0] = 9  # Endrer første element til 9
print(my_list)  # [9, 2, 3]
```

#### Immuterbare Datatyper

Immuterbare typar kan ikkje endrast etter at dei er oppretta. Dette betyr at dersom du vil endre innhaldet i eit immuterbart objekt, må du opprette eit nytt objekt med dei ønskede verdiane. Typiske eksempel på immuterbare typar inkluderer:

- **`tuple`**: Ein uforanderleg sekvens av element.
- **`string`**: Ein sekvens av teikn som ikkje kan endrast etter oppretting.
- **`int`, `float`, `bool`**: Tall- og boolske verdiar som også er immuterbare.

**Eksempel på immuterbare typar**:
```python
my_tuple = (1, 2, 3)
try:
    my_tuple[0] = 9  # Feil! Kan ikke endre innholdet i en tuple
except TypeError as e:
    print(e)  # Output: 'tuple' object does not support item assignment
```

#### Bruk av `copy()` og `deepcopy()` for Muterbare Data

Når du arbeider med muterbare objekt, kan det vere situasjonar der du treng å lage ein kopi av eit objekt. Python tilbyr to metodar for dette: `copy()` for å lage ein grunn kopi og `deepcopy()` for å lage ein dyp kopi.

- **Grunn kopi (`copy.copy()`)**: Kopierer det ytste nivået av objektet. Dersom objektet inneheld andre muterbare objekt, vil desse ikkje bli kopiert, noko som betyr at dei refererer til dei same underobjekta.
  
- **Dyp kopi (`copy.deepcopy()`)**: Kopierer heile objektet, inkludert alle muterbare objekt det inneheld. Dette skaper eit heilt uavhengig objekt der endringar i kopien ikkje påverkar originalen.

**Eksempel på bruk av `copy()` og `deepcopy()`**:
```python
from copy import deepcopy

original_list = [1, 2, [3, 4]]
shallow_copy = original_list.copy()  # Grunn kopi
deep_copy = deepcopy(original_list)  # Dyp kopi

shallow_copy[2].append(5)
print(original_list)  # [1, 2, [3, 4, 5]] - Grunn kopien deler same underliste
print(deep_copy)  # [1, 2, [3, 4]] - Dyp kopien er uavhengig
```

**Forklaring**:
- Når du bruker `shallow_copy`, vil endringar i den innstøypte lista også reflektere i `original_list`, fordi dei deler same referanse til denne lista.
- Når du bruker `deep_copy`, vil den innstøypte lista vere ein uavhengig kopi, slik at endringar i kopien ikkje påverkar originalen.

Å forstå forskjellen mellom muterbare og immuterbare objekt er essensielt for å unngå utilsikta endringar i data, spesielt når du arbeider med komplekse datastrukturar eller samarbeider på tvers av ulike delar av eit program.

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

Overflyt og underflyt er to vanlege problem som kan oppstå når du arbeider med numeriske berekningar i Python, spesielt når du handterer svært store eller svært små tal.

#### Overflyt

Overflyt skjer når eit tal blir for stort til å kunne representerast av den valde datatype. I Python, som bruker IEEE 754-standarden for flyttalsrepresentasjon, vil store tal som ikkje kan representerast, ofte resultere i ei `OverflowError` eller føre til at resultatet blir `inf` (uendelegheit).

**Eksempel på overflyt**:
```python
import math
try:
    result = math.exp(1000)  # Forsøk på å berekne e^1000
except OverflowError as e:
    print(e)  # Output: math range error
```

**Forklaring**:
- I dette eksempelet prøver `math.exp(1000)` å berekne verdien av \(e^{1000}\). Dette talet er ekstremt stort og overstig den øvre grensa for kva som kan representerast som eit flyttal i Python, noko som resulterer i ei `OverflowError`.

#### Underflyt

Underflyt skjer når eit tal blir så nær null at det ikkje kan representerast nøyaktig i flyttalsformatet, og blir derfor avrunda til null. Dette kan skje når ein deler svært små tal eller multipliserer med svært små verdier.

**Eksempel på underflyt**:
```python
underflow_result = 1e-308 / 1e308
print(underflow_result)  # 0.0
```

**Forklaring**:
- I dette eksempelet blir eit svært lite tal (`1e-308`) delt på eit svært stort tal (`1e308`). Resultatet er så nær null at det ikkje kan representerast som eit flyttal, og Python avrundar det til `0.0`.

#### Unngåing av Overflyt og Underflyt

For å unngå problem med overflyt og underflyt kan du vurdere følgande strategiar:

1. **Skalering av problemet**:
   - Om mogleg, kan du skalere tal innanfor eit representerbart område før du utfører berekningar. Til dømes kan du utføre operasjonar i logaritmisk skala for å unngå ekstremt store eller små tal.

2. **Bruk av `decimal`-modulen**:
   - For situasjonar som krev høgare nøyaktigheit eller handtering av svært store tal, kan du bruke Python sitt `decimal`-modul som tilbyr flyttalsrekning med vilkårleg presisjon.

   **Eksempel med `decimal`**:
   ```python
   from decimal import Decimal, getcontext
   getcontext().prec = 50  # Setjar presisjonen til 50 desimalar

   large_number = Decimal('1e1000')
   small_number = Decimal('1e-1000')

   print(large_number + small_number)  # Vil ikkje føre til overflyt eller underflyt
   ```

3. **Feilhandsaming**:
   - Alltid handter potensielle `OverflowError`- og `UnderflowError`-tilfelle med `try-except`-blokk, som i eksempla over, for å sikre at programmet ditt ikkje krasjar ved uventa verdier.

Å vere medviten om og handtere potensielle overflyt- og underflytsproblem er essensielt i program som jobbar med numeriske berekningar, spesielt i vitskapeleg databehandling eller finansielle applikasjonar der presisjon er avgjerande.

## Oppsummering av Veke 34
I denne veka har vi gjennomgått uttrykk og variable i Python. Vi har sett på forskjellige typer operatorer og hvordan de brukes, inkludert aritmetiske og logiske operatorer. Vi har også diskutert variabeltilordning, både med enkel og sammensatt tilordning, og sett forskjellen mellom muterbare og immuterbare datatyper samt deres bruk med shallow og deep copy. Avslutningsvis undersøkte vi flyttallsrepresentasjon, avrundingsfeil, og problemene knyttet til overflyt og underflyt.

## Repetisjonsspørsmål

<details>
    <summary>1. Hva er et beskyttet ord i Python?</summary>
    Et beskyttet ord er et reserverte ord i Python som ikke kan brukes som variabelnavn, f.eks. `while`, `for`, `if`.
</details>

<details>
    <summary>2. Hvordan fungerer heltallsdivisjon i Python, og hvilken operator brukes?</summary>
    Heltallsdivisjon deler én verdi med en annen og runder ned til nærmeste heltall; operatoren er `//`.
</details>

<details>
    <summary>3. Forklar forskjellen mellom `is` og `==`.</summary>
    `is` sjekker om to variabler refererer til samme objekt, mens `==` sjekker om verdiene til variablene er like.
</details>

<details>
    <summary>4. Hva er operatorpresedens, og hvorfor er det viktig?</summary>
    Operatorpresedens bestemmer rekkefølgen operasjoner utføres i et uttrykk. Det er viktig for å unngå feilaktige beregninger.
</details>

<details>
    <summary>5. Hvordan kan man unngå avrundingsfeil ved manipulering av flyttall?</summary>
    Avrundingsfeil kan unngås ved å omorganisere beregningene eller bruke numeriske metoder som intervalleanalyse.
</details>

<details>
    <summary>6. Forklar forskjellen mellom muterbare og immuterbare datatyper.</summary>
    Muterbare datatyper kan endres etter at de er opprettet (f.eks. `list`), mens immuterbare typer ikke kan endres (f.eks. `tuple`).
</details>

<details>
    <summary>7. Nevn to eksempler på sammensatte tilordningsoperatorer og hvordan de brukes.</summary>
    To eksempler på sammensatte tilordningsoperatorer er `+=` (x += 2) og `*=` (x *= 2).
</details>

<details>
    <summary>8. Hva mener vi med overflyt og underflyt i numeriske beregninger?</summary>
    Overflyt skjer når et tall er for stort til å representeres av typen, mens underflyt skjer når et tall er for nært null for å kunne representeres nøyaktig.
</details>


