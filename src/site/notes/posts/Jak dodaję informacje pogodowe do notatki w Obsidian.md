---
{"dg-publish":true,"permalink":"/posts/jak-dodaje-informacje-pogodowe-do-notatki-w-obsidian/","tags":["WeblogPoMo2024","Obsidian"],"updated":"2024-05-06"}
---


Po co dodawać informacje pogodowe do notatki? Nie wiem, ale dla mnie jest to niezwykle przydatne. Przez lata pracy w Obsidianie próbowałem wielu różnych sposobów, żeby to jakoś sensownie rozwiązać. Od instalacji wtyczek, przez korzystanie z API i pisanie własnych skryptów. Ostatecznie stworzyłem skrót w Apple Shortcuts, który tworzy raport pogodowy automatycznie!

## Jak to działa

Najpierw pobierane są warunki pogodowe z wybranej lokalizacji. Każda z wartości umieszczana jest w polu tekstowym, z którego jest następnie dodawana do notatki codziennej w Obsidian, w miejsce `%%weather%%`.

## Jakie informacje są dodawane

- warunki pogodowe
- najniższa i najwyższa temperatura
- godzina wschodu i zachodu słońca
- dzień roku

Informacje te są zapisane w następującej formie:

```
- weather:: Pogodnie
- low:: 13 st. C
- high:: 21 st. C
- sunrise:: 04:20
- sunset:: 21:00
- day:: 183
```

Następnie tworzę podsumowanie w oddzielnej notatce w formie tabeli, za pomocą wtyczki *Dataview*.

```sql
table
	weather as Weather,
	low as Low,
	high as High,
	sunrise as Sunrise,
	sunset as Sunset,
	dur(date(sunset, "T") - date(sunrise, "T")) as Daytime,
	day as Day
from "journal/2024/07-July"
where
	!contains(file.name,"template")
sort day desc
```

Wykluczyłem pliki, w których nazwie znajduje się słowo *template*, żeby nie wyświetlały się w tabeli.

**Daytime** to długość dnia. Mimo że czas wschodu i zachodu słońca dodane są jako ciąg znaków (string), a nie poprawna data (bo wtedy wyświetla się cała data), to udało mi się poprawnie wyświetlić długość dnia, licząc czas od wschodu do zachodu słońca.

Jest to możliwe dzięki temu, że dataview może narzucić format (luxon) na podane dane, niezależnie od ich rodzaju. Oczywiście to nie zadziała, jeśli dane nie będą dopasowane. Przykład: gdybym w sunrise i sunset podał wartość tekstową, dataview zwróci błąd.
