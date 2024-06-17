
# Image Colorization Project
Projekt koncentruje się na kolorowaniu czarno-białych obrazów za pomocą różnych architektur takich jak U-Net i autoencodery. Wykorzystano zbiór danych CIFAR-10 przekonwertowaną na przestrzeń kolorów LAB.
### Zależności Projektu

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

Upewnij się, że używasz odpowiedniej wersji Pythona (zalecana wersja 3.6 lub nowsza), aby uniknąć problemów z kompatybilnością.


### Uwagi dotyczące instalacji
Korzystanie z GPU do przyspieszenia obliczeń przez TensorFlow wymaga kompatybilnej karty graficznej NVIDIA, zainstalowanego NVIDIA CUDA Toolkit, NVIDIA cuDNN, odpowiednich sterowników NVIDIA oraz konfiguracji TensorFlow do pracy z GPU.