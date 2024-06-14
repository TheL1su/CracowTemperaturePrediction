# Cracow Temperature Prediction

Tematem projektu jest predykcja temperatury dla Krakowa w ciągu najbliższych 30 lat.

Dane zostały pobrane ze strony: https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data.  
Szczególnie interesował mnie plik o nazwie GlobalLandTemperaturesByMajorCity.csv. Zawiera on temperature mierzoną pierwszego dnia każdego miesiąca, w 3448 różnych miastach z całego świata. Rozpoczęcię pomiarów wachało się w zależności od miasta. Dla Krakowa, ciągłe dane zaczynają się w 1753 roku. Z powodu rozmiaru pliku (ponad 500mb) został on obcięty do danych tylko i wyłącznie z Krakowa i zapisany pod nazwą cracow.csv.

Dla każdego roku pomiarów (od 1753 do 2012 roku) została wyliczona średnia temperatura, na tak przygotanych danych wykonano regresję.  
Do projektu zostały wykorzystane 3 modele regresji:
- LinearRegression z PolynomialFeatures
- ElasticNet
- SVR z kernelem poly

Dane zostały podzielone na trening i test w dwóch stosunkach:
- 9/1, dane od 1753 do 1986 jako trening oraz dane od 1987 do 2012 jako test
- 4/1, dane od 1753 do 1960 jako trening oraz dane od 1961 do 2012 jako test
Na obydwóch podziałach zostały nauczone wszystkie modele.
Z powodu predykcji szeregu czasowego dane musiały zostać podzielone w sposób ciągły.

Wykorzystywane metryki:
- błąd średniokwadratowy (MSE)
- średni błąd bezwględny (MAE)

**Wyniki** <br />
Zobaczmy najpierw na wykres danych.<br />
![CracowAverateTemperature](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/415725e1-043c-436f-8a6a-07f2c93086ad)
W ciągu ostatnich lat 60-70 lat temperatura w Krakowie zaczęła wzrastać.  

Wartości błędów dla modeli z danymi testowymi uzyskanyc ze stosunku podziału 9/1:  
![test_90](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/77cd114e-f01a-45d1-b38f-d387772b1be9)  

Najlepiej poradził sobie model LinearRegression, przedstawmy rezultat jego predykcji:  

![CracowPrediction_90](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/41103489-fb0a-42a5-82c2-8c37779f1a01)  

oraz dokładne wartości:  

![predicted_90](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/081fb1d3-7b2e-4235-a77d-b702b8036b09)


Teraz wartości błędów dla modeli z danymi testowymi uzyskanyc ze stosunku podziału 4/1:  
![test_80](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/b1cdcaec-5737-475e-b1e3-8880fdd0a5aa)  
Tym razem również najlepiej poradził sobie model LinearRegression, uzyskał najlepsze wyniki dla wszystkich modeli z obu podziałów. A tutaj jego predykcje:  
![CracowPrediction_80](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/0eb4d6b5-8a08-4076-88c9-3a42b40836dc)

oraz dokładne wartości:  
![predicted_80](https://github.com/TheL1su/CracowTemperaturePrediction/assets/161051757/22111f64-f9be-4bbb-b58f-2edd0c908812)  

**Wniosek**
W ciągu najbliższych 30 lat średnia temperatura wzrośnie w Krakowie o około 0.5 stopnia Celsjusza. W porównaniu do najmniejszej zaobserwowanej średniej temperatury jest to różnica aż 4 stopnie.

