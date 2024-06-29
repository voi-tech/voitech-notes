---
{"dg-publish":true,"dg-path":"Kupuj mądrze.md","dg-permalink":"items-obsidian-2024","permalink":"/items-obsidian-2024/","tags":["WeblogPoMo2024"]}
---


> Zainspirowany przez [kepano](https://stephango.com/buy-wisely) stworzyłem w Obsidianie swój system oceniania wartości posiadanych (lub nie) rzeczy. Paradoksalnie, im wynik jest niższy, tym większa wartość (i opłacalność) danej rzeczy.

## Szablon

Wszystko zaczyna się od szablonu!

```yaml
---
created: <% tp.file.creation_date() %>
date: 
aliases: 
tags: 
category:
  - "[[Items]]"
rating: 
price: 
uses:
---
<% await tp.file.move("/Items/" + tp.file.title) %>
```

Nie będę omawiał każdego atrybutu, ale warto zwrócić uwagę na niektóre z nich:

- **date** - to data, od której używam danej rzeczy (nie data zakupu).
- **rating** - to moja osobista ocena w skali 5-cio gwiazdkowej.
- **price** - to cena, za jaką kupiłem daną rzecz.
- **uses** - to ilość użyć (więcej o tym poniżej).

Dodatkowo pod atrybutami jest komenda (*Templater*), która automatycznie przenosi notatkę do odpowiedniego folderu.

## Szczegóły

**Jak określam ilość użyć danej rzeczy?** Jeśli używam czegoś przez godzinę, traktuję to jako jedno użycie. **Przykład**: używam MacBooka około 6 godzin dziennie (średnio), 6 x 30 (dni w miesiącu) = 180. Taką właśnie wartość wpisuję w polu `uses`. Jest to średnia ilość użyć danej rzeczy w miesiącu.

Następnie tworzę tabelę za pomocą *Dataview*, w której wyświetla się **koszt na użycie**.

```yaml
dataview
table
	dateformat(date, "yyyy-MM") as Acquired,
	round((date(today) - date).months,1) as "Months",
	uses as "Uses",
	round(uses*((date(today) - date).months),0) as "Total uses",
	round(price/(uses*((date(today) - date).months)),2) as "Per use",
	string(round(price, 2)) as Price
where
	uses > 0 and
	contains(category, [[Items]])
sort
	round(price/(uses*((date(today) - date).months)),2) asc
```

**Koszt na użycie** (per use) wyliczany jest na podstawie prostego działania: **cena / ilość użyć**. Rzeczy w tabeli sortowane są na podstawie tej wartości.

## Przykłady

Jeżeli dana rzecz osiągnie wartość poniżej złotówki na użycie, oceniam, że było warto.

- myszka Logitech Ergo M575 - zakupiona w kwietniu 2022, **koszt na użycie: 0,04 zł**.
- iPhone XS Max - zakupiony w styczniu 2022, **koszt na użycie: 0,59 zł**.
- MacBook Air M1 - zakupiony w marcu 2021, **koszt na użycie 0,77 zł**.

Ten sam schemat wykorzystuję też przy ocenie, **czy warto daną rzecz kupić** (lub kiedy warto wymienić na nową). Wtedy staram się przewidzieć, ile razy w miesiącu będę czegoś używał. Mogę sobie pozwolić na wymianę czegoś na nowe, jeśli wartość posiadanej przeze mnie rzeczy spadnie **poniżej 0,50 zł**.

> **Przykład**: słuchawki Aftershokz Aeropex osiągnęły wartość 0,22 zł, zepsuły się, więc szukałem nowych. Oceniam, że będę używał nowych tyle samo razy przez okres conajmniej dwóch lat. Po intensywnych poszukiwaniach zdecydowałem się na AirPods Pro 2 (USB-C), których koszt po dwóch latach powinien wynieść 0,35 zł.

Jeżeli już danej rzeczy nie używam w polu `uses` wpisuję 0, żeby nie były brane pod uwagę w tabeli.
