# EKV Malinski — landing page usług elektroinstalacyjnych

Statyczny prototyp strony prezentującej usługi elektryczne na rynku niemieckim. Łączy ścieżkę B2B dla podwykonawstwa przemysłowego ze ścieżką B2C, w której zachętą do kontaktu jest checklista dotycząca instalacji.

**Status:** demonstracja strony i oferty. Formularz checklisty pokazuje komunikat demonstracyjny; repozytorium nie zawiera systemu wysyłki materiałów.

## Co prezentuje projekt

- Nawigację do sekcji usług, korzyści, procesu, FAQ i kontaktu.
- Rozdzielenie oferty na podwykonawstwo przemysłowe oraz instalacje prywatne i OZE.
- Sekcję lead magnetu z formularzem imienia, e-maila i rodzaju projektu.
- Rozwijane FAQ z zamykaniem pozostałych odpowiedzi w tej samej kolumnie.
- Responsywny układ, kontakt przez `mailto:` i telefoniczne CTA.

## Technologia i struktura

Całość zawiera [index.html](index.html): semantyka strony, osadzony CSS, formularz z handlerem inline oraz krótki skrypt FAQ. Projekt używa HTML, CSS i JavaScript bez frameworka. Google Fonts dostarcza kroje DM Sans i Space Mono.

```text
.
├── index.html   # oferta, formularz, style i FAQ
└── README.md
```

Nie ma npm, bundlera, backendu, bazy danych ani konfiguracji sekretów.

## Uruchomienie lokalne

Wymagane: Git, Python 3 i współczesna przeglądarka.

```sh
git clone https://github.com/dzwoniar/EKVmalinski.de.git
cd EKVmalinski.de
python -m http.server 8000
```

Otwórz [http://localhost:8000](http://localhost:8000). Na Windows można użyć `py -3 -m http.server 8000`. Serwer zatrzymasz przez `Ctrl+C`; instalacja zależności nie jest potrzebna. Fonty wymagają połączenia z Google Fonts, a odnośniki kontaktowe korzystają z aplikacji użytkownika.

## Obsługa danych i integracje

Handler `onsubmit` zatrzymuje formularz i wyświetla `alert` z informacją o demo. Nie wykonuje żądania do MailerLite ani innego serwisu. Odnośnik `mailto:` otwiera program pocztowy z adresem odbiorcy — sam nie wysyła wiadomości. Jedyny końcowy skrypt steruje stanem elementów FAQ.

## Granice demonstracji

- Repozytorium nie zawiera pliku checklisty, procesu zapisu do newslettera ani automatycznej wysyłki.
- Telefon, adres, dokumenty prawne i część odnośników pozostają wartościami zastępczymi.
- Treści o uprawnieniach, normach, oszczędnościach i referencjach są elementami prototypu. Kod nie stanowi potwierdzenia tych deklaracji ani dokumentacji zgodności instalacji.
- Przed rzeczywistym użyciem formularza należy dodać usługę obsługi zgłoszeń, walidację po stronie serwera i docelowe treści kontaktowe. Kluczy usług nie należy umieszczać w HTML.

Repozytorium nie zawiera automatycznych testów. Przy zmianach można sprawdzić nawigację, zachowanie FAQ w obu kolumnach, widok mobilny i komunikat demonstracyjny formularza bez wysyłania wiadomości.
