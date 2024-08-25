
## Innhaldsliste
1. [While-løkker](#While-løkker)
2. [For-løkker](#For-løkker)
    - [Iterering av sekvensar per element](#Iterering-av-sekvensar-per-element)
    - [Iterering av sekvensar på indeks](#Iterering-av-sekvensar-på-indeks)
    - [Break i løkker](#Break-i-løkker)
3. [Nøstede løkker](#Nøstede-løkker)
    - [Doble Løkker](#Doble-løkker)
    - [Triple Løkker](#Triple-løkker)
4. [Oppsummert](#Oppsummert)
5. [Repetisjonsspørsmål](#Repetisjonsspørsmål)

## While-løkker
Ei `while`-løkke i Python gjentar ei blokk med kode så lenge ein bestemt betingelse er sann. Dette er nyttig når talet på iterasjonar ikkje er kjent på førehand. 

```python
# Eksempel på ei while-løkke
n = 0
while n < 5:
    print("Talet er", n)
    n += 1
```
**Output:**
```
Talet er 0
Talet er 1
Talet er 2
Talet er 3
Talet er 4
```
Koden over vil skrive ut tala frå 0 til 4. Løkka held fram til betingelsen `n < 5` ikkje lenger er sann.

## For-løkker
### Iterering av sekvensar per element
`for`-løkker gir ein enkel måte å iterere over element i ein sekvens (som lister eller strenger).

```python
# Eksempel på ei for-løkke
frukt_lista = ["eple", "banan", "kirsebær"]
for frukt in frukt_lista:
    print(frukt)
```
**Output:**
```
eple
banan
kirsebær
```

### Iterering av sekvensar på indeks
Ein kan også iterere over indeksen til elementa ved å bruke `range()` og `len()` som retunerer lengda til arrayet.

```python
# Eksempel på iterering med indeks
frukt_lista = ["eple", "banan", "kirsebær"]
for i in range(len(frukt_lista)):
    print("Indeks", i, "har verdi", frukt_lista[i])
```
**Output:**
```
Indeks 0 har verdi eple
Indeks 1 har verdi banan
Indeks 2 har verdi kirsebær
```
Her nyttast `range(len(frukt_lista))` til å skape ein sekvens av indeksar som løkka itererer over.

### Break i løkker
`break`-er brukes til å stoppe ein løkke før ho har ferdig å iterere over alle elementa.

```python
# Eksempel på bruk av break
for tal in range(10):
    if tal == 5:
        break
    print(tal)
```
**Output:**
```
0
1
2
3
4
```
Løkka bryt ved `tal == 5` og skriv derfor berre ut tala frå 0 til 4.

## Nøstede løkker
### Doble løkker
Nøstede løkker er løkker inni løkker og kan brukast til å iterere over fleire sett med data.

```python
# Eksempel på doble løkker
for i in range(3):
    for j in range(2):
        print(f"i = {i}, j = {j}")
```
**Output:**
```
i = 0, j = 0
i = 0, j = 1
i = 1, j = 0
i = 1, j = 1
i = 2, j = 0
i = 2, j = 1
```

### Triple løkker
Som doble løkker, kan triple løkker også brytast innvendig for meir komplekse iterasjonar.

```python
# Eksempel på triple løkker
for i in range(2):
    for j in range(2):
        for k in range(2):
            print(f"i = {i}, j = {j}, k = {k}")
```
**Output:**
```
i = 0, j = 0, k = 0
i = 0, j = 0, k = 1
i = 0, j = 1, k = 0
i = 0, j = 1, k = 1
i = 1, j = 0, k = 0
i = 1, j = 0, k = 1
i = 1, j = 1, k = 0
i = 1, j = 1, k = 1
```

## Oppsummert
Løkker er essensielle for å gjere repeterande oppgåver i programmering. `while`-løkker er nyttige når iterasjonane ikkje er førespelbare, medan `for`-løkker er betre når ein itererer over sekvensar. Når data krev fleire nivå med iterasjon, kan ein bruke nøstede løkker. 

## Repetisjonsspørsmål
<details>
    <summary>1. Kva er ein while-løkke?</summary>
    Ein `while`-løkke er ein kontrollflytstruktur som gjentar ei blokk med kode så lenge ein spesifisert betingelse er sann.
</details>

<details>
    <summary>2. Kva funksjon har break i ei løkke?</summary>
    `break`-er blir brukt til å avslutte ei løkke før ho har iterert over alle elementa.
</details>

<details>
    <summary>3. Korleis itererer du over elementa i ei liste ved hjelp av ei for-løkke?</summary>
    Du kan iterere over elementa i ei liste ved hjelp av ei for-løkke ved å skrive `for element in liste:`.
</details>

<details>
    <summary>4. Kva verdiar får `n` i løkka `for n in range(4):`?</summary>
    `n` vil ha verdiane 0, 1, 2 og 3.
</details>

<details>
    <summary>5. Korleis itererer du over indeksen til elementa i ei liste?</summary>
    Du kan iterere over indeksen til elementa i ei liste ved å bruke `for i in range(len(liste)):` og deretter referere til elementa som `liste[i]`.
</details>

<details>
    <summary>6. Kva er ei nøsta løkke?</summary>
    Ei nøsta løkke er ei løkke som er plassert inni ei anna løkke.
</details>

<details>
    <summary>7. Kva vil løkka `for i in range(2): for j in range(2): print(i, j)` skrive ut?</summary>
    Løkka vil skrive ut alle kombinasjonar av `i` og `j` frå 0 til 1:
    ```
    0 0
    0 1
    1 0
    1 1
    ```
</details>

<details>
    <summary>8. Kva skjer når betingelsen i ein while-løkke aldri blir usann?</summary>
    Løkka vil bli ei "uendeleg løkke" og vil aldri stoppe av seg sjølv.
</details>

