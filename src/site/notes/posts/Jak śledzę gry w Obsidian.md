---
{"dg-publish":true,"permalink":"/posts/jak-sledze-gry-w-obsidian/","tags":["WeblogPoMo2024","Obsidian"],"updated":"2024-05-07"}
---


Notatki tworzone są za pomocą dedykowanej wtyczki Game Search. Wyszukuje gry po nazwie za pomocą *RAWG API*.

Wtyczka ta dodaje datę wydania, link do plakatu i tytuł. Można dodać dużo więcej informacji, jak np. nazwę dewelopera czy wydawcy, na jakich platformach jest dostępna gra, czy nawet paletę kolorystyczną ze screenshotów. Ja jednak ich nie potrzebuję.

## Szablon

```yaml
---
created: <% tp.file.creation_date() %>
released: "{{released}}"
date: 
aliases: 
tags: 
category:
  - "[[Games]]"
platform: 
price: 
duration: 
rating: 
image: "{{background_image}}"
---

![]({{background_image}})

# <% tp.file.title %>

```

Nie będę opisywał każdego atrybutu, jaki dodaję do notatek. Warto jednak zwrócić uwagę na kilka wartości.

- `date` - to data, kiedy ostatnio grałem w daną grę.
- `platform` - to platforma (serwis), na której mam daną grę.
- `price` - to cena, którą zapłaciłem. Jeśli więc gra kosztuje normalnie 200 zł, ale ja ją odebrałem za darmo, to wpisuję 0.
- `playtime` - to czas gry. Zwykle zaokrąglony do 5 godzin. Jeśli na jakąś grę poświęciłem mniej czasu, wpisuję 0.
- `rating` - to moja ocena gry w skali pięcio-gwiazdkowej.

## Czy było warto

Gry są następnie podsumowane w swojej kategorii, czyli w notatce *Games*. Dodaję tam tabelę z tytułem gry, datą ostatniej gry, czasem gry w godzinach i ceną. Następnie przy każdej grze jest napisane, ile kosztuje mnie granie w dany tytuł, na podstawie wcześniej podanych wartości. Jest to proste działanie: cena podzielona przez czas gry. Na tej podstawie uznaję, czy było warto kupić daną grę. Jeśli cena za godzinę gry spada poniżej złotówki, to uznaję, że było warto.

**Tak wygląda tabela:**

| File                                        | Played     | Playtime   | Price     | Per hour |
| ------------------------------------------- | ---------- | ---------- | --------- | -------- |
| [[games/Diablo IV\|Diablo IV]]           | 6.06.2024  | 625 godzin | 349,00 zł | 0.56     |
| [[games/Path of Exile\|Path of Exile]]   | 21.04.2024 | 300 godzin | 210,00 zł | 0.7      |
| [[games/Cyberpunk 2077\|Cyberpunk 2077]] | 23.07.2024 | 150 godzin | 203,50 zł | 1.36     |
| [[games/No Man's Sky\|No Man's Sky]]     | 20.07.2024 | 20 godzin  | 109,50 zł | 5.47     |
| [[games/Elden Ring\|Elden Ring]]         | 7.07.2024  | 20 godzin  | 197,34 zł | 9.87     |

{ .block-language-dataview}

**Tak wygląda skrypt:**

```
dataview
table
	date as Played,
	playtime + " godzin" as Playtime,
	currencyformat(price, "PLN") as Price,
	round(price/playtime, 2) as "Per hour"
where contains(category, [[Games]]) and !contains(file.name, "template") and playtime > 0
sort round(price/playtime, 2) asc
```

**W powyższym skrypcie są dwie wartości, na które warto zwrócić uwagę:**

- `currencyformat(price, "PLN")` - powoduje poprawne wyświetlanie ceny.
- `round(price/duration, 2)` - powoduje poprawnie wykonane działanie z zaokrągleniem wyniku do drugiego miejsca po przecinku.

Można całkowicie zrezygnować z używania wtyczki i wpisywać potrzebne informacje ręcznie lub z pomocą szablonu. Sam chyba tak właśnie zrobię, bo ani plakat ani data wydania gry nie są mi do niczego za bardzo potrzebne. Może wtedy te notatki ładnie wyglądają, ale jestem minimalistą i lubię prostotę.

