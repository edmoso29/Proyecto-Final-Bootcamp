# ☎️ **Análisis operativo de la empresa de telefonía virtual** ☎️
**CallMeMaybe** Es una empresa que brinda servicio de telefonía virtual, sus clientes son organizaciones que necesitan distribuir gran cantidad de llamadas entrantes entre varios operadores o realizar llamadas salientes a través de sus operadores. Asimismo, los operadores también pueden realizar llamadas internas para comunicarse entre ellos, estas llamadas se realizan a través de la red de CallMeMaybe.

*"Lo que no se define no se puede medir. Lo que no se mide, no se puede mejorar"*

Para toda empresa o negocio siempre se recomienda la identificación y medición el desempeño de los colaboradores (en este caso, operadores). Para CallMeMaybe, la medición del desempeño pudiera arrojar como salientes los siguientes aspectos:
- Desempeño como tal de los operadores (incluso un historial si la medición se realiza de manera contínua)
- Posible relación entre el desempeño operacional y los ingresos de la empresa
- Identificación de oportunidades de mejora tanto para el personal como para la operación misma
- Observar falta de recursos (humano, infraestructura, software/hardware, entre otros)
- Situaciónes en las que el desempeño aumente o disminuya

Considerando el modelo de negocio de CallMeMaybe (servicio de telefonía), podemos identificar los siguientes aspectos para identificar a un operador poco eficaz:
1. Alta cantidad de **llamadas entrantes perdidas** (internas y externas)
2. **Tiempo de espera** prolongado para las llamadas entrantes
3. Número bajo de **llamadas salientes** por parte del operador

### **Objetivo principal** 🎯
- Desarrollar indicadores KPI para identificar a los operadores eficaces e ineficaces de la empresa

### **Datos y librerías** 📚
- Utilicé librerías pandas, numpy, matplotlib, seaborn, math, stats desde scipy, scipy.stats y statsmodel.stats.proportion
- Trabajé con dos conjuntos de datos extraídos desde archivos CSV:
  - El primer dataset con los datos de operación, identifica a los operadores, indica la información para las llamadas (duración, entrantes o salientes, respondidas o perdidas).
  - El segundo dataset con datos de tarifa y fecha de registro de los clientes.

### **Preprocesamiento de Datos** 🔎🕵️
- Cambié formatos de columna con .astype y pd.to_numeric
- Procesé los valores ausentes y duplicados
- Cree una nueva columna "waiting_time" para saber el tiempo de espera de las llamadas entrantes.

### **Análisis Exploratorio de Datos** 📊📈
-	Conté el número de llamadas recibidas y perdidas por operador
-	De igual modo y por operador, calculé el promedio del tiempo de espera y el promedio de la duración de llamada sin incluír (sin incluír el tiempo de espera).
-	Calculé 3 KPI's como métricas de ineficiencia
  -	Tasa de llamadas perdidas entrantes
  -	Tiempo promedio de espera
  -	Tasa de llamadas salientes

### **Pruebas de Hipótesis** 🧮🖥️

Antes de realizar pruebas de hipótesis, primero clasifiqué a los operadores en *eficaces* e *ineficaces*
- Eficaces: Operador con una tasa de llamadas perdidas y un tiempo de espera promedio en o por debajo de la mediana del equipo (percentil 50); ***Se identifican 418 operadores eficaces de 1092***.
- Ineficaces: Operador con una tasa de llamadas perdidas o un tiempo de espera promedio por encima de la mediana del equipo (percentil 50). ***Se identifican 674 operadores ineficaces de 1092***.
Verifiqué que la distribución de datos no era normal y las varianzas de los grupos no eran homogéneas, por lo tanto realicé 3 pruebas de hipótesis por Mann-Whitney:
- Prueba para la Tasa de Llamadas Perdidas: Sí funciona como KPI ✅
- Prueba para el Tiempo de Espera: Sí funciona como KPI ✅
- Prueba para la Proporción de Llamadas Salientes: No funciona como KPI ❌

### **Conclusiones** 📝💡
1. La tasa de llamadas perdidas y el tiempo promedio de espera pueden ser métricas adecuadas para determinar si un operador es eficiente o ineficiente.
2. No se recomienda utilizar la cantidad de llamadas salientes como métrica para determinar si un operador es eficiente o ineficiente.
3. Con base a este análisis, la empresa CallMeMaybe tiene una cantidad de 418 operadores (38.28%) de operadores eficientes y una cantidad de 674 (61.72%) de operadores ineficientes.
