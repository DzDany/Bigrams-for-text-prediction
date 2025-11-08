# Modelo de Bigramas para Predicción de Texto en Python

## Descripción general

Este proyecto implementa un **modelo de lenguaje basado en bigramas** utilizando Python y la librería **NLTK**.  
El objetivo es limpiar texto (eliminando acentos, puntuación y mayúsculas), tokenizarlo, calcular frecuencias y probabilidades de aparición de palabras consecutivas (bigramas), y finalmente **predecir o generar texto** de manera simple a partir de esas relaciones.

---

## ⚙️ Funcionalidades principales

1. **Limpieza del texto (`clean_text`)**
   - Convierte el texto a minúsculas.  
   - Elimina tildes y acentos manteniendo la letra `ñ`.  
   - Devuelve una versión "limpia" del texto lista para tokenización.

2. **Tokenización**
   - Usa `word_tokenize` (de NLTK) para dividir el texto en palabras individuales.  
   - Aplica una expresión regular para quedarse solo con palabras válidas (letras y `ñ`).

3. **Frecuencias**
   - Calcula la frecuencia de cada palabra usando `FreqDist`.  
   - Genera bigramas (pares de palabras consecutivas) y obtiene su frecuencia.

4. **Probabilidades**
   - Calcula la probabilidad de cada bigrama como:

     $$
     P(w_2 \mid w_1) = \frac{\text{freq}(w_1, w_2)}{\text{freq}(w_1)}
     $$


5. **Predicción de la siguiente palabra (`predict_next_word`)**
   - Dada una palabra, devuelve las 3 palabras más probables que la sigan según las frecuencias de bigramas.

6. **Generación de texto (`generate_text`)**
   - A partir de una palabra inicial, genera texto nuevo seleccionando palabras sucesivas basadas en las probabilidades de bigramas.

---

## Librerías utilizadas

NLTK → para tokenización, bigramas y frecuencia de palabras.

heapq → para obtener los bigramas más probables.

unicodedata → para normalización y eliminación de acentos.

re → para filtrado con expresiones regulares.

random → para generar texto de forma pseudoaleatoria.
