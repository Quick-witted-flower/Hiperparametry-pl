#Hiperparametry

##Wprowadzenie
Celem tego projektu jest zastosowanie Grid Search do wyboru optymalnych hiperparametrów dla wcześniej utworzonego pipeline’u. Pipeline łączy preprocessing danych oraz model uczenia maszynowego. Projekt obejmuje eksplorację przestrzeni hiperparametrów, zastosowanie walidacji krzyżowej oraz analizę wyników optymalizacji.

##Kroki realizacji:

    Stworzenie pipeline’u integrującego preprocessing danych i model klasyfikacyjny.

    Zdefiniowanie przestrzeni hiperparametrów do optymalizacji.

    Przeprowadzenie Grid Search z walidacją krzyżową.

    Identyfikacja najlepszych hiperparametrów i ich analiza.

    Ocena skuteczności najlepszego modelu.

##Funkcjonalności

1. Stworzenie Pipeline:

    Pipeline integruje preprocessing danych (np. PCA, funkcje wielomianowe, imputacja brakujących wartości) z modelem klasyfikacyjnym (np. regresją logistyczną). W jego skład wchodzą:

    Imputacja brakujących wartości (np. średnią, medianą).

    Generowanie funkcji wielomianowych.

    Redukcja wymiarowości za pomocą PCA.

    Model regresji logistycznej jako klasyfikator.

2. Definicja siatki hiperparametrów:

Zdefiniowano przestrzeń hiperparametrów, uwzględniając:

    model__C: Współczynnik regularyzacji dla modelu.

    preprocessor__numeric_preprocessing__fill_missings__strategy: Strategia imputacji braków (mean, median).

    preprocessor__numeric_preprocessing__polynomial_features__degree: Stopień funkcji wielomianowych.

    preprocessor__numeric_preprocessing__pca__n_components: Liczba komponentów PCA.

3. Optymalizacja za pomocą Grid Search:

Użyto GridSearchCV z następującymi ustawieniami:

    cv=10: Walidacja krzyżowa z 10 podzbiorami.

    scoring='f1_macro': Optymalizacja wartości F1-macro.

    n_jobs=-1: Wykorzystanie wszystkich dostępnych rdzeni procesora.

    verbose=10: Szczegółowe logi z procesu optymalizacji.

4. Analiza wyników:

Najlepsze hiperparametry zidentyfikowane podczas optymalizacji:

    model__C = 0.12648552168552957

    preprocessor__numeric_preprocessing__fill_missings__strategy = mean

    preprocessor__numeric_preprocessing__pca__n_components = 0.99

    preprocessor__numeric_preprocessing__polynomial_features__degree = 3

    Uzyskany najlepszy wynik walidacji krzyżowej: F1-macro.

5. Porównanie wyników przed i po optymalizacji.

W celu znalezienia najlepszych hiperparametrów dla modelu Logistic Regression zastosowano GridSearchCV z walidacją krzyżową (3-fold). Przed i po optymalizacji przeprowadzono analizę skuteczności modelu przy użyciu następujących metryk:

    F1-score (równowaga między precyzją a czułością)
    Accuracy (dokładność modelu)
    AUC Score (obszar pod krzywą ROC)


Optymalizacja hiperparametrów nie przyniosła znaczącej poprawy wyników.



