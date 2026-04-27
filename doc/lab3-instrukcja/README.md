# Temat: EDA, klasteryzacja i redukcja wymiarów
## Cel zajęć
Celem laboratorium jest krótkie wejście w eksploracyjną analizę danych (EDA) oraz przygotowanie gruntu pod metody nienadzorowane: klasteryzację i redukcję wymiarów do wizualizacji.

Docelowo chcemy pracować na danych studenckich, ale w tej wersji laboratorium korzystamy ze zbioru Titanic jako zbioru referencyjnego.

## Charakter laboratorium
Materiały są podzielone na część podstawową oraz osobne notebooki rozszerzające dla chętnych:
- `notebooks/lab3_eda_clustering.ipynb` — wersja podstawowa,
- `notebooks/lab3-tsne-umap.ipynb` — redukcja wymiarów na `digits`,
- `notebooks/lab3-geopandas.ipynb` — krótki przykład wizualizacji geograficznej.

## Przygotowanie środowiska z użyciem `uv`
W katalogu `Lab3` uruchom:

```bash
uv sync
```

Notebook podstawowy:

```bash
uv run jupyter lab notebooks/lab3_eda_clustering.ipynb
```

Notebooki rozszerzające:

```bash
uv run jupyter lab notebooks/lab3-tsne-umap.ipynb
uv run jupyter lab notebooks/lab3-geopandas.ipynb
```



## Uwaga techniczna
- Środowisko podstawowe obejmuje notebook główny oraz `GeoPandas`.
- `UMAP` moze wymagać osobnego doinstalowania lub pinowania zależności w tym środowisku Python 3.10 ze względu na problem `llvmlite/numba` z nowym `setuptools`.
- Jeśli chcesz uruchomić te przykłady lokalnie, najbezpieczniej instalować je osobno i warunkowo, a notebooki zawierają odpowiednie komunikaty.
