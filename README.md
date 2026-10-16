# 🛡️ Trading Risk Firewall: Análisis Cuantitativo y Motor de Disciplina

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/Status-Completado-success.svg)]()

## 📌 Resumen Ejecutivo
Este proyecto es un análisis de datos basico diseñado para resolver la principal causa de fracaso en el trading intradía: **la brecha de ejecución psicológica (Overtrading y Revenge Trading).** 

A través del análisis de más de 100 operaciones algorítmicas/discrecionales, se identificó la ventaja matemática del sistema (Edge) y se desarrolló un **Cortafuegos Emocional (Risk Firewall)**: un conjunto de reglas algorítmicas y mecánicas que aíslan la psicología del operador, transformando una curva de capital negativa en una rentable puramente mediante la reducción del ruido y el ahorro en comisiones.

> 🔒 **Nota sobre Privacidad de Datos:** El código de este repositorio utiliza un dataset sintético (`dummy_data.csv`) que mantiene las proporciones estadísticas, correlaciones y métricas de riesgo idénticas a una cuenta real.

## 📊 1. El Problema: Diagnóstico Cuantitativo
El análisis inicial de un backtsting reveló un sistema con una alta tasa de acierto en escenarios específicos, pero severamente drenado por fallas en la gestión emocional:

* **Adicción a la "Fase 3" (Rangos laterales):** El 41% de las operaciones se realizaron en mercados sin tendencia, resultando en un Win Rate del 23% y drenando el capital.
* **Sobreoperación por Horario:** Rendimiento negativo crónico fuera de la ventana óptima (después de las 14:00 PM) debido a la fatiga de decisión (Decision Fatigue).
* **Gestión de Stop Loss Subóptima:** El análisis de Excursión Adversa Máxima (MAE) demostró que el 75% de las operaciones ganadoras nunca retrocedían más de 7 ticks. El stop inicial de 10-12 ticks asumía un riesgo innecesario.

---

## 📐 2. La Solución: El Cortafuegos de Riesgo (Risk Firewall)
Basado en los datos empíricos, se diseñó un modelo de gestión de ruina inquebrantable para blindar la cuenta de rachas emocionales:

1. **Hard Stop Basado en MAE:** Reducción del Stop Loss técnico a un máximo absoluto de 8 ticks.
2. **Time-Out Biológico (15 Minutos):** Tras una operación perdedora, bloqueo estricto de la plataforma durante 15 minutos para desactivar la respuesta amigdalina (FOMO).
3. **El "Kill-Switch" Diario:** Límite absoluto de **2 pérdidas consecutivas** o **3 pérdidas totales** en el día. Al tocar este límite, la operativa se suspende hasta la siguiente sesión.
4. **Filtro de Especialización:** Ejecución restringida exclusivamente a configuraciones de alta probabilidad (A1 en Corto, A2 en Largo) durante Fases tendenciales (1 y 4) en el bloque horario de 10:00 a 14:00.

---

## 💵 3. El Impacto Real (Resultados de la Simulación)
Al cruzar el historial de operaciones real a través de las reglas del motor de riesgo (simulando los cortes automáticos y filtros), los resultados proyectan un cambio radical en la rentabilidad:

| Métrica | Operativa Original (Emocional) | Operativa con Cortafuegos (Filtrada) | Diferencia |
| :--- | :--- | :--- | :--- |
| **Total de Trades** | 101 operaciones | 43 operaciones | -57% (Menos ruido) |
| **PnL Neto** | -$108.15 | **+$55.80** | **Rentable** |
| **Gasto en Comisiones**| $191.90 | $81.70 | **+$110.20 Ahorrados** |

**Conclusión:** La rentabilidad del sistema estaba oculta bajo $110 dólares en gastos de comisiones por operaciones impulsivas. El cortafuegos no cambia la estrategia de entrada, simplemente elimina el comportamiento destructivo.

---

## 📂 4. Estructura del Repositorio

```text
trading-risk-firewall/
│
├── data/
│   └── dummy_data.csv               # Dataset anónimo con proporciones estadísticas reales
│
├── README.md                        # Resumen ejecutivo del proyecto
└── Portfolio_Project_Risk_Engine.ipynb # Notebook interactivo con el análisis, gráficos MAE/MFE y simulación