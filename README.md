# 📉 Event-Driven-Risk-Engine-Multi-Portfolio-Backtesting-Stress-Testing

Este repositorio presenta un marco cuantitativo especializado diseñado para evaluar la resiliencia de carteras durante eventos de estrés histórico (por ejemplo, shocks pandémicos, conflictos geopolíticos). El motor automatiza la validación de modelos de riesgo mediante backtesting sistemático y visualiza la evolución del riesgo de cola (tail risk) en carteras regionales y sectoriales.

🎯 **Objetivo:** Cuantificar el impacto de eventos de riesgo de cola en carteras diversificadas y validar la precisión de los modelos de Valor en Riesgo (VaR) y VaR Condicional (CVaR).

---

## 📖 Resumen Extendido
El sistema analiza múltiples carteras temáticas (Perú, Sudamérica, Norteamérica y Global) durante ventanas específicas de alta volatilidad. Utiliza una **"ventana de retrospectiva" (look-back) de 252 días hábiles** para calibrar los umbrales de riesgo y una **"ventana de estrés" de 40 días** para monitorear las brechas del modelo (violaciones), proporcionando una auditoría estadística rigurosa de la protección contra riesgos a la baja.

### 🎯 Objetivos clave del análisis
* **Pruebas de Estrés Específicas por Evento:** Aislamiento de fechas históricas clave para analizar el comportamiento de los activos durante dislocaciones del mercado (p. ej., marzo de 2020, octubre de 2023).
* **Backtesting de Riesgo Dinámico:** Implementación de VaR Móvil (95%) para rastrear la frecuencia y magnitud de las violaciones, identificando una posible subestimación del modelo.
* **Cuantificación del Riesgo de Cola (CVaR):** Evaluación del Déficit Esperado (VaR Condicional) para medir la pérdida promedio en el 5% de los peores casos, ofreciendo una visión más profunda que el VaR estándar.
* **Comparación de Carteras Regionales:** Análisis comparativo de métricas de riesgo entre carteras especializadas, como P_Peru (BVN, SCCO) frente a P_Norteamerica (FCX, HL, etc.).

---

## 🔍 Carteras y Activos Analizados
El motor procesa un universo diverso de acciones mineras e industriales en diferentes jurisdicciones:

* **🇵🇪 Perú:** BVN (Buenaventura), SCCO (Southern Copper).
* **🌎 Sudamérica:** FM.TO, HBM, SCCO, GMEXICOB.MX.
* **🇺🇸 Norteamérica:** FCX (Freeport-McMoRan), HL (Hecla Mining), HBM, FM.TO.
* **🌐 Grupal:** BHP, GLEN.L, FCX, FM.TO, RIO.

---

## 📊 Resultados Clave de la Cartera y Riesgo
* **Sensibilidad al Riesgo de Cola:** Identificación de niveles elevados de CVaR durante "Ventanas de Eventos" específicas, permitiendo clasificar las carteras por sus capacidades defensivas.
* **Integridad del Modelo:** A través del gráfico de Backtesting, el sistema identifica grupos de violaciones de VaR, señalando períodos donde la volatilidad del mercado excedió las expectativas estadísticas (p. ej., shocks a principios de 2020).
* **Beneficio de la Diversificación:** Análisis de la "P_Grupal" frente a carteras regionales para cuantificar la reducción del riesgo idiosincrásico a través de la asignación global de activos.

---

## 🛠️ Estructura y Lógica del Código

### 1. Capa de Procesamiento de Datos
* Recuperación automatizada de tickers globales a través de **yfinance** con manejo de fechas adaptable para diferentes bolsas internacionales.

### 2. Motor de Cálculo de Riesgo
* **Cuantil Móvil:** `rolling().quantile(0.05)` para la estimación dinámica del VaR.
* **VaR Condicional:** Calculado como la media de los rendimientos que exceden el umbral del VaR.

### 3. Módulo de Backtesting
* Identificación de **"Violaciones"** donde los rendimientos reales caen por debajo del VaR previsto, marcados con indicadores especializados en los informes visuales.

### 4. Suite de Visualización
* **Superposición de CVaR:** Gráficos sincronizados de múltiples carteras durante la misma ventana de evento para comparación directa.
* **Gráfico de Dispersión de Backtesting:** Visualización de alto contraste de valores atípicos y fallas del modelo.

---

## 🚀 Tecnologías y Conceptos Utilizados
* **Gestión de Riesgos Cuantitativos:** Backtesting de VaR, VaR Condicional (Déficit Esperado).
* **Pruebas de Estrés:** Análisis basado en eventos, Simulación Histórica.
* **Stack de Python:** Pandas (manipulación de series temporales), NumPy (vectorización estadística), Matplotlib (gráficos de riesgo avanzados).
* **Clases de Activos:** Acciones Mineras Globales, Metales Base y Preciosos (Cobre, Oro, Plata).

---

## 📧 Contacto y Networking
📩 **Abierto a conectar y explorar nuevas oportunidades.** 📩 **carloscaballeromc@gmail.com**
