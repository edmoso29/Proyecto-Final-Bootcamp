# Proyecto-Final-Bootcamp

•	Objetivo general: Identificar a los operadores ineficaces de la empresa de telefonía virtual CallMeMaybe

•	Librerías habituales detectadas/esperadas: pandas, numpy, matplotlib/seaborn, scipy.stats, statsmodels (proportions_ztest), sklearn (preprocesado, modelos, métricas).

•	Carga y tipos:
o	Lectura de uno o varios ficheros (CSV/TSV). Conversión de timestamps a datetime y casting de IDs a str. Renombrado de columnas para homogeneidad.

•	Preprocesamiento:
o	Filtrado por fecha/condiciones de negocio (fecha de corte).
o	Limpieza básica: eliminación de duplicados y tratamiento de nulos (dropna / fillna según caso).
o	Feature engineering: event_date, event_hour, flags binarias, agregados por usuario (eventos únicos, sesiones, lifetime).
o	Uso de .groupby() / pivot_table para agregados por usuario/evento/variant.

•	Análisis exploratorio (EDA):
o	Conteos totales de eventos y usuarios únicos; eventos por usuario.
o	Distribuciones temporales (día/hora), histogramas y barplots; identificación de eventos clave.
o	Construcción de embudo: usuarios por etapa y tasas de conversión entre pasos.

•	Experimentación / pruebas:
o	Agrupación por variante/exp_id y conteo de usuarios por grupo.
o	Tests de proporciones (z-test / proportions_ztest) para comparar conversiones entre grupos (A/A o A/B), p-values calculados y decisiones con alpha (habitualmente 0.05).
o	Tablas resumen con p-values por evento; posible combinación de controles (concatenar grupos) para comparaciones.

•	Salidas y visualizaciones:
o	Tablas resumen (usuarios por evento, conversion rates), gráficos del embudo, series temporales y comparaciones por variante.

•	Conclusiones operativas y recomendaciones finales.
