Vivian Daniela Sánchez Montaña
Resumen de las Observaciones:
El modelo LeNet modificado, a pesar de las mejoras realizadas, sigue alcanzando una precisión de alrededor del 90% en el conjunto de datos MNIST. Las conclusiones que se pudieron inferir durante el ejercicio de configuración del modelo son:
•	Ae aumentaron los filtros a 32 y 64, lo que podría llegar a no ser suficiente para aprender los patrones que nos podrían funcionar para mejorar el accuracy. Adicionalmente, aunque aumenté las épocas de entrenamiento, continuó en 0.9, un número más alto de filtros y capas podría funcionar para mejorar el rendimiento.

•	A partir de la documentación, podría ser que el modelo este sufriendo de sobreajuste, incluso cuando se utilizó Dropout y Batch Normalization. Lo anterior nos indica que posiblemente el conjunto de entrenamiento está entendiendo bien los datos recibidos, pero no está generalizando como se busca.
Cambios realizados:
•	Se aumentó el número de épocas de entrenamiento de 5 a 20 para dar más tiempo al modelo para aprender.

•	A partir de la documentación se recomedaba reemplazar el optimizador SGD por Adam, que es un optimizador adaptativo que generalmente mejora la convergencia.


•	Se introdujo Dropout para la regularización, en las capas densas con una tasa del 50% para reducir el sobreajuste.

El resumen de las diferencias realizadas al código original (tras varias modificaciones previas, pero se optó por mostrar la más completa) son:
Resumen de Diferencias:
•	Activación tanh a ReLU en las capas convolucionales.
•	Adición de Batch Normalization para estabilizar el entrenamiento.
•	Implementación de Dropout con una tasa del 50% para evitar sobreajuste.
•	Cambio del optimizador de SGD a Adam, que mejora la convergencia.
•	Aumento de las épocas de 5 a 20 para dar más tiempo de aprendizaje.
•	Mejora en la visualización de la precisión y pérdida durante el entrenamiento.
•	Ajustes en la carga y partición de los datos para asegurarse de que el modelo reciba los datos de manera correcta.