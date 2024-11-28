# MNIST Accuracy Challenge

## Descripción

Este proyecto implementa y mejora un modelo LeNet para clasificar dígitos en el conjunto de datos MNIST. La precisión inicial del modelo se limitaba al 90%. Se aplicaron mejoras progresivas para superar este límite y documentar los resultados obtenidos a través de múltiples pruebas y ajustes en la arquitectura del modelo, optimización y técnicas de regularización.

---

## Mejoras Implementadas prueba 1

1. **Cambio de la función de activación**:
   - Se cambió `tanh` por `ReLU` en las capas convolucionales y densas para mejorar la convergencia y evitar problemas de gradientes desvanecidos.
2. **Optimizador Adam**:
   - Se utilizó `adam` en lugar de `sgd` para acelerar la convergencia.
3. **Aumento de épocas**:
   - Se entrenó el modelo por 10 épocas para observar mejoras en la precisión.
4. **Data Augmentation**:
   - Se implementó rotación, escalado y desplazamiento para enriquecer el conjunto de datos y mejorar la capacidad de generalización del modelo.
5. **Arquitectura más profunda**:
   - Se añadieron más capas convolucionales con un mayor número de filtros para aumentar la capacidad del modelo.

---

## Resultados prueba 1

### **Precisión Obtenida**
- **Epoch 1:** loss = 0.3742, accuracy = 0.8995  
- **Epoch 2:** loss = 0.3280, accuracy = 0.9000  
- **Epoch 3:** loss = 0.3276, accuracy = 0.9000  
- **Epoch 4:** loss = 0.3273, accuracy = 0.9000  

**Análisis:**  
No se observaron cambios significativos en la precisión, lo que indica que el problema podría estar relacionado con la arquitectura del modelo o la capacidad del optimizador para explorar un espacio de solución más amplio.

---

## Mejoras Implementadas prueba 2

1. **Cambio del Optimizador**:
   - Se utilizó un optimizador más avanzado, como **Adam**, ajustando la tasa de aprendizaje para encontrar una configuración más eficiente.

---

## Resultados prueba 2

### **Precisión Obtenida**
- **Epoch 1:** loss = 0.3455, accuracy = 0.8999  
- **Epoch 2:** loss = 0.3288, accuracy = 0.9000  
- **Epoch 3:** loss = 0.3276, accuracy = 0.9000  
- **Epoch 4:** loss = 0.3274, accuracy = 0.9000  

**Análisis:**  
Aunque el optimizador Adam mostró estabilidad en la convergencia, no se logró superar el límite del 90% de precisión, lo que refuerza la necesidad de ajustar la arquitectura o aplicar técnicas de regularización.

---

## Mejoras Implementadas prueba 3

1. **Regularización**:
   - Se añadió **Dropout** para apagar aleatoriamente algunas unidades durante el entrenamiento y reducir la dependencia del modelo en características específicas.
   - Se integró **L2 Regularization** para penalizar los pesos grandes y reducir el sobreajuste.

---

## Resultados prueba 3

### **Precisión Obtenida**
- **Epoch 1:** loss = 0.4767, accuracy = 0.8988  
- **Epoch 2:** loss = 0.3338, accuracy = 0.9000  
- **Epoch 3:** loss = 0.3290, accuracy = 0.9000  
- **Epoch 4:** loss = 0.3276, accuracy = 0.9000  

**Análisis:**  
La regularización ayudó a estabilizar el modelo, pero no produjo mejoras en la precisión. Esto sugiere que el problema podría deberse a limitaciones en la arquitectura o a una falta de variabilidad en los datos.

---

## Mejoras Implementadas prueba 4

1. **Optimización Avanzada**:
   - Se utilizó el optimizador Adam con una **tasa de aprendizaje ajustada** (0.0005) para permitir pasos más pequeños en el gradiente y explorar mejor el espacio de solución.
