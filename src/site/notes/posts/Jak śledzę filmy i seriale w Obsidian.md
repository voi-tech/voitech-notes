---
{"dg-publish":true,"dg-permalink":"obsidian-media-tracking-2024","permalink":"/obsidian-media-tracking-2024/","tags":["WeblogPoMo2024","Obsidian"],"updated":"2024-05-08"}
---


Notatki tworzone są za pomocą wtyczki *Moviegrabber*, która wykorzystuje *OMDb API* do wyszukiwania filmów i seriali.

Wtyczka ta dodaje tytuł (i rok premiery w nawiasie), plakat, czas trwania w minutach i dodatkowo liczbę sezonów w przypadku seriali. Można za jej pomocą dodać dużo więcej informacji, w tym np. reżysera, aktorów, opis filmu czy nawet trailer.

## Szablon

```yaml
---
created: <% tp.file.creation_date() %>
date: 
aliases: 
tags: 
category:
  - "[[Series]]"
duration: {{Runtime}}
rating: 
seasons: {{totalSeasons}}
image: {{Poster}}
---

![]({{Poster}})

# <% tp.file.title %>

{{YoutubeEmbed}}

{{Plot}}
```

- `date` - to dzień, kiedy ostatnio oglądałem dany film czy serial.
- `duration` - to czas trwania w minutach.
- `rating` - to moja ocena w skali pięcio-gwiazdkowej.
- `seasons` - czyli ile sezonów ma dany serial.

Dodatkowo każda notatka zawiera tagi, które określają jej status.

## Zmiany

W najbliższym czasie zamierzam zupełnie zrezygnować z wtyczki, a posługiwać się tylko szablonem i ewentualne informacje wpisywać ręcznie. Uświadomiłem sobie, podobnie jak w przypadku gier, że nie potrzebuję informacji, które dostarcza *API*. Tytuł zwykle znam już wcześniej, bo tworzę notatkę w momencie oglądania filmu lub kiedy mam w planach daną produkcję obejrzeć. Nie potrzebuję plakatu, bo jest on i tak nieczytelny poza Obsidianem. Czas trwania łatwo jest sprawdzić, a nie dodaję tych notatek jakoś niezwykle dużo, żeby ten czas poświęcony na ręczne wpisanie informacji był jakoś mocno istotny.

Na ten moment nie podsumowuję śledzonych filmów i seriali w oddzielnej tabeli. Śledzę je, żeby łatwo było później sprawdzić, kiedy daną produkcję ostatnio oglądałem.

