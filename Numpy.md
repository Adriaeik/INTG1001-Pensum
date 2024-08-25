
## Table of Contents
1. [Grunnleggende om NumPy](#Grunnleggende-om-NumPy)
2. [Vanlige Matematikkfunksjoner i NumPy](#Vanlige-Matematikkfunksjoner-i-NumPy)
3. [Oppretting og Modifisering av Arrays](#Oppretting-og-Modifisering-av-Arrays)
4. [Indeksering og Slicing i Arrays](#Indeksering-og-Slicing-i-Arrays)
5. [Beregningsoperasjoner med NumPy](#Beregningsoperasjoner-med-NumPy)
6. [Inn- og Utdata med NumPy Arrays](#Inn--og-Utdata-med-NumPy-Arrays)
7. [Tilfeldige Tall med NumPy](#Tilfeldige-Tall-med-NumPy)
8. [Oppsummering](#Oppsummering)
9. [Repetisjonsspørsmål](#Repetisjonsspørsmål)
10. [Svar på Repetisjonsspørsmål](#Svar-på-Repetisjonsspørsmål)

## Grunnleggende om NumPy
NumPy er et kraftig bibliotek for numeriske beregninger i Python. Det er spesielt nyttig i ingeniørfag for å håndtere store datamengder og komplekse matematiske operasjoner. Vi begynner med å importere NumPy og sette et alias:

```python
import numpy as np
```

Ved å bruke `import numpy as np`, kan vi referere til NumPy som `np`, noe som gjør koden kortere og mer lesbar.

## Vanlige Matematikkfunksjoner i NumPy
NumPy tilbyr flere innebygde matematiske konstanter og funksjoner som er nyttige i beregninger.

Eksempler på konstanter:
- $\pi$: `np.pi`
- $e$: `np.e`

Eksempler på funksjoner:
- Kvadratrot: `np.sqrt()`
- Sinus: `np.sin()`
- Cosinus: `np.cos()`
- Avrunding: `np.round()`
- Absoluttverdien: `np.abs()`
- Logaritme: `np.log()`
- Eksponentialfunksjon: `np.exp()`

## Oppretting og Modifisering av Arrays
NumPy gir flere metoder for å opprette arrays:

```python
# Enkel array fra liste
array1 = np.array([1, 2, 3, 4])
print(array1)

# Range med arange
array2 = np.arange(0, 10, 2)
print(array2)

# Linje mellomrom med linspace
array3 = np.linspace(0, 1, 5)
print(array3)

# Nuller og enere arrays
array4 = np.zeros((3, 3))
print(array4)

array5 = np.ones((2, 2))
print(array5)
```

Vi kan også sjekke og konvertere datatyper i array:

```python
# Sjekke datatype
print(array1.dtype)

# Konvertere til en annen datatype
array1_float = array1.astype(float)
print(array1_float)
```

### Omforming av Arrays
Vi kan endre formen på arrays med `resize` og `transpose`:

```python
# Endre størrelse
array6 = np.array([1, 2, 3, 4, 5, 6])
array6.resize(2, 3)
print(array6)

# Transponere en 2D array
array7 = np.array([[1, 2, 3], [4, 5, 6]])
array7_T = np.transpose(array7)
print(array7_T)
```

## Indeksering og Slicing i Arrays
Indeksering og slicing tillater tilgang til og modifikasjon av bestemte deler av arrays.

### 1D-array
```python
# Tilgang til elementer
print(array1[1])  # Gir 2
# Slicing
print(array1[1:3])  # Gir [2, 3]
```

### 2D-array
```python
# Tilgang til enkelt element
print(array7[1, 2])  # Gir 6

# Slicing
print(array7[:, 1])  # Gir [2, 5]
print(array7[1, :])  # Gir [4, 5, 6]
```

## Beregningsoperasjoner med NumPy
Vi kan utføre operasjoner på hele arrays:

```python
array8 = np.array([1, 2, 3])
array9 = np.array([4, 5, 6])

# Element-wise operasjoner
print(array8 + array9)  # Gir [5, 7, 9]

# Skalare operasjoner
print(array8 * 2)  # Gir [2, 4, 6]
```

For noen operasjoner, må vi bruke løkker:

```python
# Løkke for spesialiserte operasjoner
result = np.zeros_like(array8)
for i in range(array8.size):
    result[i] = array8[i] + array9[i]
print(result)
```

## Inn- og Utdata med NumPy Arrays
NumPy tilbyr flere metoder for inn- og utdata:

```python
# Laste fra tekstfil
data = np.loadtxt('data.txt')
print(data)

# Lagre til tekstfil
np.savetxt('output.txt', array8)
```

## Tilfeldige Tall med NumPy
NumPy inneholder flere metoder for å generere arrays med tilfeldige tall:

```python
# Tilfeldige tall mellom 0 og 1
rand_array = np.random.rand(3, 2)
print(rand_array)

# Tilfeldige heltall
randint_array = np.random.randint(0, 10, (3, 3))
print(randint_array)

# Tilfeldig valg fra liste
choice_array = np.random.choice([1, 2, 3, 4], size=3)
print(choice_array)

# Shuffle en array
np.random.shuffle(array1)
print(array1)
```

## Oppsummering
Vi har dekket grunnleggende funksjoner og metoder i NumPy, fra grunnleggende matematiske operasjoner til bruk av tilfeldige tall og inn- og utdata-metoder. NumPy er et essensielt verktøy i ingeniørfag for å håndtere statistiske data, komplekse beregninger og store datamengder effektivt.

## Repetisjonsspørsmål
<details>
    <summary>1. Hva er aliaset for å importere NumPy?</summary>
    `np`
</details>

<details>
    <summary>2. Skriv en funksjon som lager en 2x2 matrix med nuller.</summary>
    `np.zeros((2, 2))`
</details>

<details>
    <summary>3. Hvordan endrer man datatype på en array til float?</summary>
    `array.astype(float)`
</details>

<details>
    <summary>4. Hva returnerer `np.arange(0, 10, 2)`?</summary>
    `[0, 2, 4, 6, 8]`
</details>

<details>
    <summary>5. Hvordan transponerer du en 2D array `a`?</summary>
    `np.transpose(a)`
</details>

<details>
    <summary>6. Hva gjør funksjonen `np.random.shuffle()`?</summary>
    Den stokker elementene i en array tilfeldig.
</details>

<details>
    <summary>7. Hvordan lagrer du en array til en tekstfil i NumPy?</summary>
    `np.savetxt('filename.txt', array)`
</details>

<details>
    <summary>8. Skriv et eksempel på indeksere 2D array for å få siste raden.</summary>
    `array[-1, :]`
</details>
