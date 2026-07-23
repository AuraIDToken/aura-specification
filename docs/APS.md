# APS — Aura Protocol Specification

Wersja: **1.0.0**  
Status: **Active**

## 1. Cel i zakres

APS definiuje standard dla komponentów i interfejsów ekosystemu Aura:

- wspólne pojęcia i model domenowy,
- kontrakty API i formaty danych,
- reguły bezpieczeństwa i zgodności,
- wymagania jakościowe oraz operacyjne.

## 2. Definicje

- **Klient** – podmiot korzystający z interfejsu APS.
- **Usługa** – komponent realizujący kontrakt APS.
- **Token AuraID** – nośnik tożsamości/atrybutów w granicach zdefiniowanych przez APS.
- **Profil zgodności** – zestaw wymagań niezbędnych do uznania implementacji za zgodną.

## 3. Zasady projektowe

1. **Security by default** – bezpieczne ustawienia domyślne.
2. **Explicit contracts** – jawnie opisane wejścia, wyjścia i błędy.
3. **Backward compatibility** – kompatybilność w ramach wersji głównej.
4. **Determinism** – przewidywalne zachowanie dla tych samych danych wejściowych.
5. **Auditability** – możliwość śledzenia i wyjaśnienia decyzji systemu.

## 4. Architektura logiczna

APS zakłada architekturę opartą o:

- warstwę tożsamości i autoryzacji,
- warstwę usług domenowych,
- warstwę integracji i transportu,
- warstwę obserwowalności (logi, metryki, ślady).

Każda warstwa musi definiować:

- odpowiedzialności,
- granice zaufania,
- interfejsy wejściowe/wyjściowe.

## 5. Kontrakty interfejsów

### 5.1 Wymagania ogólne

- Wszystkie publiczne interfejsy muszą mieć wersję.
- Każda operacja musi posiadać:
  - identyfikator operacji,
  - schemat walidacji wejścia,
  - schemat odpowiedzi sukcesu,
  - listę błędów i kodów.

### 5.2 Stabilność

- Usunięcie pola/operacji wymaga deprecjacji.
- Deprecjacja musi mieć minimalny okres przejściowy.

## 6. Model danych

Model danych APS musi:

- używać jednoznacznych identyfikatorów,
- definiować pola obowiązkowe i opcjonalne,
- definiować ograniczenia walidacyjne,
- mieć politykę serializacji i deserializacji.

## 7. Bezpieczeństwo

Minimalne wymagania:

- uwierzytelnianie i autoryzacja dla operacji wrażliwych,
- walidacja danych wejściowych na granicach systemu,
- ochrona przed nadużyciami (rate limiting/throttling),
- bezpieczne przechowywanie tajemnic i kluczy,
- zasada najmniejszych uprawnień.

## 8. Prywatność i zgodność

- Dane osobowe przetwarzane wyłącznie w zakresie celu.
- Retencja danych musi być zdefiniowana i ograniczona.
- Dostęp do danych audytowalny i rozliczalny.

## 9. Niezawodność i operacje

- Krytyczne operacje muszą być idempotentne lub bezpieczne przy ponowieniu.
- Implementacje powinny definiować SLO/SLI.
- Obsługa błędów musi rozróżniać błędy klienta i serwera.

## 10. Wersjonowanie

APS używa semantycznego wersjonowania:

- **MAJOR** – zmiany niekompatybilne,
- **MINOR** – nowe funkcje kompatybilne wstecz,
- **PATCH** – poprawki bez zmian kontraktu.

## 11. Zgodność implementacji

Implementacja zgodna z APS musi:

1. spełniać wymagania bezpieczeństwa,
2. spełniać wymagania kontraktowe,
3. przejść testy zgodności określone dla profilu.

## 12. Zarządzanie zmianą

Wszystkie zmiany APS:

- muszą być opisane w PR z uzasadnieniem,
- muszą wskazywać wpływ na zgodność i migrację,
- podlegają regułom z `docs/CONSTITUTION.md`.
