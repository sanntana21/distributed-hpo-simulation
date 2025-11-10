# Evolutionary Hyperparameter Optimization in Big Data Simulation

## Descripción General

Poyecto diseñado para simular el ajuste de hiperparámetros en un entorno **Big Data distribuido**.  
Aunque el entorno se ejecuta en un único notebook, se **emula la arquitectura de un sistema distribuido** con un nodo **Master** y múltiples **Workers**, siguiendo los principios de la computación paralela.

El proyecto implementa un **algoritmo evolutivo**, inspirado en la biología, para optimizar los hiperparámetros de un modelo de Machine Learning mediante operaciones de **selección, mutación y cruzamiento**.

---

## 1. Objetivo

Simular el proceso de **optimización de hiperparámetros** en un entorno distribuido, mostrando cómo se puede paralelizar la evaluación y selección de modelos en un contexto Big Data.

---

## 2. Enfoque y Metodología

### Algoritmo Evolutivo
El método de optimización se basa en un **algoritmo evolutivo**, compuesto por las siguientes etapas:

- **Individuo:** Representa una configuración específica de hiperparámetros.
- **Población:** Conjunto de individuos evaluados en cada generación.
- **Función de fitness:** Basada en el **F1-score**, para medir el rendimiento del modelo.
- **Mutación:** Modificación aleatoria de uno o más hiperparámetros.
- **Cruzamiento:** Combinación de dos individuos para generar descendencia.
- **Selección:** Escoge los individuos con mejor desempeño para la siguiente generación.

---

## 3. Arquitectura Simulada

El sistema se estructura en dos tipos de nodos:

### **Nodo Master**
- Genera la población inicial de hiperparámetros.
- Distribuye la población a los Workers.
- Agrega los resultados locales.
- Ejecuta operaciones de reproducción (crossover y mutación).

### **Nodos Worker**
- Reciben la población desde el Master.
- Evalúan los individuos en un subconjunto del dataset (simulando datos distribuidos).
- Calculan métricas locales (F1-score).
- Devuelven al Master los mejores individuos locales.

El proceso se repite durante un número determinado de generaciones, simulando una **optimización paralela y distribuida**.

---

## 4. Flujo General del Sistema

1. **Inicialización** → El Master genera una población inicial aleatoria.  
2. **Distribución** → Cada Worker recibe la población y un subconjunto del dataset.  
3. **Evaluación Local** → Los Workers calculan el F1-score de cada individuo.  
4. **Agregación Global** → El Master combina los resultados y crea un ranking global.  
5. **Reproducción** → Se aplican operaciones evolutivas para formar la nueva población.  
6. **Iteración** → El ciclo se repite hasta alcanzar el número de generaciones definidas.

---

## 5. Resultados Esperados

- Mejora progresiva del F1-score global a lo largo de las generaciones.
- Comparación de desempeño entre individuos y generaciones.
- Representación gráfica del proceso evolutivo.

---

## Autores

 - Álvaro Santana Sánchez
