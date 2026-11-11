# 📘 Semana 3 · Mapas de Karnaugh y Simplificación de Circuitos

> **🎯 Unidad:** 1 – Análisis de lógica combinacional con diseño clásico.  
> **💡 Resultado de aprendizaje:** Aplica mapas de Karnaugh para simplificar funciones booleanas y optimizar la implementación de circuitos digitales.

---

## 🚀 1. Introducción

Los mapas de Karnaugh son una herramienta gráfica que permite simplificar funciones booleanas de manera visual, más rápida y ordenada que el método algebraico tradicional.

> 📌 **¿Por qué son importantes?** Se utilizan para reducir expresiones lógicas complejas, identificar términos comunes de forma intuitiva y disminuir drásticamente la cantidad de compuertas necesarias para implementar un circuito físico.

---

## 🗺️ 2. Concepto de Mapa de Karnaugh

Un mapa de Karnaugh es esencialmente una representación matricial de una tabla de verdad.

* 🔲 **Celdas:** Cada celda representa un minitérmino (una combinación de las variables de entrada) y contiene el valor de salida correspondiente ($0$ o $1$).
* 🎯 **Objetivo principal:** Agrupar celdas adyacentes con valor `1` utilizando potencias de dos ($1, 2, 4, 8\dots$) para obtener una expresión algebraica sumamente simplificada.

---

## 📐 3. Mapas de Karnaugh de Dos Variables

Un mapa de dos variables (como $A$ y $B$) contiene **4 celdas**, abarcando todas las combinaciones posibles.

| $A \setminus B$ | 0 | 1 |
| :---: | :---: | :---: |
| **0** | $m_0$ | $m_1$ |
| **1** | $m_2$ | $m_3$ |

---

## 🧊 4. Mapas de Karnaugh de Tres Variables

Un mapa de tres variables contiene **8 celdas**. Está organizado siguiendo el **código Gray**, lo que garantiza que las celdas adyacentes difieran en el cambio de una sola variable a la vez.

| $A \setminus BC$ | 00 | 01 | 11 | 10 |
| :---: | :---: | :---: | :---: | :---: |
| **0** | $m_0$ | $m_1$ | $m_3$ | $m_2$ |
| **1** | $m_4$ | $m_5$ | $m_7$ | $m_6$ |

---

## 🧊 5. Mapas de Karnaugh de Cuatro Variables

Un mapa de cuatro variables contiene **16 celdas**, distribuyendo dos variables en las filas ($AB$) y dos en las columnas ($CD$).

| $AB \setminus CD$ | 00 | 01 | 11 | 10 |
| :---: | :---: | :---: | :---: | :---: |
| **00** | $m_0$ | $m_1$ | $m_3$ | $m_2$ |
| **01** | $m_4$ | $m_5$ | $m_7$ | $m_6$ |
| **11** | $m_{12}$ | $m_{13}$ | $m_{15}$ | $m_{14}$ |
| **10** | $m_8$ | $m_9$ | $m_{11}$ | $m_{10}$ |

---

## 📋 6. Reglas para Agrupar

Para simplificar correctamente un mapa de Karnaugh se deben seguir estas reglas fundamentales:

1. 🎯 **Solo unos:** Agrupar exclusivamente celdas que contengan el valor `1` (para obtener expresiones en forma SOP).
2. 📏 **Potencias de 2:** Los grupos deben contener un número de celdas igual a $1, 2, 4, 8$ o $16$.
3. 📦 **Máximo tamaño:** Formar siempre los grupos del **mayor tamaño posible**.
4. 🔀 **Superposición:** Los grupos pueden superponerse entre sí cuando sea necesario para cubrir más celdas.
5. 🔄 **Adyacencia en bordes:** Los extremos del mapa (bordes opuestos) se consideran conectados y adyacentes en forma toroidal.
6. 🌐 **Cobertura total:** Todas las celdas con valor `1` deben quedar cubiertas por al menos un grupo.
7. 📉 **Mínimo número de grupos:** Buscar la menor cantidad de grupos posibles para evitar redundancias.

