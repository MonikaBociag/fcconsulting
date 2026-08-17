# FC Consulting — strona internetowa

Statyczna strona (czysty HTML + CSS, minimalny JavaScript). Bez procesu budowania
i bez zależności — wystarczy wgrać pliki.

Treści i stronę przygotowała [Kocia Korektorka](https://www.kociakorektorka.pl/).

## Zawartość

```
index.html                              strona główna
o-nas.html                              podstrona „O nas” (zasady pracy, sylwetki, zasięg)
blog.html                               lista artykułów
czym-sa-dotacje-dla-firm.html           artykuł 1
pozyczki-unijne-kiedy-warto.html        artykuł 2
jak-wybrac-finansowanie-dla-firmy.html  artykuł 3

fc-logo.png            logo marki (przezroczyste tło)
filip.webp             zdjęcie Filipa Chlewińskiego
monika.webp            zdjęcie Moniki Jóźwiak-Bociąg
og-image.png           miniatura przy udostępnianiu linku (1200 × 630 px)
favicon.ico            ikona karty przeglądarki (16/32/48 px w jednym pliku)
favicon-16/32/48/64.png    ikony dla nowoczesnych przeglądarek
favicon-192/512.png    ikony dla Androida i ekranów startowych
apple-touch-icon.png   ikona ekranu startowego iOS (180 px)
site.webmanifest       manifest z kolorem motywu marki
robots.txt             zgoda na indeksowanie + wskazanie sitemapy
sitemap.xml            lista adresów strony
```

Wszystkie pliki muszą leżeć w jednym katalogu — odwołania w kodzie są względne.

## Wdrożenie na Vercelu

1. Utwórz repozytorium na GitHubie i wgraj **zawartość** tego katalogu (plik `index.html`
   musi znaleźć się w katalogu głównym repozytorium, nie w podfolderze).
2. W Vercelu: **Add New → Project → import repozytorium**. Framework preset: **Other**.
3. Podepnij domenę w **Settings → Domains**.
4. **Jeśli domena będzie inna niż `fcconsulting.pl`**, podmień ten adres w plikach
   `index.html`, `o-nas.html`, `blog.html`, trzech plikach artykułów, `robots.txt`
   i `sitemap.xml`. Najprościej funkcją „znajdź i zamień”, szukając `fcconsulting.pl`.
   Adres występuje w znaczniku canonical, w danych Open Graph i w danych strukturalnych.

Subdomena `*.vercel.app` celowo nie indeksuje się w Google — to normalne do czasu
podpięcia własnej domeny. Każdy zapis zmian na GitHubie uruchamia wdrożenie
automatycznie; do bieżącej edycji treści panel Vercela nie jest potrzebny.

## Do uzupełnienia przed premierą

- [ ] **Dane rejestrowe w stopce** — w każdym pliku HTML, w stopce, znajduje się komentarz
      `[WSTAW: pełna nazwa rejestrowa, NIP, adres siedziby]`. Alternatywnie dane mogą
      znaleźć się wyłącznie w polityce prywatności.
- [ ] **Polityka prywatności** — plik `polityka-prywatnosci.html` (linki w stopce i pod
      formularzem już do niego prowadzą). Musi wskazywać administratora danych, bo
      formularz zbiera dane osobowe. Wymagana od dnia premiery.
- [ ] **Test formularza** — formularz jest podłączony do Formspree (`xwlerozq`), wysyłka
      odbywa się w tle. Po wdrożeniu wyślij testowe zgłoszenie: Formspree przy pierwszym
      zgłoszeniu prosi o potwierdzenie adresu odbiorcy. Warto też ustalić w panelu, czy
      powiadomienia mają trafiać na oba adresy (darmowy plan pozwala na dwa).
- [ ] **Daty artykułów** — wpisy nie mają dat publikacji. Jeśli klient chce je pokazywać,
      trzeba je dopisać do kart na `blog.html` i do danych strukturalnych `Article`.
- [ ] **Zdjęcia zespołu** pochodzą z dwóch różnych sesji i mają wyraźnie inną tonację
      (Filip: ciemne wnętrze, Monika: jasne biuro). W sekcji zespołu stoją obok siebie.
      Do rozważenia: korekta tonalna albo nowe kadry z jednej sesji.
- [ ] **Logo w formacie SVG** — obecnie PNG. Przy wysokości 52 px różnica jest niewidoczna,
      ale wektor przyda się na ekranach o wysokiej rozdzielczości i w druku. Warto też
      poprosić grafika o wersję jednokolorową, bo logo ma gradient.

## Po wdrożeniu

1. Google Search Console — weryfikacja rekordem DNS, zgłoszenie `sitemap.xml`.
2. Rich Results Test — sprawdzenie danych strukturalnych (`ProfessionalService`, `FAQPage`,
   `AboutPage`, `Blog`, `Article`).
3. `Ctrl+U` na opublikowanej stronie — cała treść jest w źródle, więc widzą ją także
   crawlery modeli językowych (istotne dla widoczności w AI).

## Uwagi techniczne

- Paleta i typografia wynikają z fiszki marki: granat `#0A1B33`, złoto `#DBA540`,
  Deep Gold `#8B671B` na linki i obrys fokusu. Wszystko siedzi w zmiennych CSS
  w sekcji `:root` na początku arkusza — podmiana koloru to jedna linia.
- Nagłówki: Cormorant Garamond (szeryf), treść: Source Sans 3.
- Animacje: wejście sekcji przy przewijaniu, podświetlenia kart, wskaźnik postępu
  czytania na artykułach. Wszystko wyłącza się przy systemowym ustawieniu
  ograniczonego ruchu (`prefers-reduced-motion`).
- Menu mobilne, rozwijane FAQ i formularz nie wymagają żadnych bibliotek.
- Zdjęcia w formacie WebP, obrazy poza pierwszym ekranem mają `loading="lazy"`.
- Style i skrypty są powtórzone w każdym pliku HTML (strona jest statyczna, bez
  szablonów). Zmiana wspólnego elementu — nagłówka, stopki, koloru — wymaga
  poprawienia wszystkich sześciu plików.
