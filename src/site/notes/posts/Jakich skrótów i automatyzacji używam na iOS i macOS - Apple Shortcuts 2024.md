---
{"dg-publish":true,"dg-permalink":"apple-shortcuts-2024","permalink":"/apple-shortcuts-2024/","tags":["WeblogPoMo2024","AppleShortcuts"]}
---


Odkąd używam urządzeń z nadgryzionym jabłkiem nie mogę się nadziwić, jak bardzo można ułatwić sobie niektóre rzeczy korzystając po prostu z wbudowanych funkcji, takich jak np. skróty i automatyzacje.

Poniżej zamieszczam listę skrótów i automatyzacji, z których korzystam, z krótkim opisem. Skróty mają tytuły po angielsku z oczywistego powodu - Siri nie zna polskiego, a ja najczęściej je uruchamiam z jej pomocą, głosowo. Nie udostępniam linków do pobrania tych skrótów, bo pracuję nad dedykowaną zakładką na mojej stronie właśnie do tego celu.

## Obsidian

Ze skrótów współpracujących z aplikacją Obsidian korzystam zdecydowanie najczęściej. Do ich poprawnego działania niezbędne jest zainstalowanie programu [Actions for Obsidian](https://actions.work/actions-for-obsidian) i wtyczki [Actions URI](obsidian://show-plugin?id=actions-uri), chociaż możliwe jest takie ich ustawienie, aby to nie było konieczne. Ja wolę jednak *pójść na łatwiznę* i nie ustawiać wszystkiego *na piechotę*.

- **Add weather to daily note in Obsidian** - jak sama nazwa wskazuje skrót ten dodaje informacje pogodowe do notatki codziennej w miejsce placeholderów. Można to było zrobić na kilka sposobów, ale ja postanowiłem dodawać te informacje jako properties.

**Jakie konkretnie informacje dodaję:**

```yaml
weather: "Pochmurnie" - warunki pogodowe
min: "11 st. C" - najniższa temperatura
maks: "25 st. C" - najwyższa temperatura
sunrise: "05:02" - czas wschodu słońca
sunset: "20:04" - czas zachodu słońca
day: "123" - dzień w roku
```

- **Add calendar events to daily note in Obsidian** - skrót ten dodaje wydarzenia z kalendarza do notatki codziennej w kolejności chronologicznej, na podstawie daty i godziny rozpoczęcia danego wydarzenia.

**Domyślny format wydarzeń wygląda następująco:**

```
- [ ] godzina rozpoczęcia - godzina zakończenia nazwa wydarzenia
```

**A ostatecznie wygląda to mniej więcej tak:**

- [ ] 18:00 - 19:00 Nazwa wydarzenia

Wydarzenia oznaczam jako ukończone (czyli klikam checkbox) po ich ukończeniu. Czasami dodaję jakiś komentarz.

- **Add reminders to daily note in Obsidian** - skrót ten dodaje zadania do zrobienia z aplikacji Przypomnienia (Reminders), która służy mi też jako narzędzie do przechwytywania wszystkiego (inbox). Format jest podobny do wydarzeń z kalendarza, ale bez godziny rozpoczęcia i zakończenia.

- [ ] nazwa przypomnienia

W zasadzie nie zapisuję sobie zadań do zrobienia. Zapisuję za to np. strony intternetowe czy inne rzeczy z internetu, bo aplikacja Przypomnienia jest łatwo dostępna w menu udostępniania i działa szybko i bezproblemowo. Do takich zapisanych rzeczy dodaję tylko datę, najczęściej jutrzejszą, bo inaczej nie zostaną dodane do notatki codziennej.

- **Add media to Obsidian** - skrót ten wyświetla menu, z którego mogę wybrać rodzaj treści (gry, filmy, seriale). W zależności od wyboru aktywuje komendę, aby dodać wybraną treść jako notatkę w Obsidian za pomocą dedykowanej wtyczki (Game search, Moviegrabber).

- **Add item to Obsidian** - skrót ten dodaje notatkę na temat jakiejś rzeczy, korzystając z szablonu. Informacje dodaję ręcznie już w Obsidianie, ale planuję rozbudować ten skrót, żeby można było wszystko dodać za jego pomocą.

- **Clip to Obsidian** - skrót ten dodaje skopiowany link jako notatkę. W zależności od rodzaju treści wykorzystywany jest inny szablon. Można w ten sposób zapisać treść całego artykułu, film z YT czy nawet wpis z Mastodona.

## Travel

Skróty te wykorzystuję do nawigacji.

- **Directions to home** - skrót ten uruchamia trasę do adresu domowego w aplikacji Apple Maps.

- **Directions to next event** - skrót ten wyświetla listę nadchodzących wydarzeń z kalendarza, które mają określone miejsce, a następnie uruchamia do wybranego trasę w Apple Maps.

- **Share my location** - skrót ten udostępnia link do mapy z zaznaczoną moją lokalizacją w iMessage wybranym kontaktom.

## Calendar

Skróty te wykorzystuję do dodawania określonych wydarzeń do kalendarza.

- **Add event to calendar** - skrót ten tworzy nowe wydarzenie w kalendarzu prywatnym, który udostępniam też żonie.

- **Add media to calendar** - skrót ten tworzy nowe wydarzenie w kalendarzu do śledzenia konsumpcji mediów w zależności od rodzaju treści z dedykowaną ikonką w tytule (🎮 - gry, 🍿 - filmy, 📺 - seriale).

- **Add work to calendar** - skrót ten tworzy nowe wydarzenie w kalendarzu pracowym.

## Podcasts

- **Play podcast** - skrót ten odtwarza ostatnio odtwarzany podcast lub następny w kolejce.

- **Go back** - skrót ten przewija aktualnie odtwarzany podcast o 60 sekund do tyłu.

- **Skip ahead** - skrót ten przewija aktualnie odtwarzany podcast o 120 sekund do przodu (zwykle właśnie tyle trwają segmenty sponsorowane).

## Inne

- **Get device storage** - skrót ten pokazuje okienko z aktualnym stanem zapełnienia pamięci urządzenia.

- **Speak article** (in Polish, in English) - skrót ten odczytuje na głos artykuł w wybranym języku.

- **Translate text** - skrót ten tłumaczy tekst na wybrany język.

- **Find RSS feed** - skrót ten znajduje link do subskrybowania kanału RSS podanej strony.

- **Count letters and words** - skrót ten liczy litery i wyrazy w podanym tekście.

- **Split last two apps** - skrót ten wyświetla dwie ostatnio otwarte aplikacje na podzielonym ekranie (tylko macOS).

## Automatyzacje

- Gdy połączę się z samochodem, wyjście audio zmienia się na AirPods, zaczyna odtwarzać się podcast i uruchamia się trasa na najbliższe wydarzenie z kalendarza w Apple Maps.
- Gdy będę w odległości 500 metrów od miejsca pracy mojej żony (w godzinach, kiedy kończy), dostanie ona smsa z informacją, że już jestem, bo czasami ją odbieram, kiedy sam kończę pracę w pobliżu.
- Gdy otworzę jedną z kilku wybranych aplikacji (typu Facebook, Instagram, TikTok) i akurat nie korzystam ze słuchawek, głośność audio mojego telefonu zostanie zmniejszona do 0%.
- Gdy otworzę jedną z kilku aplikacji (typu Safari, YouTube) blokada orientacji mojego telefonu zostanie odblokowana, bo domyślnie jest zablokowana.

To oczywiście nie wszystko. Korzystam także z trybów skupienia, które też mają swoje automatyzacje, jak np. zmiana ekranu głównego na iOS. Wszystko opiszę w swoim czasie!
