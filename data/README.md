# 📂 Dataset de Videojuegos — Documentación Técnica

Este documento describe el conjunto de datos utilizado para el análisis de tendencias en videojuegos, incluyendo detalles sobre las columnas, su limpieza y transformaciones, y la gestión de calidad de los datos.

## 📥 Fuente del Dataset

- Dataset original disponible en Kaggle:  
  [Video Games Data — por sakibimtiaz](https://www.kaggle.com/datasets/sakibimtiaz/video-games-data)

- Formato original: `.csv` y `.xlsx`
- Se trabajó principalmente con el archivo `.xlsx` por mejor compatibilidad con Colab.

---

## 🧾 Descripción de las columnas principales

| Columna              | Descripción                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `id`                 | Identificador único para cada juego                                         |
| `slug`               | Versión simplificada del nombre del juego (para URLs)                       |
| `name`               | Nombre completo del videojuego                                              |
| `released`           | Fecha de lanzamiento                                                        |
| `tba`                | 0 o 1 — indica si está "por anunciarse"                                     |
| `background_image`   | URL de imagen del juego (en su mayoría inválidas o vacías)                  |
| `rating`             | Calificación promedio del juego (0 a 5)                                     |
| `rating_top`         | Calificación máxima alcanzada (normalmente 5)                               |
| `reviews_text_count` | Número de reseñas textuales                                                  |
| `metacritic`         | Calificación de Metacritic                                                  |
| `playtime`           | Tiempo promedio de juego en horas                                           |
| `suggestions_count`  | Número de sugerencias de usuarios                                           |
| `updated`            | Fecha de última actualización de datos del juego                            |
| `user_game`          | Indicador si fue generado por usuario                                       |
| `reviews_count`      | Total de reseñas (numérico)                                                 |

---

## 🧹 Limpieza y Transformación de Datos

- Se eliminaron columnas sin valor analítico (`background_image`, `user_game`).
- Se completaron valores nulos en `released` de forma manual, utilizando fuentes externas confiables.
- Se aplicó un **relleno con promedio** para valores faltantes en `metacritic`.
- Se convirtieron columnas `released` y `updated` al tipo `datetime`.
- Se removieron registros duplicados y se normalizó el formato de fechas.

---

## 📊 Gobernanza y Gestión de Calidad

Este proyecto aplica principios de gobernanza autogestionada:

- **Data Owner:** Responsable de la integridad general del dataset.
- **Data Steward:** Documenta y supervisa actualizaciones.
- **Data Analyst:** Limpieza, transformación y análisis exploratorio (EDA).

Se verificaron:

- **Integridad**: sin duplicados, formatos estandarizados.
- **Exactitud**: validación de fechas, calificaciones y nombres.
- **Completitud**: sin valores nulos en columnas clave (`name`, `released`, `rating`).
- **Consistencia**: uniformidad de nombres y estructuras.

---

## 🛡️ Consideraciones Éticas y Seguridad

- El dataset **no contiene datos personales** o sensibles.
- Se mantiene copia local del dataset original y el limpio.
- La documentación del proceso permite **reproducibilidad y transparencia**.

---

## 🔍 Observaciones Adicionales

- Se detectó que las URL de imágenes estaban rotas por ello no se contemplo un análisis de tendencias sobre las portadas de los videojuegos. 
- Si se tuviera acceso a texto completo de reseñas, podría explorarse un análisis de sentimiento.
- El dataset permite analizar **tendencias históricas, correlaciones, y géneros dominantes**.


