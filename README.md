
# Image Colorization Project
Projekt koncentruje się na kolorowaniu czarno-białych obrazów za pomocą różnych architektur takich jak U-Net i autoencodery. Wykorzystano zbiór danych CIFAR-10 przekonwertowaną na przestrzeń kolorów LAB.

## Struktura projektu

- **image_colorization.ipynb** - plik zawiera ładowanie danych, przetwarzanie, tworzenie modeli, trenowanie i testowanie.
- [Image Colorization Project Report](https://github.com/p-malecki/img-colorization/blob/main/Image%20Colorization%20Project%20Report.pdf) - plik zawiera dokumentację projektu.
- `/example_imgs` - folder z przykładowymi zdjęciami do testowania koloryzacji.


## Uruchamianie kodu


1. Umieść kolorowe zdjęcia o rozmiarze 32x32 pixele w formacie jpg/png w folderze `/example_imgs`
2. Pokoloruj czarnobiałe wersje z użyciem przetrenowanych modeli:

### Użycie Pipeline

1. **Inicjalizacja Pipeline**
   ```python
   pipeline = Pipeline([
       ('image_processing', ImageProcessingPipeline(model_list)),
       ('image_comparing', ImageModelComparingPipeline())
   ])
   ```
   Pipeline jest zbudowany z dwóch głównych komponentów. `ImageProcessingPipeline` ładuje obrazy, konwertuje jen a przestrzeń kolorów LAB i zmienia rozdzielczość na 32x32, natomiast `ImageModelComparingPipeline` przyjmuje listę modeli, które będą używane do kolorowania obrazów i jest odpowiedzialny za porównanie wyników kolorowania.

2. **Przygotowanie Ścieżki do Obrazów**
   ```python
   path = './example_imgs/bw'
   ```
   Ścieżka do folderu zawierającego czarno-białe obrazy, które będą przetwarzane.

3. **Uruchomienie Pipeline**
   ```python
   pipeline.fit(path)
   ```
   Metoda `fit` uruchamia cały pipeline, przetwarzając obrazy znajdujące się w podanej ścieżce. Obrazy są kolorowane za pomocą różnych modeli.

## Zależności Projektu

Plik `requirements.txt` zawiera listę zależności niezbędnych do uruchomienia projektu. Aby zainstalować wszystkie wymagane biblioteki, wykonaj poniższą komendę w terminalu:

```bash
pip install -r requirements.txt
```

#### Lista zależności (wybrane):

```
numpy==1.26.4
matplotlib==3.4.2
tensorflow==2.16.1
scikit-image==0.23.2
scikit-learn==0.24.2
opencv-python==4.10.0.82
```

Korzystanie z GPU do przyspieszenia obliczeń przez TensorFlow wymaga kompatybilnej karty graficznej NVIDIA, zainstalowanego NVIDIA CUDA Toolkit, NVIDIA cuDNN, odpowiednich sterowników NVIDIA oraz konfiguracji TensorFlow do pracy z GPU.
## Screenshots

![original_sample](https://raw.githubusercontent.com/p-malecki/img-colorization/main/Results/original_sample.png)

![unet_skip_connections_sample](https://raw.githubusercontent.com/p-malecki/img-colorization/main/Results/unet_skip_connections_sample.png)

