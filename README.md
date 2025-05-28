# 📊 Proyecto de Predicción de Montos de Préstamos Digitales en Perú

---

## 🎯 Objetivo del Trabajo

Desarrollar modelos de aprendizaje automático —una regresión lineal simple y una red neuronal— para predecir el monto promedio de préstamos digitales otorgados a clientes peruanos. El proyecto se construyó utilizando Python, con bibliotecas como Pandas, Scikit-learn y TensorFlow/Keras. GitHub se empleó para el control de versiones y documentación.

---

## 📁 Breve Descripción del Dataset

El dataset fue extraído de Kaggle y contiene información anonimizada de clientes que han solicitado préstamos digitales. Las variables incluyen datos como género, procedencia, número de transacciones digitales y rango de sueldo.

Para este análisis se filtraron solo los registros donde el cliente realmente tuvo un préstamo (`promSaldoPrest3Um > 0`), y se trabajó principalmente con estas variables:

- `rngSueldo`: rango de sueldo mensual del cliente.
- `sueldo_promedio`: valor numérico promedio calculado a partir del rango.
- `genero`: sexo del cliente (codificado como `genero_cod`).
- `procedencia`: ciudad o región del cliente (codificada como `procedencia_cod`).
- `promSaldoPrest3Um`: variable objetivo, el promedio del saldo de préstamo en los últimos tres meses.

---

## 🧰 Librerías Utilizadas

- `pandas` y `numpy`: para manejo y limpieza de datos.
- `matplotlib`: para visualizaciones de entrenamiento y regresión.
- `scikit-learn`: para regresión lineal, escalamiento de datos y métricas.
- `tensorflow.keras`: para construir y entrenar la red neuronal.

---

## 🤖 Explicación de los Modelos

### 1. Regresión Lineal Simple

- Se utilizó `sueldo_promedio` como variable independiente y `promSaldoPrest3Um` como dependiente.
- Se entrenó un modelo de regresión lineal para observar si el nivel de ingreso del cliente tenía relación directa con el monto del préstamo.
- Se graficó la predicción con respecto a los valores reales.

### 2. Red Neuronal Artificial

- Se utilizaron como entrada: `sueldo_promedio`, `genero_cod`, y `procedencia_cod`.
- La arquitectura fue de 3 capas ocultas con 64, 32 y 16 neuronas respectivamente.
- Se utilizó la función de activación ReLU y un optimizador Adam.
- Se entrenó el modelo durante **50 ciclos** para evitar sobreajuste y se validó con el 20% de los datos de entrenamiento.

---

## 📷 Capturas de Gráficas

1. Gráfico de regresión lineal: muestra puntos reales vs. predicción.
2. Evolución del error en la red neuronal durante las 50 épocas.
3. Comparación gráfica entre los valores predichos por la red y los valores reales.

---

## ✅ Conclusiones

- Usar `sueldo_promedio` como variable principal resultó lógico, ya que está muy relacionado con la capacidad crediticia del cliente.
- La regresión lineal mostró la tendencia general, pero fue limitada en precisión.
- La red neuronal capturó mucho mejor las relaciones, incluso con pocas variables y solo 50 ciclos de entrenamiento.
- Trabajar con categorías como `genero` y `procedencia` implicó codificarlas para que el modelo las entienda.
- Filtrar registros con préstamos reales y limpiar los datos mejoró mucho la calidad del entrenamiento.

