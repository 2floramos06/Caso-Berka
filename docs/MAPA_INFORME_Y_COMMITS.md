# Mapa de consignas y división de cuatro integrantes

## Resumen de tareas y commits sugeridos

| Integrante | Notebook | Qué demuestra | Commit sugerido |
|---|---|---|---|
| 1 | `01_integracion_datos.ipynb` | Lectura de ocho orígenes, unión de cinco, 1 fila/cliente, variable Y | `feat: inventario y dataframe base Berka` |
| 2 | `02_analisis_univariado.ipynb` | Diccionario de todas las variables, descripción, tendencia central y dispersión, gráficos | `feat: exploracion univariada completa` |
| 3 | `03_bivariado_perfilado.ipynb` | Cinco variables contra Y, tablas, gráficos, perfilado HTML | `feat: analisis bivariado y perfilado ydata` |
| 4 | `04_preparacion_tabla_minable.ipynb` | >60% nulos, outliers IQR, imputación, z-score, one-hot, CSV validado | `feat: preparacion y tabla minable final` |

**Los nombres son roles sugeridos**: la asignación debe reflejar las contribuciones reales. El informe actual lista cuatro integrantes; agreguen un cuadro `Integrante | Colaboración` y cómo resolvieron desacuerdos reales (no inventados).

## Secuencia Git compatible con trabajo en paralelo
1. Integrante 1 crea `main` con carpetas, `README.md`, `requirements.txt`, `01` y sube la base del notebook; **no subir datos ni resultados generados** al repositorio.
2. Cada miembro trabaja en rama propia, por ejemplo `feat/univariado`, `feat/bivariado`, `feat/preparacion`.
3. Acordar nombres y tipos de columnas de `01_base_clientes.csv` antes de integrar los notebooks 02-04. Los notebooks publicados ya comparten esas columnas.
4. Cada integrante hace su commit solo sobre su `.ipynb`, abre PR y otra persona lo revisa. Evitar editar simultáneamente la misma celda de un `.ipynb`.
5. Integrar ramas y ejecutar **01 → 02 → 03 → 04**. La persona responsable de entrega copia al ZIP final el CSV, el perfilado HTML y el informe con rúbrica completada.

Comandos de ejemplo:
```bash
git checkout -b feat/univariado
git add notebooks/02_analisis_univariado.ipynb
git commit -m "feat: exploracion univariada completa"
git push -u origin feat/univariado
```

## Qué responde cada notebook en el informe
**3.2 Entendimiento de datos**
- `01`: tablas utilizadas, tamaño de **todos** los archivos, claves, limitaciones de integración, Y binaria y razón para usar ML en una fase posterior.
- `02`: clasificación de **todas** las variables unificadas; media, mediana, moda, cuartiles, desviación, varianza y rangos; gráficos y nulos.
- `03`: cinco relaciones con Y; HTML de perfilado y conclusiones descriptivas sobre variables que pueden caracterizar clientes.

**3.3 Preparación de datos**
- `04`: descarte de >60% nulos, outliers por RIC y decisión de conservar/no conservar, imputación, z-score, one-hot encoding; CSV final y verificación del grano.

## Recomendaciones para mejorar el informe original
- Cambiar el título de portada genérico "Práctica" por "Práctica semanal – Caso Banco Berka".
- En 3.2.1 insertar tabla de uniones `client→disp→account` + agregaciones `card` y `trans`, así como la verificación de unicidad.
- En 3.2.2 indicar que **tener tarjeta no equivale a ser buen candidato de crédito**; el modelo es una hipótesis, no un clasificador entrenado.
- En 3.2.3 usar los CSV 02 y 03 más la interpretación del perfilado; responder las preguntas de entendimiento con hechos observados, no solo capturas.
- En 3.3.1 explicar decisiones y métricas del notebook 04. Indicar por qué se conservaron outliers.
- En 4 redactar conclusiones con cifras observadas al ejecutar; **no afirmar capacidad de pago, causalidad o calidad predictiva**.
- Agregar una tabla de contribución de cuatro integrantes y resolución de controversias real; la consigna del PDF menciona cinco, pero el grupo actual es de cuatro, así que consulten si debe autorizarse.
- No confundir tasas por categoría (porcentaje dentro de cada frecuencia) con porcentajes de todo el dataset.
