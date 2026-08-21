# FC Consulting — strona internetowa (motyw ciemny)

Statyczna strona: czysty HTML, CSS i minimalny JavaScript. Bez procesu budowania
i bez zależności — wystarczy wgrać pliki.

Wersja z sierpnia 2026: cała strona w granacie ze złotymi akcentami, karty z ikonami
liniowymi, numerowany proces, zdjęcie architektury wtopione w sekcję główną.

Treści i stronę przygotowała [Kocia Korektorka](https://www.kociakorektorka.pl/).

## Zawartość

```
index.html                              strona główna
o-nas.html                              podstrona „O nas”
blog.html                               lista artykułów
czym-sa-dotacje-dla-firm.html           artykuł 1
pozyczki-unijne-kiedy-warto.html        artykuł 2
jak-wybrac-finansowanie-dla-firmy.html  artykuł 3

fc-logo.png            logo marki (przezroczyste tło)
hero-budynki.webp      zdjęcie architektury w sekcji głównej
filip.webp             zdjęcie Filipa Chlewińskiego
monika.webp            zdjęcie Moniki Jóźwiak-Bociąg
og-image.png           miniatura przy udostępnianiu linku (1200 × 630 px)
favicon.ico            ikona karty przeglądarki (16/32/48 px w jednym pliku)
favicon-16/32/48/64.png    ikony dla przeglądarek
favicon-192/512.png    ikony dla Androida i ekranów startowych
apple-touch-icon.png   ikona ekranu startowego iOS (180 px)
site.webmanifest       manifest z kolorem motywu
robots.txt             zgoda na indeksowanie + wskazanie sitemapy
sitemap.xml            lista adresów strony
```

Wszystkie pliki muszą leżeć w jednym katalogu — odwołania w kodzie są względne.

## Wdrożenie

1. Wgraj **zawartość** tego katalogu do repozytorium (plik `index.html` w katalogu głównym,
   nie w podfolderze).
2. W Vercelu: **Add New → Project → import repozytorium**, Framework Preset: **Other**.
   Jeśli strona ma leżeć w podfolderze wspólnego repozytorium, ustaw **Root Directory**
   na ten folder.
3. Domena `fcconsulting.com.pl` jest już wpisana we wszystkich plikach: canonical,
   Open Graph, dane strukturalne, `robots.txt` i `sitemap.xml`. Gdyby się zmieniła,
   podmień ją funkcją „znajdź i zamień” we wszystkich sześciu plikach HTML oraz
   w `robots.txt` i `sitemap.xml`.

## Motyw i identyfikacja

Zmienne CSS na początku arkusza w każdym pliku (`:root`):

```
--navy-900  #061020   najciemniejszy: stopka, pasy
--navy-800  #0A1B33   tło podstawowe
--navy-700  #0E2340   panele i sekcje
--navy-600  #14304F   obramowania
--gold      #D6A94A   akcent główny
--gold-lt   #E8C77E   złoto na tekst
--text      #E6EBF2   tekst podstawowy
--text-dim  #A9B6C7   tekst drugorzędny
```

Nagłówki: Cormorant Garamond. Treść: Source Sans 3. Oba z Google Fonts, z podzbiorem
znaków łacińskich rozszerzonych (polskie znaki).

**Uwaga:** style i skrypty są powtórzone w każdym pliku HTML — strona jest statyczna,
bez szablonów. Zmiana wspólnego elementu (kolor, nagłówek, stopka, pozycja w menu)
wymaga poprawienia wszystkich sześciu plików.

## Zdjęcie w sekcji głównej

`hero-budynki.webp` pochodzi z Unsplash (autor: Sean Pollock). Licencja Unsplash
pozwala na użycie komercyjne bez opłat i bez obowiązku podawania autora, ale wskazanie
autorstwa jest mile widziane. Zdjęcie jest przyciemnione i odbarwione, a w kodzie
dodatkowo wygaszane maską, żeby tekst leżał na czystym granacie.

## Do uzupełnienia przed premierą

- [ ] **Polityka prywatności** — plik `polityka-prywatnosci.html`. Linki w stopce i pod
      formularzem już do niego prowadzą. Wymagana, bo formularz zbiera dane osobowe.
- [ ] **Dane rejestrowe w stopce** — w `index.html` znajduje się komentarz
      `[WSTAW: pełna nazwa rejestrowa, NIP, adres siedziby]`. Alternatywnie dane mogą
      znaleźć się wyłącznie w polityce prywatności.
- [ ] **Test formularza** — podłączony do Formspree (`xwlerozq`), wysyłka w tle.
      Po wdrożeniu wyślij testowe zgłoszenie: Formspree przy pierwszym prosi
      o potwierdzenie adresu odbiorcy.
- [ ] **Daty artykułów** — wpisy nie mają dat publikacji.
- [ ] **Zdjęcia zespołu** pochodzą z dwóch różnych sesji i mają inną tonację.
- [ ] **Logo w SVG** i wersja jednokolorowa — obecnie PNG z gradientem.

## Po wdrożeniu

1. Google Search Console — weryfikacja rekordem DNS, zgłoszenie `sitemap.xml`.
2. Rich Results Test — sprawdzenie danych strukturalnych (`ProfessionalService`,
   `FAQPage`, `AboutPage`, `Blog`, `Article`).
3. `Ctrl+U` na opublikowanej stronie — cała treść jest w źródle, więc widzą ją także
   crawlery modeli językowych.
