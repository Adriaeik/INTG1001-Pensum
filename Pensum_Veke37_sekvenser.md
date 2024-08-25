
## Innholdsfortegnelse
1. [Sekvenser](#sekvenser)
    1. [Strenger](#strenger)
    2. [Tupler](#tupler)
    3. [Lister](#lister)
2. [Eksempler og Øvingar](#eksempler-og-øvingar)
3. [Repitisjonsspørsmål](#repitisjonsspørsmål)
4. [Svar på repitisjonsspørsmål](#svar-på-repitisjonsspørsmål)

## Sekvenser

### Strenger
Strenger er sekvenser av tegn og blir brukt til å representere tekst. Strenger kan definerast ved hjelp av enkeltfnuttar (`'`), dobbeltfnuttar (`"`), eller trippelfnuttar (`'''` eller `"""`) for flern linjetekst.

**Eksempel:**
```python
streng1 = 'Dette er ein streng'
streng2 = "Dette er også ein streng"
streng3 = '''Dette er ein
flern linjestreng'''
```

#### Strengkonkatenering (+) og repetering (*)
Du kan slå saman (konkatenering) to strenger med `+` og repetere ei streng med `*`.

**Eksempel:**
```python
streng = 'Hei' + ' verda!'
print(streng)  # Output: Hei verda!

repetert_streng = 'Hei! ' * 3
print(repetert_streng)  # Output: Hei! Hei! Hei!
```

#### Indeksering og slicing
Indeksering lar deg få tilgang til enkel-tegn i ei streng ved hjelp av indeksar, der første teiknet har indeks 0. Slicing lar deg hente ut eit utsnitt av strengen.

**Eksempel:**
```python
streng = 'Hei verda!'
første_teikn = streng[0]
uer = streng[4:7]

print(første_teikn)  # Output: H
print(uer)          # Output: ver
```

#### Vanlige sekvensfunksjoner og -metoder
- `len()`: Returnerer lengda på sekvensen.
- `min()`: Returnerer minste elementet.
- `max()`: Returnerer største elementet.
- `count()`: Teler kor mange ganger eit element oppstår.
- `index()`: Returnerer indeksen til første opptreden av eit element.

**Eksempel:**
```python
streng = 'Hei verda!'
print(len(streng))      # Output: 10
print(min(streng))      # Output: ' '
print(max(streng))      # Output: 'v'
print(streng.count('e')) # Output: 2
print(streng.index('v')) # Output: 4
```

#### F-strenger
F-strenger (format-strenger) tillater enkle og oversiktlige formateringsoperasjoner.

**Eksempel:**
```python
namn = 'Verda'
alder = 2023
utskrift = f'Hei {namn}, du er {alder} år!'
print(utskrift)  # Output: Hei Verda, du er 2023 år!
```

#### Vanlige strengmetoder
- `strip()`: Fjerner mellomrom frå start og slutt.
- `split()`: Splittar strengen ved oppgjeve separator.
- `join()`: Slår saman element i ei liste til ei streng.
- `upper()`: Konverterer strengen til store bokstavar.
- `lower()`: Konverterer strengen til små bokstavar.
- `replace()`: Erstatta del av strengen med ein annan streng.
- `isdigit()`: Sjekkar om alle teikn i strengen er sifre.

**Eksempel:**
```python
streng = '  Hei Verda!  '
print(streng.strip())          # Output: Hei Verda!
print('Hei Verda!'.split())    # Output: ['Hei', 'Verda!']
print(' '.join(['Hei', 'Verda!'])) # Output: Hei Verda!
print('hei verda!'.upper())    # Output: HEI VERDA!
print('HEI VERDA!'.lower())    # Output: hei verda!
print('Hei Verda!'.replace('Hei', 'Hallo')) # Output: Hallo Verda!
print('123'.isdigit())         # Output: True
print('123a'.isdigit())        # Output: False
```

### Tupler
Tupler er uforanderlige sekvenser som bruker parentesar for å bli definert.

**Eksempel:**
```python
tuppel = (1, 2, 3, 'ein', 'to')
første_element = tuppel[0]
siste_element = tuppel[-1]

print(første_element)  # Output: 1
print(siste_element)   # Output: to
```

### Lister
Lister er foranderlige sekvenser som bruker klammeparentesar for å bli definert.

**Eksempel:**
```python
liste = [1, 2, 3, 'ein', 'to']
første_element = liste[0]
siste_element = liste[-1]

print(første_element)  # Output: 1
print(siste_element)   # Output: to
```

#### Vanlige listemetoder
- `append()`: Legg til eit element på slutten av lista.
- `insert()`: Set inn eit element på ein gitt posisjon.
- `remove()`: Fjerna første oppstanden av eit element.
- `pop()`: Fjerna og returner element ved gitt posisjon.
- `sort()`: Sorterer lista.
- `reverse()`: Snu rekkefølga til elementa i lista.

**Eksempel:**
```python
liste = [1, 2, 3]
liste.append(4)            # liste blir [1, 2, 3, 4]
liste.insert(1, 'to')      # liste blir [1, 'to', 2, 3, 4]
liste.remove(2)            # liste blir [1, 'to', 3, 4]
pop_element = liste.pop(1) # liste blir [1, 3, 4], pop_element er 'to'
liste.sort()               # liste blir [1, 3, 4]
liste.reverse()            # liste blir [4, 3, 1]
```

#### Fjerning av element med `del`
**Eksempel:**
```python
liste = [1, 2, 3, 4]
del liste[2]  # liste blir [1, 2, 4]
```

#### Todimensjonale lister og tupler
Du kan lage nestede lister og tupler for å representere matriser.

**Eksempel:**
```python
todimensjonal_liste = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(todimensjonal_liste[1][2])  # Output: 6

todimensjonal_tuppel = ((1, 2, 3), (4, 5, 6), (7, 8, 9))
print(todimensjonal_tuppel[1][2])  # Output: 6
```

## Eksempler og Øvingar
**Eksempel 1:**
Lag ei liste med namn på fire ingeniørdisiplinar. Bruk listemetoder for å sortere lista i alfabetisk rekkefølge og fjerne det siste elementet.

**Kode:**
```python
ingenior_disiplinar = ['Kjemi', 'Mekanikk', 'Bygg', 'Elektronikk']
ingenior_disiplinar.sort()
sist = ingenior_disiplinar.pop()
print(ingenior_disiplinar)  # Output: ['Bygg', 'Elektronikk', 'Kjemi']
print(sist)                 # Output: 'Mekanikk'
```

**Eksempel 2:**
Gitt følgjande todimensjonale liste som representerer ein matrise, finn summen av alle elementa.

**Kode:**
```python
matrise = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
summa = 0
for rad in matrise:
    for element in rad:
        summa += element
print(summa)  # Output: 45
```

### Repitisjonsspørsmål
<details>
    <summary>1. Korleis kan du konkatene to strenger i Python?</summary>
    Bruk '+'-operatoren.
</details>

<details>
    <summary>2. Kva metode bruker du for å dele ei streng?</summary>
    `split()`
</details>

<details>
    <summary>3. Skriv eitt eksempel på å opprette ei todimensjonal liste.</summary>
    `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`
</details>

<details>
    <summary>4. Korleis reversere du ei liste?</summary>
    Bruk `reverse()`-metoden.
</details>

<details>
    <summary>5. Kva er forskjellen mellom ei liste og eit tuppel?</summary>
    Lister er foranderlige, medan tupler er uforanderlige.
</details>

<details>
    <summary>6. Korleis kan du finne lengda på ei streng?</summary>
    Bruk `len()`-funksjonen.
</details>

<details>
    <summary>7. Korleis kan du fjerne eit element frå ei liste på ein gitt posisjon utan å returnere det?</summary>
    Bruk `del`-kommandoen.
</details>

<details>
    <summary>8. Kva er formålet med `isdigit()`-metoden?</summary>
    Å sjekke om alle teikn i ei streng er sifre.
</details>
