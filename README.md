# 🛡️ Trading Risk Firewall: Análisis Cuantitativo y Motor de Disciplina

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## 📌 Resumen
Este proyecto es un análisis de datos basico diseñado para resolver la principal causa de fracaso en el trading intradía: **la brecha de ejecución psicológica (Overtrading y Revenge Trading).** 

A través del análisis cuantitativo de más de 100 operaciones, se identificó la ventaja matemática del sistema (Edge) y se desarrolló un **Cortafuegos Emocional (Risk Firewall)**: un conjunto de reglas algorítmicas y mecánicas que aíslan la psicología del operador, transformando una curva de capital negativa en una rentable puramente mediante la reducción del ruido y el ahorro en comisiones.

> 🔒 **Nota sobre Privacidad de Datos:** Para proteger la privacidad financiera, el código de este repositorio utiliza un dataset sintético (`dummy_data.csv`) que mantiene las proporciones estadísticas, correlaciones y métricas de riesgo exactas de la cuenta real.

---

## 📊 1. El Problema: Diagnóstico Cuantitativo
El análisis inicial de la base de datos reveló un sistema con una alta tasa de acierto en escenarios específicos, pero severamente drenado por fallas en la gestión emocional:
* **Adicción a rangos laterales:** Operar en Fases sin tendencia drenó el capital con un bajo Win Rate.
* **Sobreoperación por Horario:** Rendimiento negativo crónico fuera de la ventana óptima (después de las 14:00 PM) debido a la fatiga de decisión.
* **Gestión de Stop Loss Subóptima:** El análisis de Excursión Adversa Máxima (MAE) demostró que el 75% de las operaciones ganadoras nunca retrocedían más de 7 ticks. El stop inicial asumía un riesgo innecesario.

---

## 📐 2. La Solución: El Cortafuegos de Riesgo
Basado en los datos empíricos, se diseñó un modelo de gestión de ruina inquebrantable:
1. **Hard Stop Basado en MAE:** Reducción del Stop Loss técnico a un máximo absoluto de 8 ticks.
2. **Time-Out Biológico (15 Minutos):** Tras una operación perdedora, bloqueo estricto de la plataforma para desactivar el FOMO.
3. **El "Kill-Switch" Diario:** Límite absoluto de **2 pérdidas consecutivas** o **3 totales** en el día.
4. **Filtro de Especialización:** Ejecución restringida exclusivamente a configuraciones de alta probabilidad (Trades Tipo 1 y Tipo 2) en el bloque horario óptimo (10:00 a 14:00).

---

## 💵 3. El Impacto Real (Resultados de la Simulación)
Al simular el historial de operaciones a través de las reglas del motor de riesgo, los resultados proyectan un cambio radical:

| Métrica | Operativa Original (Emocional) | Operativa con Cortafuegos (Filtrada) |
| :--- | :--- | :--- |
| **Total de Trades** | 101 operaciones | 43 operaciones (-57% de ruido) |
| **PnL Neto** | -$108.15 | **+$55.80 (Rentable)** |
| **Gasto en Comisiones**| $191.90 | **$81.70 (+$110.20 Ahorrados)** |

**Conclusión:** La rentabilidad del sistema estaba oculta bajo $110 dólares en gastos de comisiones por operaciones impulsivas.

---

## ⚙️ 4. Tecnologías y Dependencias
El análisis y motor de riesgo fueron construidos íntegramente en Python. Para ejecutar este proyecto, se requieren las siguientes librerías estándar de ciencia de datos:
* `pandas` (Procesamiento y limpieza de datos)
* `numpy` (Cálculo numérico)
* `matplotlib` & `seaborn` (Visualización de datos)
* `jupyter` / `notebook` (Entorno de desarrollo interactivo)

---

## 🚀 5. Guía de Uso: Cómo explorar este proyecto

Tienes dos formas de interactuar con este análisis:

1. **Lectura Rápida (Recomendado):** Simplemente haz clic en el archivo `Portfolio_Project_Risk_Engine.ipynb` en la lista de archivos de arriba. GitHub lo renderizará como un documento estático donde podrás leer la metodología y ver los gráficos generados sin necesidad de instalar nada.
2. **Ejecución Interactiva:** Si deseas probar el código tú mismo:
   * Clona este repositorio en tu máquina local.
   * Instala las dependencias mencionadas utilizando `pip install pandas numpy matplotlib seaborn jupyter`.
   * Ejecuta `jupyter notebook` en tu terminal para abrir el entorno.
   * Corre las celdas secuencialmente; el código se alimentará de los datos ubicados en la carpeta `data/dummy_data.csv`.

---

### *Autor* : 
Jesus Martinez [JMGhostCode](https://github.com/JMGhostCode)
*Analista de Datos*