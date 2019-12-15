# Deep-Learning-BCI-IV-2a
Clasificacion de Imagenes Motoras en senales EEG con Deep Learning y Machine Learning

Los modelos utilizados son:
CNN-2D
CNN-1D
LSTM
GRU
CNN-1D-LSTM
CNN-1D-GRU
ConvLSTM2D
MLP
SVM
Random Forest

Data Set: BCI Competition IV-2a

### RAW
Datos crudos, 22 canales con 1000 valores (4seg a 250Hz), filtrado con pasa banda (8Hz-30Hz)
Input Shape: 288x22000

### RWE-DWT
RWE con db4 y 2 niveles de descomposicion, 22 canales con 3 valores
Input Shape: 288x66

### AlfaC3C4
Alfa (8Hz-13.5Hz), 2 canales (C3 y C4) con 255 valoress
Input Shape: 288x510

### DWT-Coef
Coeficientes de aproximacion y detalle concatenados de DWT-db4 de 2 niveles de descomposicion, 22 canales con 1013 valores
Input Shape: 288x22286

### Notas
Al importar los datos header=None porque no hay encabezado

Las etiquetas tienen valores de 1 a 4 por lo tanto en Keras se tienen que codificar las etiquetas

Los datos estan escalados para que tengan media = 0 y desviacion estandar = 1 (ReLU), excepto para LSTM y GRU los cuales estan en el rango [-1, 1] (tanh)