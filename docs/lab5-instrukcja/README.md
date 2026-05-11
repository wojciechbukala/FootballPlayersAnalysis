# Temat: Weryfikacja hipotez

Notebook podstawowy (w trakcie przygotowania rozszerzenie w Julia).

Notebooki:
- `notebooks/*.ipynb`

## Czym jest bootstrap?

Bootstrap to technika resamplingu polegająca na wielokrotnym losowaniu z próby (z zastępowaniem) w celu przybliżenia rozkładu statystyki próbnej. Umożliwia ona wyznaczanie przedziałów ufności czy oceny błędu standardowego bez silnych założeń parametrycznych — szczególnie przydatna, kiedy próbka jest mała lub jej rozkład nie jest znany dokładnie.

## Czym i kiedy użyć testu Manna-Whitneya?

Test Manna-Whitneya to nieparametryczny odpowiednik testu t dla niezależnych prób. Używamy go, gdy obserwacje nie spełniają założeń normalności lub są porządkowe, a chcemy porównać mediany dwóch grup. Nie wymaga określania rozkładu i jest odporny na wartości odstające, ale zakłada podobne kształty rozkładów poza przesunięciem mediany.

## Co dokładnie tu sprawdzamy w kodzie?

- `shapiro_x = stats.shapiro(x)` oraz `shapiro_y = stats.shapiro(y)` – test Shapiro-Wilka sprawdza, czy każda z dwóch badanych prób pochodzi z rozkładu normalnego (czyli czy możemy założyć normalność danych przed zastosowaniem testu parametrycznego).
- `levene = stats.levene(x, y)` – test Levene'a ocenia równość wariancji między grupami, co jest jednym z założeń klasycznego testu t.
- `ttest = stats.ttest_ind(x, y, equal_var=False)` – test t z ustawieniem `equal_var=False` (Welcha) porównuje średnie dwóch niezależnych prób bez zakładania równości wariancji, wykorzystując wiedzę z Shapiro i Levene do decydowania o odpowiedniej wersji testu.
