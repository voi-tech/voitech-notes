---
{"dg-publish":true,"dg-permalink":"obsidian-weather-2024","permalink":"/obsidian-weather-2024/","tags":["WeblogPoMo2024","Obsidian"]}
---


Po co dodawać informacje pogodowe do notatki? Nie wiem, ale dla mnie jest to niezwykle przydatne. Przez lata pracy w Obsidianie próbowałem wielu różnych sposobów, żeby to jakoś sensownie rozwiązać. Od instalacji wtyczek, przez korzystanie z API i pisania własnych skryptów.

Ostatecznie stworzyłem skrót w Apple Shortcuts, który tworzy raport pogodowy automatycznie! Jak to się dzieje?

Najpierw pobierane są warunki pogodowe z bieżącej lokalizacji. Każda z wartości umieszczana jest w oddzielnym polu tekstowym, z którego jest następnie dodawana do notatki codziennej w Obsidian, w miejsce placeholderów.

## Jakie informacje dodaję

- warunki pogodowe
- najniższa i najwyższa temperatura
- godzina wschodu i zachodu słońca
- dzień roku

Następnie tworzę podsumowanie w oddzielnej notatce w formie tabeli, za pomocą wtyczki *Dataview*.

```
table
	weather as Weather,
	min as Min,
	maks as Maks,
	sunrise as Sunrise,
	sunset as Sunset,
	dur(date(sunset, "T") - date(sunrise, "T")) as Daytime,
	day as Day
from #Daily 
where
	!contains(file.name,"template")
sort day desc
```

Każda notatka codzienna zawiera tag *Daily*, dzięki czemu łatwo je odnaleźć. Dodatkowo każda notatka zawiera kategorię *Journal* i jest umieszczona w folderze o tej samej nazwie. Można je więc umieszczać w tej tabeli na kilka sposobów.

Wykluczyłem też pliki, w nazwie których znajduje się słowo *template*, żeby nie wyświetlały się w tabeli.

Powyższa tabela ograniczona jest do zaledwie 5 pozycji. W mojej notatce stosuję podział miesięczny. Wtedy zamiast `from #Daily` stosuję np. `from "Journal/2024/04-kwiecień"`.

**Daytime** to długość dnia. Mimo że czas wschodu i zachodu słońca dodane są jako ciąg znaków (string), a nie poprawna data (bo wtedy wyświetla się cała data), to udało mi się też poprawnie wyświetlić długość dnia, licząc czas od wschodu do zachodu słońca.

Jest to możliwe dzięki temu, że dataview może narzucić format (luxon) na podane dane, niezależnie od ich rodzaju. Oczywiście to nie zadziała, jeśli dane nie będą dopasowane. Przykład: gdybym w sunrise i sunset podał wartość tekstową, dataview zwróci błąd.
