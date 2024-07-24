---
{"dg-publish":true,"dg-path":"posts/Kupuj mądrze.md","permalink":"/posts/kupuj-madrze/","tags":["WeblogPoMo2024"],"updated":"2024-05-13"}
---


> Zainspirowany przez [kepano](https://stephango.com/buy-wisely) stworzyłem w Obsidianie swój system oceniania wartości posiadanych (lub nie) rzeczy. Paradoksalnie, im wynik jest niższy, tym większa wartość (i opłacalność) danej rzeczy.

## Wszystko zaczyna się od szablonu!

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
---

	<% await tp.file.move("/items/" + tp.file.title) %>
```

Nie będę omawiał każdego atrybutu, ale warto zwrócić uwagę na niektóre z nich:

- **date** - to data, od której używam danej rzeczy (nie data zakupu).
- **rating** - to moja osobista ocena w skali 5-cio gwiazdkowej.
- **price** - to cena, za jaką kupiłem daną rzecz.

Dodatkowo pod atrybutami jest komenda (*Templater*), która automatycznie przenosi notatkę do odpowiedniego folderu.

## Tabela Dataview

```yaml
dataview
table
	dateformat(date, "yyyy-MM") as "Date",
	round((date(today) - date).months,1) as "Months",
	round(price/((date(today) - date).months),2) as "Monthly",
	string(round(price, 2)) as "Price"
where
	contains(category, [[Items]])
sort
	round(price/((date(today) - date).months),2) asc
```

Tabela przedstawia miesięczny koszt posiadania danej rzeczy. Przykład: koszt ekspresu do kawy zakupionego w lipcu 2021 wynosi obecnie 45 zł miesięcznie.

Można też zastosować nieco inne podejście, gdzie obliczany jest *koszt za użycie*. Wtedy jednak trzeba określić, ile razy w danym miesiącu używamy danej rzeczy. Stosowałem tą metodę wcześniej, wtedy określałem jedną godzinę jako jedno użycie. Osobiście wolę jednak nieco szerszy kontekst, dlatego koszt miesięczny bardziej mi odpowiada.

Tą samą metodę stosuję do śledzenia kosztów miesięcznych używanych aplikacji lub do stwierdzenia, czy warto coś kupić.