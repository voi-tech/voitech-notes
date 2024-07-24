---
{"dg-publish":true,"dg-path":"posts/Jak tworzę notatki codzienne w Obsidian - szablon 2024.md","permalink":"/posts/jak-tworze-notatki-codzienne-w-obsidian-szablon-2024/","tags":["Obsidian"],"updated":"2024-04-22"}
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

Pod tytułem znajdują się informacje progowe. [[2_areas/web/posts/Jak dodaję informacje pogodowe do notatki w Obsidian\|Jak dodaję informacje pogodowe do notatki w Obsidian]]?

## Plan dnia

Następna sekcja to plan dnia, czyli wydarzenia z kalendarza dodawane za pomocą skrótu w Apple Shortcuts.

Poniżej znajduje się skrypt Dataview, który wyświetla kto ma dziś urodziny.

```SQL
list
where contains(category, [[People]]) 
and date(birthdate).month = this.file.day.month 
and date(birthdate).day = this.file.day.day
```

## Notatki

Ostatnia sekcja to zbiór notatek utworzonych lub zmodyfikowanych dzisiaj. Notatki są automatycznie dodawane za pomocą wtyczki *Dataview*, ale nic nie stoi na przeszkodzie, aby robić to ręcznie.

```SQL
list
where
	!contains(category, [[Journal]]) and
	contains(file.outlinks, this.file.link) or
	contains(string(file.frontmatter), string(dateformat(this.file.day,"yyyy-MM-dd")))
sort file.mtime desc
```

Powyższy skrypt tworzy listę notatek (`list`), z wykluczeniem kategorii o nazwie *Journal* (`!contains(category, [[Journal]])`), gdzie notatka zawiera link do tej notatki (`contains(file.outlinks, this.file.link`) lub datę tej notatki w metadanych (`contains(string(file.frontmatter), string(dateformat(this.file.day, "yyyy-MM-dd")))`). Notatki są sortowane w kolejności od ostatnio edytowanych (`sort file.mtime desc`).

Może się to wydawać skomplikowane, ale tak naprawdę wystarczy znać trochę słówek po angielsku i da się wszystko rozszyfrować. Bardzo polecam pobawić się takimi skryptami z wtyczką *Dataview*!
