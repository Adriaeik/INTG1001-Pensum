
## Innhaldsliste

1. [If](#If)
2. [If-else](#If-else)
3. [If-elif-else](#If-elif-else)
4. [Nøstede if-setningar](#Nøstede-if-setningar)
5. [Lecture Summary](#Lecture-Summary)
6. [Repeatsjonsoppgåver](#Repeatsjonsoppgåver)

## Hovudinnhald

### If

If-setninger er dei mest grunnleggande kontrollstrukturane for betinga logikk i Python. Dei lar oss utføre kodeblokker basert på om ein tilstand er sann eller ikkje.

#### Teori

If-setninga fungerer ved å evaluere ein uttrykk. Dersom uttrykket er sann, vil koden inni if-blokka bli utført. Struktur:

```python
if uttrykk:
    # Kodeblokka
```

#### Praktisk Eksempel

```python
x = 10
if x > 5:
    print("x er større enn 5")
```

**Output:** 
```
x er større enn 5
```

### If-else

For å utføre eit alternativt sett med handlingar når if-uttrykket er usann, bruker vi if-else-setningar.

#### Teori

Structur på if-else:

```python
if uttrykk:
    # Kodeblokka dersom uttrykket er sann
else:
    # Kodeblokka dersom uttrykket er usann
```

#### Praktisk Eksempel

```python
x = 3
if x > 5:
    print("x er større enn 5")
else:
    print("x er mindre enn eller lik 5")
```

**Output:** 
```
x er mindre enn eller lik 5
```

### If-elif-else

For å håndtere fleire tilstandar, bruker vi if-elif-else-setningar. 

#### Teori

Structur på if-elif-else:

```python
if uttrykk1:
    # Kodeblokka dersom uttrykk1 er sann
elif uttrykk2:
    # Kodeblokka dersom uttrykk2 er sann
else:
    # Kodeblokka dersom ingen av uttrykka er sann
```

#### Praktisk Eksempel

```python
x = 10
if x > 20:
    print("x er større enn 20")
elif x > 15:
    print("x er større enn 15, men mindre enn eller lik 20")
elif x > 5:
    print("x er større enn 5, men mindre enn eller lik 15")
else:
    print("x er mindre enn eller lik 5")
```

**Output:** 
```
x er større enn 5, men mindre enn eller lik 15
```

### Nøstede if-setningar

Nøstede if-setningar lar oss sjekke fleire tilstandar innanfor ein annan if-setning. Dette kan gjere koden mindre oversiktleg, men er nyttig når me treng komplekse logikkar.

#### Teori

Strukturen på nøsta if-setningar:

```python
if uttrykk1:
    if uttrykk2:
        # Kodeblokka dersom begge uttrykk1 og -2 er sanne
    else:
        # Kodeblokka dersom uttrykk1 er sann, men uttrykk2 er usann
else:
    # Kodeblokka dersom uttrykk1 er usann
```

#### Praktisk Eksempel

```python
x = 8
if x > 5:
    print("x er større enn 5")
    if x % 2 == 0:
        print("x er også eit partal")
    else:
        print("x er eit oddetal")
else:
    print("x er mindre enn eller lik 5")
```

**Output:** 
```
x er større enn 5
x er også eit partal
```

## Lecture Summary

1. **If-setningar** vert brukt for å køyre kodeblokk viss ein tilstand er sann.
2. **If-else-setningar** legg til ein alternativ kodeblokk viss tilstanden er usann.
3. **If-elif-else-setningar** håndterer fleire tilstandar ved å bruke fleire logiske sjekkar.
4. **Nøstede if-setningar** tillater sjekking av fleire tilstandar innanfor ein annan if-setning, meir kompleks logikk.

## Repeatsjonsoppgåver

<details>
    <summary>1. Kva er syntaksen for ei enkel if-setning i Python?</summary>
    if uttrykk:
        # Kodeblokk
</details>

<details>
    <summary>2. Kva gjer ei if-else-setning?</summary>
    Den utfører alternativ kodeblokk dersom uttrykket er usann.
</details>

<details>
    <summary>3. Korleis kan me sjekke fleire tilstandar i rekkefølge?</summary>
    Ved å nytte if-elif-else-setningar.
</details>

<details>
    <summary>4. Kva er ei nøsta if-setning?</summary>
    Ein if-setning inni ein anna if-setning.
</details>

<details>
    <summary>5. Gje eit eksempel på ei nøsta if-setning.</summary>
    ```python
    if x > 5:
        if y < 10:
            print("x er større enn 5 og y er mindre enn 10")
    ```