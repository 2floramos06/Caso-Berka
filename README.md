# Banco Berka · Práctica semanal · Trabajo de 4 integrantes

## Objetivo
Construir una tabla minable con **1 fila por cliente**, que sirva para estudiar la tenencia histórica de tarjetas, como aproximación a una posible segmentación comercial. **No equivale a predecir aprobación o solvencia**. El modelado supervisado se plantea como aplicación posterior; **no se entrena** ningún modelo en esta entrega.

## Estructura
```
Berka_Equipo/
├── datos/
│   └── Caso Berka.zip                ← Archivo original (incluido en paquete)
├── notebooks/
│   ├── 01_integracion_datos.ipynb
│   ├── 02_analisis_univariado.ipynb
│   ├── 03_bivariado_perfilado.ipynb
│   └── 04_preparacion_tabla_minable.ipynb
├── intermedios/                    ← Resultado notebook 01
├── resultados/                     ← CSV, estadísticos, gráficos y HTML
├── docs/
│   └── MAPA_INFORME_Y_COMMITS.md
├── requirements.txt
└── .gitignore
```

## Cómo ejecutarlo con Miniconda 3 (Windows o Linux)
1. Extraer **completa** la carpeta `Berka_Equipo`, incluida `datos/Caso Berka.zip`. No descomprimir el ZIP del dataset.
2. Abrir **Miniconda Prompt**, activar el entorno de trabajo: `conda activate TU_ENTORNO`.
3. Desde la carpeta `Berka_Equipo`, instalar dependencias: `python -m pip install -r requirements.txt`.
4. Instalar el perfilado obligatorio: `python -m pip install ydata-profiling` (desde el MISMO entorno del kernel). Reiniciar Jupyter si se acaba de instalar.
5. Ejecutar `jupyter lab` **desde la carpeta del proyecto**. Abrir `notebooks/` y ejecutar **01, 02, 03, 04**, en ese orden, cada uno con **Run All**.
6. Comprobar en `resultados/` que existen `03_perfilado_ydata.html` y `04_tabla_minable_berka.csv`.

Si el entorno de Jupyter tiene otro nombre, seleccionarlo en *Kernel → Change Kernel* antes de ejecutar. El notebook 03 avisa si falta `ydata_profiling` y continúa, **pero en ese caso la entrega queda incompleta hasta generar el HTML**.

## Trabajo colaborativo
Cada integrante edita **solo su notebook**, y todos revisan el informe. Los notebooks 02, 03 y 04 leen la **misma tabla 01_base_clientes.csv**, sin modificarla. La ejecución y los commits están detallados en `docs/MAPA_INFORME_Y_COMMITS.md`.

## Validación
`04_tabla_minable_berka.csv` debe contener un `client_id` único por fila, valores binarios en `tiene_tarjeta` y cero nulos. Las columnas de tarjeta derivadas directamente de Y quedan excluidas de X. El archivo `resultados/03_perfilado_ydata.html` se genera **solo si ydata-profiling está instalado**.

## Fuente y salvedades
Caso Banco Berka, PKDD'99; archivos `.asc` provistos para la práctica. Los cálculos de edad/antigüedad se refieren al 31/12/1998. Transacciones y saldos de una cuenta compartida pueden ser usados por más de un cliente; no representan movimientos individualizados. Los resultados no son evaluación real de capacidad de pago y podrían contener información posterior a la emisión de tarjeta (riesgo de fuga temporal).
