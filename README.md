# Pig-Analytics-Core
Sistema de Inteligencia de Negocios para la optimización de la producción porcina basado en modelos de crecimiento no lineales y análisis de márgenes operativos.
# 🐖 AgroGompertz-BI: Inteligencia de Datos Porcina

AgroGompertz-BI es un ecosistema de analítica avanzada diseñado para transformar registros operativos de granjas porcinas en decisiones estratégicas de alta rentabilidad. El núcleo del proyecto utiliza el **Modelo de Crecimiento de Gompertz** para predecir el rendimiento biológico y lo integra con una matriz de **Gastos Operativos (OPEX)**.

## 🚀 Propósito del Proyecto
Maximizar el margen de utilidad neta por animal, determinando el punto óptimo de venta frente al costo de alimentación acumulado y los gastos fijos de infraestructura (Renta, Luz, Agua, WiFi).



## 🛠️ Arquitectura de Datos (Metodología de Capas)
El proyecto implementa una arquitectura de procesamiento de datos en tres niveles:
1.  **Capa de Bronce:** Ingesta de datos crudos desde Google Drive (Excel).
2.  **Capa de Plata:** Limpieza, estandarización de fechas y cálculo de KPIs (Mortalidad, DNP, GPD).
3.  **Capa de Oro:** Modelado predictivo de crecimiento y proyecciones de flujo de caja.

## 📈 Características Principales
* **Modelo Gompertz Dinámico:** Ajuste de curvas no lineales para determinar la velocidad de crecimiento ($k$) por lote.
* **Análisis de Margen Real:** Deducción automática de gastos operativos compartidos entre la población total.
* **Ranking de Productividad:** Evaluación de cerdas madre basada en la eficiencia de sus camadas en la etapa de engorda.
* **Optimización de Ventas:** Cálculo del punto de retorno decreciente donde el costo de mantenimiento supera la ganancia de peso diaria.



## 💻 Tecnologías Utilizadas
* **Python 3.x**
* **Pandas:** Manipulación y limpieza de datos.
* **SciPy:** Ajuste de curvas y optimización matemática.
* **Plotly:** Visualizaciones interactivas de rentabilidad.
* **Google Colab / Drive API:** Integración de entorno en la nube.

## 📋 Ejemplo de Uso
```python
# Calibración del modelo con datos de la granja
b, k = calibrar_lote(peso_nacimiento=1.2, peso_venta=115, dias=135)
utilidad = calcular_margen_neto(gpd, gastos_fijos=11150)
