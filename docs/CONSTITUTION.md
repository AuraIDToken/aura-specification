# Constitution — Aura Specification

Version: **1.0.0**  
Status: **Active**

## 1. Cel

Constitution definiuje zasady zarządzania projektem Aura Specification:

- role i odpowiedzialności,
- proces podejmowania decyzji,
- standard jakości zmian,
- reguły publikacji i wersjonowania.

## 2. Zasady nadrzędne

1. **Jawność** – decyzje i uzasadnienia są dokumentowane.
2. **Bezpieczeństwo** – bezpieczeństwo ma priorytet nad wygodą.
3. **Stabilność** – zmiany nie mogą destabilizować ekosystemu.
4. **Spójność** – APS i Constitution muszą pozostawać zgodne.
5. **Rozliczalność** – każda zmiana ma właściciela i historię decyzji.

## 3. Role

- **Maintainerzy** – utrzymują repozytorium i akceptują zmiany.
- **Autorzy zmian** – przygotowują propozycje, implementują i dokumentują wpływ.
- **Recenzenci** – oceniają poprawność merytoryczną i zgodność z zasadami.

## 4. Proces zmian

### 4.1 Typy zmian

- **Normatywne** – zmieniają wymagania APS/Constitution.
- **Nienormatywne** – redakcja, doprecyzowanie bez zmiany znaczenia.

### 4.2 Wymagania dla PR

Każdy PR musi zawierać:

1. opis zakresu i celu,
2. klasyfikację zmiany (normatywna/nienormatywna),
3. wpływ na kompatybilność i migrację,
4. aktualizację wersji (jeśli wymagana).

### 4.3 Akceptacja

- Zmiany normatywne wymagają co najmniej jednej recenzji maintainera.
- Zmiany krytyczne bezpieczeństwa mają priorytet i ścieżkę przyspieszoną.

## 5. Polityka wersjonowania dokumentacji

- Wersje APS i Constitution są koordynowane.
- Zmiana normatywna wymaga aktualizacji numeru wersji.
- Zmiana nienormatywna może pozostać w tej samej wersji PATCH.

## 6. Kompatybilność i migracje

- Zmiany łamiące kompatybilność muszą zawierać plan migracji.
- Okres przejściowy i zasady deprecjacji muszą być jasno opisane.

## 7. Jakość i zgodność

Przed akceptacją zmiany należy potwierdzić:

- spójność terminologiczną,
- brak sprzeczności między dokumentami,
- kompletność sekcji wymaganych przez APS i Constitution.

## 8. Bezpieczeństwo i ujawnianie podatności

- Potencjalne podatności należy zgłaszać maintainerom bez publicznego ujawnienia szczegółów do czasu oceny ryzyka.
- Poprawki bezpieczeństwa powinny minimalizować wpływ na interfejsy publiczne.

## 9. Rozstrzyganie sporów

- Spory merytoryczne rozstrzyga maintainer odpowiedzialny za obszar.
- W razie braku konsensusu decyzja musi zawierać uzasadnienie i skutki.

## 10. Wejście w życie i zmiany Constitution

- Constitution obowiązuje od momentu publikacji wersji.
- Zmiana Constitution podlega tym samym zasadom co zmiana normatywna APS.
