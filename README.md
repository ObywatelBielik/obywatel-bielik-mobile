# Obywatel BIELIK Mobile

Repozytorium zawierające aplikację mobilną Obywatel BIELIK zbudowaną przy użyciu frameworka Flutter.

## Opis projektu

Obywatel BIELIK to aplikacja służąca do gromadzenia opisów zdjęć (anotacji) przez społeczność, w tym seniorów i lokalnych aktywistów. Aplikacja umożliwia użytkownikom opisywanie losowych zdjęć lub dodawanie własnych zdjęć wraz z opisami.

## Struktura projektu

```
obywatel-bielik-mobile/
├── android/               # Konfiguracja specyficzna dla platformy Android
├── ios/                   # Konfiguracja specyficzna dla platformy iOS
├── lib/                   # Główny kod źródłowy aplikacji
│   ├── api/               # Klienty API i logika integracji z backendem
│   ├── config/            # Konfiguracja aplikacji
│   ├── models/            # Modele danych
│   ├── screens/           # Ekrany aplikacji
│   ├── theme/             # Definicje motywu i stylizacji
│   ├── utils/             # Narzędzia pomocnicze
│   └── widgets/           # Komponenty widżetów wielokrotnego użytku
├── assets/                # Zasoby (obrazy, fonty, itp.)
├── test/                  # Testy
│   ├── unit/              # Testy jednostkowe
│   ├── widget/            # Testy widżetów
│   └── integration/       # Testy integracyjne
├── pubspec.yaml           # Definicja zależności i metadanych
└── README.md              # Dokumentacja
```

## Funkcjonalności aplikacji

- Rejestracja i logowanie użytkowników (Google, Facebook, Apple)
- Wybór zespołu i konfiguracja profilu
- Strona startowa z:
  - Statystykami społeczności
  - Celem tygodniowym
  - Osiągnięciami użytkownika
  - Rankingami użytkowników i zespołów
- Opisywanie losowych zdjęć:
  - Wyświetlanie losowego zdjęcia
  - Generowanie automatycznego opisu
  - Dodawanie opisu narracyjnego i faktograficznego
  - Nagrywanie głosowe opisów
  - Korekta opisów przy pomocy AI
- Opisywanie własnych zdjęć:
  - Wykonywanie zdjęć aparatem
  - Wybieranie zdjęć z galerii
  - Dodawanie opisów
- Zarządzanie kontem użytkownika

## Technologie

- **Framework:** Flutter 3.x
- **Język programowania:** Dart 3.x
- **Zarządzanie stanem:** Provider/Riverpod
- **Nawigacja:** Go Router
- **Zarządzanie zasobami lokalnymi:** Hive / SharedPreferences
- **Komunikacja z API:** Dio/http
- **Testy:** Flutter Test, Integration Test

## Wymagania deweloperskie

- Flutter SDK 3.x
- Dart SDK 3.x
- Android Studio / Visual Studio Code z wtyczką Flutter
- Dla kompilacji iOS: macOS z Xcode
- Dla kompilacji Android: Android SDK

## Ustawienie środowiska deweloperskiego

1. Zainstaluj Flutter SDK: [instrukcje instalacji](https://flutter.dev/docs/get-started/install)

2. Sklonuj repozytorium:
```bash
git clone https://github.com/organization/obywatel-bielik-mobile.git
cd obywatel-bielik-mobile
```

3. Zainstaluj zależności:
```bash
flutter pub get
```

4. Uruchom wersję debug:
```bash
flutter run
```

## Konfiguracja środowiska

Aplikacja korzysta z plików konfiguracyjnych dla różnych środowisk:
- `.env.dev` - Środowisko deweloperskie
- `.env.staging` - Środowisko testowe
- `.env.prod` - Środowisko produkcyjne

Do przełączania między środowiskami używany jest pakiet `flutter_config`.

## Testowanie

### Testy jednostkowe
```bash
flutter test
```

### Testy widżetów
```bash
flutter test test/widget
```

### Testy integracyjne
```bash
flutter drive --target=test_driver/app.dart
```

## Wersjonowanie i wydania

Aplikacja używa wersjonowania semantycznego (MAJOR.MINOR.PATCH).

Aby przygotować nową wersję:
1. Zaktualizuj numer wersji w `pubspec.yaml`
2. Utwórz tag w git
```bash
git tag -a v1.0.0 -m "Wersja 1.0.0"
git push origin v1.0.0
```

## Wytyczne stylowania kodu

- Kod powinien być zgodny z [Effective Dart](https://dart.dev/guides/language/effective-dart)
- Używaj `flutter format` przed każdym commitem
- Stosuj się do wytycznych dla UI/UX zdefiniowanych w katalogu `docs/design`

## Dostępność

Aplikacja jest tworzona z uwzględnieniem dostępności (WCAG 2.2), co jest szczególnie ważne dla projektu skierowanego m.in. do seniorów:
- Wszystkie obrazy mają opisy alternatywne
- Interfejs jest dostosowany do czytników ekranu
- Odpowiednie kontrasty kolorystyczne
- Skalowalne rozmiary tekstu

## Licencja

Projekt jest dostępny na licencji [licencja]. Szczegółowe informacje w pliku LICENSE.
