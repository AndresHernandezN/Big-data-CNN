# Big-data-CNN


# MNIST Accuracy Challenge

## Descripción

Este proyecto implementa y mejora un modelo LeNet para clasificar dígitos en el conjunto de datos MNIST. La precisión inicial del modelo se limitaba al 90%. Se aplicaron mejoras progresivas para superar este límite y documentar los resultados.

---

## Mejoras Implementadas

1. **Cambio de la función de activación**:
   - Se cambió `tanh` por `ReLU` en las capas convolucionales y densas.
2. **Optimizador Adam**:
   - Se utilizó `adam` en lugar de `sgd` para acelerar la convergencia.
3. **Aumento de épocas**:
   - Se entrenó el modelo por 20 épocas para mejorar la precisión.
4. **Data Augmentation**:
   - Se implementó rotación, escalado y desplazamiento para enriquecer el conjunto de datos.
5. **Arquitectura más profunda**:
   - Se añadieron más capas convolucionales con mayor número de filtros.

---

## Resultados

### **Precisión Inicial**
- Modelo LeNet original: **90% precisión**

### **Resultados Mejorados**
- **Activación ReLU**: Incremento del 2-3% en precisión.
- **Optimizador Adam**: Reducción del tiempo de convergencia.
- **Más épocas**: Precisión final del modelo: **~97%**.

---

## Cómo Usar

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/mnist-accuracy-challenge.git
   cd mnist-accuracy-challenge
