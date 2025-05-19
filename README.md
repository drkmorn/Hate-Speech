# Clasificación de Mensajes de Odio en Redes Sociales

Este proyecto tiene como objetivo desarrollar un modelo de aprendizaje automático capaz de identificar mensajes de odio en redes sociales.

##  ¿Qué es un discurso de odio?

Un discurso de odio es cualquier mensaje ofensivo dirigido a una persona o grupo por características inherentes como raza, género, religión, orientación sexual u origen nacional, y que puede poner en riesgo la paz social.

---

##  Propósito del Proyecto

Dado el volumen diario de mensajes en redes sociales, es fundamental identificar y clasificar los discursos de odio para alertar o sancionar comportamientos tóxicos. Nuestro objetivo fue crear un clasificador que distinga entre mensajes de odio y mensajes inofensivos.

---

##  Conjunto de Datos

Se utilizaron múltiples bases de datos públicas extraídas de Kaggle, la mayoría provenientes de la red social “X” (antes Twitter). Se seleccionaron seis categorías principales:

- **Sexismo**: 22,407 mensajes
- **Racismo**: 18,167 mensajes
- **Religión**: 16,088 mensajes
- **Orientación sexual / identidad de género**: 18,031 mensajes
- **Origen / xenofobia**: 11,487 mensajes
- **No odio**: 23,053 mensajes

 Para facilitar la traducción al español, se seleccionaron 10,000 ejemplos por categoría y se tradujeron usando la API de Google Translate.

---

##  Preprocesamiento de Datos

Las etapas de limpieza incluyeron:

- Eliminación de caracteres extraños (como errores de codificación)
- Conversión a minúsculas
- Remoción de acentos, signos de puntuación y números
- Eliminación de menciones `@user` y otros caracteres que no son necesarios al momento de clasificar mensajes de odio
- Detección y eliminación de duplicados
- Tokenización, lematización y stemming
- Vectorización usando **TF-IDF**

---

##  Modelado y Evaluación

Se probaron múltiples algoritmos de clasificación multiclase, optando finalmente por **Random Forest** debido a su capacidad para manejar características comunes entre clases sin sobreajuste significativo.

###  Métricas del Mejor Modelo:

- **Accuracy**: 0.84  
- **Precision**: 0.83  
- **Recall**: 0.84  
- **F1 Score**: 0.83  

Entrenado varios modelos con validación cruzada (5-fold), se obtuvo un desempeño consistente. Los hiperparámetros óptimos se seleccionaron usando `GridSearchCV`.

###  Desempeño por Categoría:

| Categoría     | Precisión |
|---------------|-----------|
| Sexismo       | 0.73      |
| No Odio       | 0.81      |
| Origen        | 0.89      |
| Racismo       | 0.89      |
| Religión      | 0.91      |
| Orientación   | 0.65      |

---

##  Conclusión

El modelo funciona adecuadamente, especialmente en la detección de mensajes **no ofensivos**, lo que es crucial para evitar sanciones erróneas. Se observó menor precisión en categorías como **sexismo** y **orientación**, lo cual podría mejorarse con una mayor cantidad de datos representativos.

---

##  Autores

- Ana Cristina Cuevas García  
- Derek Saúl Morán Pérez  
- Emiliano Vicaña García  

---

##  Archivos Clave

- `Clasificación de Mensajes de Odio.ipynb`: cuaderno Jupyter con el código completo del proyecto.
- `README.md`: este archivo.
- `Bases de Datos/`: Incluye todas las bases de datos trabajadas, desde las iniciales hasta las traducidas y procesadas.
- `Proyecto 2 Clasificación de mensajes en redes sociales.pptx`: Presentación resumida sobre el proyecto.



