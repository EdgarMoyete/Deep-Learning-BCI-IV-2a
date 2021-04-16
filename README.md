# Deep-Learning-BCI-IV-2a
Clasificación de imaginación motora en señales de EEG con Deep Learning y Machine Learning utilizando BCI Competition IV dataset 2a

**Modelos para RAW, DWT-Coef, AlfaC3C4 y RWE-DWT:**
* CNN-2D
* CNN-1D
* LSTM
* GRU
* CNN-1D + LSTM
* CNN-1D + GRU
* ConvLSTM2D
* MLP
* SVM
* Random Forest

**Modelos para Espectros-STFT y Escalogramas-CWT**
* CNN-2D
* CNN-2D + LSTM
* CNN-2D + GRU
* ConvLSTM2D
* CNN-3D

**Data Set:**
* BCI Competition IV-2a

### RAW
* Datos crudos, 22 canales con 1000 valores (4seg a 250Hz), filtrado con pasa banda (8Hz-30Hz)
* Input Shape: 288x22000

### RWE-DWT
* RWE con db4 y 2 niveles de descomposicion, 22 canales con 3 valores
* Input Shape: 288x66

### AlfaC3C4
* Alfa (8Hz-13.5Hz), 2 canales (C3 y C4) con 255 valores
* Input Shape: 288x510

### DWT-Coef
* Coeficientes de aproximacion y detalle concatenados de DWT-db4 de 2 niveles de descomposicion, 22 canales con 1013 valores
* Input Shape: 288x22286

### Espectros-STFT
* Espectrogramas con la transformada de Fourier de tiempo corto, ventana de tukey de 0.25

* `STFT-CNN.ipynb`
* `STFT-CNN-CV.ipynb`
* `STFT-CNN-GS.ipynb`
* `STFT-CNN-Predecir.ipynb`
* `STFT-CNN-LSTM.ipynb`
* `STFT-CNN-LSTM-CV.ipynb`
* `STFT-CNN-LSTM-GS.ipynb`
* `STFT-CNN-LSTM-Predecir.ipynb`
* `STFT-CNN-Explorar.ipynb`
* Fine-Tuning.ipynb
* STFT3D-CNN2D-2C-V.ipynb
* STFT3D-CNN2D-2C-V-Resize.ipynb
* STFT3D-CNN2D-H.ipynb
* STFT3D-CNN2D-V.ipynb
* STFT3D-CNN2D-V-DataAug-Explorar.ipynb
* STFT3D-CNN2D-V-Resize.ipynb
* STFT3D-ConvLSTM2D-V-Resize.ipynb
* STFT3D-RNNs-2C-V.ipynb
* STFT3D-RNNs-H.ipynb
* STFT3D-RNNs-Ventaneo.ipynb
* STFT3D-Ventaneo.ipynb
* STFT3D-Ventaneo-DataAugmentation.ipynb
* STFT4D.ipynb
* STFT4D-2C.ipynb
* STFT4D-2C-Resize.ipynb
* STFT4D-Resize.ipynb
* STFT-CNN2D-DA_2.ipynb
* Transfer-Learning.ipynb

* 2C = 2 canales: Los canales son C3 y C4
* V/H = Concatenacion vertical u horizontal
* Resize = resize de la imagen
* Explorar = Impresion de ejemplos
* DataAugmentation = width_shift_range
* Ventaneo = Ventanas de 2 segundos superpuestas al 95%
* x_2 = 2 segundos de señal

### Escalogramas-CWT
* Escalogramas con la transformada continua wavelet, modulo de la wavelet de Morlet compleja (cmor3-3), 128 escalas

* `CWT-CNN.ipynb`
* `CWT-CNN-CV.ipynb`
* `CWT-CNN-GS.ipynb`
* `CWT-CNN-Predecir.ipynb`
* `CWT-CNN-LSTM.ipynb`
* `CWT-CNN-LSTM-CV.ipynb`
* `CWT-CNN-LSTM-GS.ipynb`
* `CWT-CNN-LSTN-Predecir.ipynb`
* `CWT-CNN-Explorar.ipynb`
* CWT3D-CNN2D-2C-V.ipynb
* CWT3D-CNN2D-V.ipynb
* CWT3D-RNNs-2C-V.ipynb
* CWT3D-Ventaneo.ipynb
* CWT3D-Ventaneo-DataAugmentation.ipynb
* CWT4D.ipynb
* CWT4D-2C.ipynb
* CWT-CNN2D-DA_2.ipynb
* Fine-Tuning.ipynb
* Transfer-Learning.ipynb

* 2C = 2 canales: Los canales son C3 y C4
* V = Concatenacion vertical
* Explorar = Impresion de ejemplos
* DataAugmentation = width_shift_range
* Ventaneo = Ventanas de 2 segundos superpuestas al 95%
* x_2 = 2 segundos de señal

### Notas
* Al importar los datos header=None porque no hay encabezado
* Las etiquetas tienen valores de 1 a 4 por lo tanto en Keras se tienen que codificar las etiquetas u otra opción es procesar las etiquetas para que los valores sean del 0 al 3

### Mas información
https://github.com/EdgarMoyete/EEG-Classification-with-CNN