---

## 🔄 7. Procedimiento de Simplificación

Para simplificar cualquier función mediante mapas de Karnaugh, sigue estos pasos:

1. 📊 Obtener la **tabla de verdad** del problema.
2. 🔍 Identificar las combinaciones donde la función da como salida un `1`.
3. ✍️ Ubicar dichos valores `1` en las celdas correspondientes del mapa.
4. 📦 **Agrupar** las celdas adyacentes aplicando las reglas anteriores.
5. 🔎 Identificar las variables que **permanecen constantes** dentro de cada grupo (eliminando las que cambian).
6. ➕ Escribir la expresión algebraica simplificada sumando los términos resultantes.

---

## 📝 8. Ejemplo de Simplificación con Tres Variables

* **Función de partida:** 
  $$F(A,B,C) = \sum m(1, 3, 5, 7)$$

* **Mapa de Karnaugh resultante:**
  | $A \setminus BC$ | 00 | 01 | 11 | 10 |
  | :---: | :---: | :---: | :---: | :---: |
  | **0** | 0 | **1** | **1** | 0 |
  | **1** | 0 | **1** | **1** | 0 |

* **Proceso de agrupación:** Se agrupan las cuatro celdas centrales que contienen el valor `1` en un bloque de $2 \times 2$.
* **Análisis del grupo:**
  * La variable $A$ cambia de $0$ a $1$ (se elimina).
  * La variable $B$ cambia de $0$ a $1$ en unas columnas y de $1$ a $1$ en otras... examinando las columnas `01` y `11`, $B$ cambia (se elimina).
  * La variable $C$ permanece constante en el valor **`1`** en todas las celdas del grupo.

* **🎯 Resultado simplificado:**
  $$F = C$$

---

## 🔀 9. Condiciones Indiferentes (*Don't Care*)

* **Concepto:** Son combinaciones de entrada que las especificaciones del sistema garantizan que **nunca ocurrirán** o cuyas salidas son irrelevantes para el diseño.
* **Representación:** Se indican con una letra **`X`** en el mapa.
* **Utilidad:** Pueden ser tratadas como `1` o como `0` a conveniencia del diseñador, eligiendo el valor que permita formar grupos más grandes y lograr una **simplificación máxima**.

---

## 🔌 10. Compuertas NAND y NOR (Universales)

Las compuertas NAND y NOR se denominan **compuertas universales** porque es posible implementar cualquier función lógica básica (AND, OR, NOT) utilizándolas exclusivamente de forma individual.

### ✖️ 10.1. Compuerta NAND
Es la negación de la operación AND básica.
* **Expresión:** 
  $$Y = (A \cdot B)'$$

### ➕ 10.2. Compuerta NOR
Es la negación de la operación OR básica.
* **Expresión:** 
  $$Y = (A + B)'$$

---

## 🛠️ 11. Aplicaciones de los Mapas de Karnaugh

Los mapas de Karnaugh se aplican cotidianamente en:
* ⚙️ El diseño óptimo de circuitos combinacionales complejos.
* ✂️ La simplificación rápida de funciones booleanas sin errores algebraicos.
* 🎛️ El diseño eficiente de sistemas de control industrial y domótica.
* 📉 La reducción drástica de compuertas electrónicas físicas.
* ⚡ La optimización de retardos de propagación en circuitos digitales.


---

## 🏁 12. Conclusión

Los mapas de Karnaugh constituyen una herramienta metodológica fundamental para el análisis y simplificación de funciones booleanas. Su uso sistemático permite reducir de forma geométrica la complejidad de los circuitos digitales, minimizando el número de compuertas físicas requeridas, reduciendo el consumo energético y facilitando la implementación exitosa de sistemas combinacionales robustos.

---

## 📚 13. Bibliografía

* 📖 Mano, M. M. *Diseño digital*.
* 📖 Floyd, T. L. *Fundamentos de sistemas digitales*.
* 📖 Tocci, R. J., Widmer, N. S., y Moss, G. L. *Sistemas digitales: principios y aplicaciones*.
