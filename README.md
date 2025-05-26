# Time-Series-Imacec

## 📈 Forecast de IMACEC con XGBoost y Prophet

Este proyecto realiza una proyección mensual del IMACEC (Índice Mensual de Actividad Económica de Chile) utilizando dos metodologías de modelamiento:
	•	Gradient Boosting (XGBoost)
	•	Modelado aditivo no lineal (Prophet)

El objetivo es generar estimaciones de corto plazo (3 meses) que permitan anticipar el comportamiento de la economía chilena.

## 🔎 ¿Qué es el IMACEC?

El IMACEC es un indicador que estima la evolución mensual del Producto Interno Bruto (PIB) en Chile. Es publicado por el Banco Central de Chile y representa aproximadamente un 90% del PIB. Se utiliza como un termómetro de la economía, permitiendo tomar decisiones informadas.
https://www.bcentral.cl/areas/estadisticas/imacec

##💡 Metodologías implementadas

### 1. Gradient Boosting (XGBoost)

Modelo supervisado de tipo tree boosting, muy eficaz para problemas estructurados. En este proyecto:
	•	Se transforma la serie de tiempo en un problema supervisado usando features de rezago (lag_1, lag_2, …, lag_12).
	•	Se entrena el modelo para predecir el valor del mes siguiente.
	•	Se aplica recursivamente para obtener los próximos 3 meses.

Ventajas:
	•	Captura relaciones no lineales y patrones complejos.
	•	Altamente eficiente y rápido para producción.

### 2. Prophet (Meta/Facebook)

Modelo de descomposición aditiva desarrollado por Facebook:
	•	Ajusta componentes de tendencia, estacionalidad y festividades (aunque en este caso no se utilizan días especiales).
	•	No requiere ingeniería de features.
	•	Muy útil para datos con patrones temporales y estacionales fuertes.

Ventajas:
	•	Fácil de interpretar.
	•	Automático y robusto para series temporales económicas.

## 🏗️ Estructura del código
	•	TimeSeries_GradientBoosting: Entrena modelo con lag features y genera proyecciones.
	•	TimeSeries_Prophet: Ajusta modelo Prophet y predice los siguientes 3 meses.
	•	Los Datos históricos del IMACEC mensual desde 2018 a la fecha, ingresados directamente en el notebook.

 ## 📊 Salida esperada

El código genera gráficos con:
	•	La serie original.
	•	La proyección de los próximos 3 meses usando cada modelo.
	•	Valores proyectados impresos en consola.
