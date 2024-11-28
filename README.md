# Modificación del Modelo LeNet para MNIST  
**Autor**: Vivian Daniela Sánchez Montaña  

## Resumen de las Observaciones  
El modelo LeNet modificado, a pesar de las mejoras realizadas, alcanza una precisión del **90%** en el conjunto de datos MNIST.  

### Conclusiones  
- **Filtros insuficientes**:  
  Aunque se aumentaron los filtros a 32 y 64, esto podría no ser suficiente para aprender patrones que mejoren la precisión. Incrementar el número de filtros y capas podría mejorar el rendimiento.  
- **Posible sobreajuste**:  
  - A pesar de implementar **Dropout** y **Batch Normalization**, el modelo podría estar sufriendo de sobreajuste.  
  - Esto indica que el conjunto de entrenamiento entiende bien los datos recibidos, pero no generaliza de manera óptima.  

---

## Cambios Realizados  
1. **Número de épocas**:  
   - Aumentado de **5** a **20** para dar más tiempo al modelo para aprender.  
2. **Optimización**:  
   - Cambio del optimizador de **SGD** a **Adam**, que mejora la convergencia.  
3. **Regularización**:  
   - Introducción de **Dropout** en capas densas con una tasa del 50% para reducir el sobreajuste.  

---

## Resumen de Diferencias con el Código Original  
1. **Activación**:  
   - Sustitución de **tanh** por **ReLU** en las capas convolucionales.  
2. **Batch Normalization**:  
   - Adición para estabilizar el entrenamiento.  
3. **Dropout**:  
   - Implementado con una tasa del 50% para evitar sobreajuste.  
4. **Optimizador**:  
   - Cambio de **SGD** a **Adam**.  
5. **Épocas**:  
   - Aumentadas de **5** a **20**.  
6. **Visualización**:  
   - Mejora en la visualización de precisión y pérdida durante el entrenamiento.  
7. **Carga y partición de datos**:  
   - Ajustes para asegurar que los datos se procesen correctamente.  

---

## Ejecución del Código  
1. **Pre-requisitos**:  
   - Python 3.x  
   - Bibliotecas necesarias: `TensorFlow`, `Keras`, `numpy`, `matplotlib`.  

2. **Entrenamiento del modelo**:  
   ```bash
   python train_lenet.py
