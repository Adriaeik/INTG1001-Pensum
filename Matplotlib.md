
## Table of Contents
1. [Introduksjon til Matplotlib](#Introduksjon-til-Matplotlib)
2. [Grunnleggende Funksjonsgrafer med Matplotlib](#Grunnleggende-Funksjonsgrafer-med-Matplotlib)
3. [Avanserte Funksjonsgrafer og Andre Typer Plott](#Avanserte-Funksjonsgrafer-og-Andre-Typer-Plott)
4. [Eksempel og Øvelser](#Eksempel-og-Øvelser)
5. [Repetisjonsspørsmål](#Repetisjonsspørsmål)

## Main Content

### 1. [Introduksjon til Matplotlib](#Introduksjon-til-Matplotlib)

Matplotlib er et kraftig bibliotek for datavisualisering i Python. Spesielt viktig i ingeniørstudier er `matplotlib.pyplot`, en samling av kommandoer som gjør det enkelt å lage plott.

For å bruke Matplotlib i Python, må biblioteket importeres slik:
```python
import matplotlib.pyplot as plt
```

Dette vil tillate oss å bruke aliaset `plt` for tilgang til funksjonene i biblioteket, slik som å opprette plott, endre etiketter, og vise figurer.

### 2. [Grunnleggende Funksjonsgrafer med Matplotlib](#Grunnleggende-Funksjonsgrafer-med-Matplotlib)

#### Lage en Enkel Funksjonsgraf
Her er et grunnleggende eksempel på hvordan man kan plotte en funksjon:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)  # Genererer 100 punkt fra 0 til 10
y = np.sin(x)                # Beregner y-verdiene som sinus til x

plt.plot(x, y)               # Lager plott
plt.xlabel('x-akse')         # Setter etikett på x-aksen
plt.ylabel('y-akse')         # Setter etikett på y-aksen
plt.title('Enkel Funksjonsgraf')  # Lager en tittel til grafen
plt.grid(True)               # Legger til rutenett
plt.show()                   # Viser plottet
```

Her bruker vi NumPy for å generere dataene vi ønsker å plotte. `np.linspace` brukes for å generere en jevn rekke av tall.

### 3. [Avanserte Funksjonsgrafer og Andre Typer Plott](#Avanserte-Funksjonsgrafer-og-Andre-Typer-Plott)

#### Flere Funksjoner i Samme Plott
Noen ganger er det nyttig å plotte flere funksjoner i samme diagram:
```python
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

plt.plot(x, y1, label='sin(x)')
plt.plot(x, y2, label='cos(x)')
plt.xlabel('x-akse')
plt.ylabel('y-akse')
plt.title('Flere Funksjoner')
plt.legend()                 # Legger til en legende som forklarer hver kurve
plt.grid(True)
plt.show()
```

#### Søylediagram
Når man ønsker å visualisere kategoriske data, er søylediagrammer nyttige:
```python
categories = ['A', 'B', 'C', 'D']
values = [10, 15, 7, 10]

plt.bar(categories, values)
plt.xlabel('Kategorier')
plt.ylabel('Verdier')
plt.title('Søylediagram')
plt.show()
```

#### Kakediagram
Kakediagrammer brukes ofte for å vise prosentfordelinger:
```python
labels = ['Apples', 'Bananas', 'Cherries', 'Dates']
sizes = [15, 35, 25, 25]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0.1, 0, 0, 0)  # Fremhever den første skiven

plt.pie(sizes, explode=explode, labels=labels, colors=colors,
autopct='%1.1f%%', shadow=True, startangle=140)
plt.title('Kakediagram')
plt.show()
```

## Eksempel og Øvelser

### Eksempel 1: Enkel Trigonometri
Lag plott som viser $y = \sin(x)$ og $y = \cos(x)$ i samme diagram:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

plt.plot(x, y1, label='sin(x)')
plt.plot(x, y2, label='cos(x)')
plt.xlabel('x-akse')
plt.ylabel('y-akse')
plt.title('Sinus og Cosinus')
plt.legend()
plt.grid(True)
plt.show()
```

### Øvelse 1
Lag en graf av funksjonen $y = x^2$ og $y = x^3$ i samme diagram, med ulik farge for hver kurve og legg til en tittel.

### Eksempel 2: Søylediagram
Visualiser fordelingen av fire kategorier:
```python
categories = ['A', 'B', 'C', 'D']
values = [23, 17, 35, 29]

plt.bar(categories, values, color=['red', 'blue', 'green', 'purple'])
plt.xlabel('Kategorier')
plt.ylabel('Verdier')
plt.title('Fordeling av Verdier')
plt.show()
```

### Øvelse 2
Lag et søylediagram som viser resultatet av en spørreundersøkelse med følgende kategorier og verdier: ['Ja', 'Nei', 'Kanskje', 'Ingen Kommentar'] og [50, 30, 10, 10].

### Eksempel 3: Kakediagram
Lag et kakediagram av prosentandelene av forskjellige frukt:
```python
labels = ['Apples', 'Bananas', 'Cherries', 'Dates']
sizes = [20, 30, 25, 25]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0.1, 0, 0, 0)

plt.pie(sizes, explode=explode, labels=labels, colors=colors,
autopct='%1.1f%%', shadow=True, startangle=140)
plt.title('Frukt Kakediagram')
plt.show()
```

### Øvelse 3
Lag et kakediagram som viser de fire mest populære fargene i en gruppe med navnelapper: ['Rød', 'Blå', 'Grønn', 'Gul'] og [12, 28, 5, 15].

## Lecture Summary
I denne mini-kompendium har vi gått gjennom import av Matplotlib og grunnleggende plotteteknikker for funksjonsgrafer, søylediagram, og kakediagram. Du har også sett eksempler på hvordan man kombinerer flere grafiske elementer i samme plot.

## Repetisjonsspørsmål

<details>
    <summary>1. Hva er kommandoen for å importere Matplotlib?</summary>
    `import matplotlib.pyplot as plt`
</details>

<details>
    <summary>2. Hvordan genererer man data for å plotte en funksjon som sinus?</summary>
    `x = np.linspace(0, 10, 100)`
</details>

<details>
    <summary>3. Hva brukes `plt.legend()` til?</summary>
    For å legge til en legende som forklarer hver kurve i plottet.
</details>

<details>
    <summary>4. Hvordan legger man til en tittel til et plott?</summary>
    `plt.title('Tittel')`
</details>

<details>
    <summary>5. Hva er forskjellen mellom et søyleplott og et kakediagram?</summary>
    Søyleplott brukes for å vise kategoriske data, mens kakediagram viser prosentfordelinger.
</details>

<details>
    <summary>6. Hvordan kan du legge til en grid i et plott?</summary>
    `plt.grid(True)`
</details>

<details>
    <summary>7. Hvordan fremhever du en spesifikk skive i et kakediagram?</summary>
    Ved å bruke parameteret `explode`, for eksempel `explode = (0.1, 0, 0, 0)`.
</details>

<details>
    <summary>8. Hvordan lager du en enkel lineær graf av $y = 2x + 1$?</summary>
    Bruk `plt.plot(x, 2*x + 1)`