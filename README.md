# Projekt Analizy Sentimentów na Twitterze

Ten projekt koncentruje się na czyszczeniu, analizie danych oraz porównywaniu różnych algorytmów do przetwarzania języka naturalnego. Użyto zbioru danych z postami na Twitterze z Kaggle, który zawiera wiele potocznych wyrażeń, co czyni go odpowiednim do analizy sentimentu.

## Przegląd Procesu

Projekt obejmuje następujące kroki:

1. Przegląd i analiza danych
2. Czyszczenie i przetwarzanie danych
3. Budowanie i ocena modeli AI

## Użyte Biblioteki

- Pandas
- Seaborn
- SciKit Learn
- NLTK

## Przegląd Danych

Zbiór danych jest podzielony na zestawy treningowe, testowe i walidacyjne:
- `train.csv`
- `test.csv`
- `val.csv`

Te pliki są połączone w jeden DataFrame do przetwarzania. Przegląd danych oraz dystrybucja klas są przedstawione za pomocą wizualizacji w Seaborn.

## Czyszczenie i Przetwarzanie Danych

### Usuwanie Odstających Wartości i Duplikatów

- Obliczanie długości każdego tweeta.
- Usuwanie tweetów, których długość przekracza określony próg.
- Usuwanie zduplikowanych tweetów.

### Zmniejszanie Wielkości Klas

Zbiór danych jest zmniejszany, aby zbalansować klasy, poprzez przyjęcie wielkości najmniejszej klasy i dostosowanie reszty do tej wielkości.

### Niestandardowy Tokenizer

Zbudowano niestandardowy tokenizer przy użyciu NLTK, który:
- Konwertuje emoji na słowa.
- Usuwa wzmianki (@).
- Zastępuje popularne skróty pełnymi słowami.
- Stosuje stemming.

## Budowanie Modeli AI

Zbudowano i porównano dwa modele:
1. Naive Bayes (CNB)
2. Stochastic Gradient Descent (SGD)

Modele te są oceniane przy użyciu oryginalnych oraz zmniejszonych zbiorów danych.

### Pipeline Modeli

- CountVectorizer z niestandardowym tokenizerem
- ComplementNB
- SGDClassifier

### Ocena Modeli

Modele są oceniane przy użyciu:
- Raportu klasyfikacyjnego
- Macierzy pomyłek
- F1 Score

### Testowanie Praktyczne

Modele są testowane na nowych zdaniach, aby ocenić ich praktyczną wydajność.

## Optymalizacja Hiperparametrów

RandomizedSearchCV jest używany do optymalizacji hiperparametrów SGDClassifier.

## Wyniki

Oba modele są porównywane pod względem dokładności i F1 Score. Model Complement Naive Bayes zazwyczaj osiąga lepsze wyniki z zredukowanymi danymi, podczas gdy SGD pokazuje obiecujące wyniki po dalszej optymalizacji hiperparametrów.

## Wnioski

Pomimo surowego i potocznego charakteru zbioru danych, możliwe jest stworzenie klasyfikatora sentimentu. Jednak skuteczność klasyfikatora zależy od złożoności struktury zdania i kontekstu.

## Instrukcje do Uruchomienia Projektu

1. Upewnij się, że masz zainstalowane wymagane biblioteki:
   ```bash
   pip install pandas seaborn scikit-learn nltk
Umieść pliki zbioru danych (train.csv, test.csv, val.csv) w katalogu projektu.

Uruchom dostarczony kod w Jupyter Notebook lub dowolnym środowisku Python.

Notebook wygeneruje wyniki analizy, oceny modeli oraz testów praktycznych.

Przyszłe Prace
Eksploracja dodatkowych technik przetwarzania tekstu.
Implementacja bardziej zaawansowanych modeli, takich jak LSTM lub BERT.
Zwiększenie rozmiaru zbioru danych w celu lepszej generalizacji modeli.
Autor
Projekt został stworzony przez [Twoje Imię].