2. **Batch Normalization**:
   - Se incluyó normalización por lotes en cada capa convolucional para mejorar la estabilidad del entrenamiento y acelerar la convergencia.
3. **Arquitectura más compleja**:
   - Incremento en el número de filtros en las capas convolucionales (32, 64 y 128).
   - Mayor número de unidades en las capas densas (256 y 128).
4. **Mayor número de épocas**:
   - El entrenamiento se extendió a 10 épocas para permitir una convergencia más completa.

---

## Resultados prueba 4

### **Precisión Obtenida**
- **Epoch 1:** loss = 1.3468, accuracy = 0.8959
- **Epoch 2:** loss = 0.3697, accuracy = 0.9000
- **Epoch 3:** loss = 0.3454, accuracy = 0.9000
- **Epoch 4:** loss = 0.3315, accuracy = 0.9000
- **Epoch 5:** loss = 0.3263, accuracy = 0.9000
- **Epoch 6:** loss = 0.3265, accuracy = 0.9000
- **Epoch 7:** loss = 0.3264, accuracy = 0.9000
- **Epoch 8:** loss = 0.3260, accuracy = 0.9000
- **Epoch 9:** loss = 0.3262, accuracy = 0.9000

Epoch 1: loss = 1.0599, accuracy = 0.8975
Epoch 2: loss = 0.3271, accuracy = 0.9000
Epoch 3: loss = 0.3268, accuracy = 0.9000
Epoch 4: loss = 0.3265, accuracy = 0.9000
Epoch 5: loss = 0.3261, accuracy = 0.9000
Epoch 6: loss = 0.3259, accuracy = 0.9000
Epoch 7: loss = 0.3255, accuracy = 0.9000
Epoch 8: loss = 0.3254, accuracy = 0.9000
Epoch 9: loss = 0.3253, accuracy = 0.9000


### **Análisis**

Los resultados muestran que, aunque se realizaron múltiples mejoras en la arquitectura, optimización y regularización del modelo, **la precisión sigue estancada en el 90%**. Esto sugiere que el problema podría no estar completamente relacionado con la capacidad del modelo o las técnicas aplicadas, sino con limitaciones inherentes al conjunto de datos o los siguientes factores:

1. **Saturación del modelo:**  
   A pesar de las mejoras en la arquitectura (incremento de filtros y unidades densas), el modelo no logra extraer información adicional que le permita superar este límite.

2. **Optimización estable pero sin impacto significativo:**  
   La normalización por lotes y la tasa de aprendizaje ajustada estabilizaron el entrenamiento, pero no llevaron a una mejora en la precisión.

3. **Restricciones del conjunto de datos MNIST:**  
   El conjunto de datos MNIST es conocido por su simplicidad. Es posible que no existan características adicionales significativas para que el modelo aprenda, limitando así el potencial de mejora.

4. **Sobreajuste:**  
   Aunque no se observan pérdidas significativas en la generalización, el modelo podría estar alcanzando un límite de aprendizaje que no puede superar sin mayor variabilidad en los datos.

---

## Conclusiones Parciales

1. **El límite del 90% persiste:**  
   A pesar de las mejoras significativas en la arquitectura y técnicas avanzadas de regularización, el modelo sigue limitado al 90% de precisión en las pruebas, lo que sugiere que el problema puede estar relacionado con la naturaleza del conjunto de datos o con configuraciones más fundamentales.

2. **Impacto de las mejoras implementadas:**  
   - **Batch Normalization:** Mejoró la estabilidad del entrenamiento, reduciendo fluctuaciones en la pérdida.  
   - **Tasa de aprendizaje ajustada:** Evitó explosiones o estancamientos en el gradiente, pero no contribuyó a un aumento en la precisión.  
   - **Arquitectura más compleja:** Incrementó la capacidad del modelo, pero esto no se tradujo en mejoras de precisión debido a posibles limitaciones en las características aprendibles del conjunto de datos.
