---
{"dg-publish":true,"dg-path":"posts/Jak tworzę notatki codzienne w Obsidian - szablon 2024.md","dg-permalink":"obsidian-daily-notes-2024","permalink":"/obsidian-daily-notes-2024/","tags":["Obsidian"]}
---


Szablon notatki codziennej, czyli takiej, której tytuł to dzisiejsza data a treść odnosi się do dzisiejszego dnia.

**Wymagane rzeczy:**

- **Codzienne notatki** - wtyczka wbudowana
- **Dataview** i **Templater** - wtyczki stworzone przez społeczność
- **Apple Shortcuts** - aplikacja Skróty
- **Actions for Obsidian** - program rozszerzający możliwości skrótów

## Properties

**W metadanych notatki zawarte są następujące informacje:**

```yaml
tags: #Daily
category: [[Journal]]
weather: %%weather%% - pogoda
min: %%min%% - najniższa temperatura
max: %%max%% - najwyższa temperatura
sunrise: %%sunrise%% - godzina wschodu słońca
sunset: %%sunset%% - godzina zachodu słońca
day: %%day%% - dzień roku (1-365)
```

## Nazwa i tytuł notatki

Nazwa notatki to dzisiejsza data w formacie `YYYY-MM-DD`, czyli np. `2024-04-22`. Notatki są automatycznie przenoszone do odpowiedniego folderu, dzięki możliwości ustawienia odpowiedniej nazwy w opcjach wtyczki *Codzienne notatki*: `YYYY/MM-MMMM/YYYY-MM-DD`.

- **4 Archive**
	- **journal**
		- **2024**
			- **01-styczeń**
			- **02-luty**
			- **03-marzec**
			- **04-kwiecień**
				- 2024-04-22

Tytuł notatki jest zapisany jako nagłówek pierwszego poziomu, czyli **H1**: `# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, DD MMMM YYYY") %>`. Templater wykrywa datę na podstawie nazwy notatki i zamienia na format `"dddd, DD MMMM YYYY"`, czyli np. `poniedziałek, 22 kwietnia 2024`.

Pod tytułem Templater dodaje losowy cytat: `<% tp.web.daily_quote() %>`.

## Plan dnia

Następna sekcja to `## Plan dnia`, czyli wydarzenia w ciągu dnia. Wpisuję je ręcznie lub korzystam ze skrótu w aplikacji *Apple Shortcuts*, który wyciąga dane z aplikacji Apple Calendar (Kalendarz) i Apple Reminders (Przypomnienia) i dodaje nad placeholderem `%%calendar%%` i `%%reminders%%`.

## Notatki

Ostatnia sekcja to `## Notatki`, czyli zbiór notatek utworzonych lub zmodyfikowanych dzisiaj. Notatki są automatycznie dodawane za pomocą wtyczki *Dataview*, ale nic nie stoi na przeszkodzie, aby robić to ręcznie.

```
list
from !"0 Index"
where
	!contains(category, [[Journal]]) and
	contains(file.outlinks, this.file.link) or
	contains(string(file.frontmatter), string(dateformat(this.file.day,"yyyy-MM-dd")))
sort file.mtime desc
```

Powyższy skrypt tworzy listę notatek (`list`), z wykluczeniem folderu o nazwie *0 Index* (`from !"0 Index"`) i z wykluczeniem kategorii o nazwie *Journal* (`!contains(category, [[Journal]])`), ale gdzie notatka zawiera link do tej notatki (`contains(file.outlinks, this.file.link`) lub datę tej notatki w metadanych (`contains(string(file.frontmatter), string(dateformat(this.file.day, "yyyy-MM-dd")))`). Notatki są sortowane w kolejności od ostatnio edytowanych (`sort file.mtime desc`).

Może się to wydawać skomplikowane, ale tak naprawdę wystarczy znać trochę słówek po angielsku i da się wszystko rozszyfrować. Bardzo polecam pobawić się takimi skryptami z wtyczką *Dataview*!

## Skróty - Apple Shortcuts + Actions for Obsidian

Do tworzenia notatek i dodawania do nich informacji korzystam z *Apple Shortcuts* i programu *Actions for Obsidian*, który znacząco poszerza możliwości skrótów i ułatwia ich tworzenie.

W szablonie notatki dodałem placeholdery, czyli tymczasowy tekst w formacie `%%nazwa%%`, który będzie zastąpiony przez odpowiednie dane. Taki format sprawia, że same placeholdery nie są widoczne w notatce dla mnie, bo są rozpoznawane jako komentarz. Są one jednak widoczne dla skrótów.

**Linki do pobrania skrótów, z których korzystam do dodawania informacji do notatki:**

- [Add weather to daily note in Obsidian](https://www.icloud.com/shortcuts/41095556ed014e71b2b411a74270aa1e) - dodaj informacje pogodowe
- [Add calendar events to daily note in Obsidian](https://www.icloud.com/shortcuts/781a4837a63a4515ad3944f28e3d3c21) - dodaj wydarzenia z kalendarza
- [Add reminders to daily note in Obsidian](https://www.icloud.com/shortcuts/c78e2113dd574f8f85e6b5f12817d617) - dodaj zadania z aplikacji Przypomnienia

Do działania tych skrótów wymagane jest zainstalowanie i skonfigurowanie programu *Actions for Obsidian*. Później trzeba w każdym ze skrótów wskazać sejf z notatkami w miejsce *Vault*.

Nazwy skrótów są po angielsku bo Siri nie zna polskiego.

Link do szablonu: https://paste.lol/voitech/obsidian-daily-note-template

Skopiuj i wklej do swojego szablonu, edytuj według potrzeby. Pamiętaj, że w ustawieniach wtyczki *Codzienne notatki* należy wskazać ten plik jako szablon.
