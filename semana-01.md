# 📚 Semana 1 · Sistemas Numéricos, Códigos y Compuertas Lógicas

> **🎯 Unidad:** 1 – Análisis de lógica combinacional con diseño clásico.  
> **💡 Resultado de aprendizaje:** Diseña e implementa circuitos combinacionales básicos utilizando técnicas de diseño clásico.

---

## 🚀 1. Introducción

Los sistemas digitales utilizan señales que representan dos estados lógicos: **0** y **1**. Estos valores permiten representar información, realizar operaciones matemáticas y construir circuitos electrónicos.

En esta semana se estudian:
* 🔢 Los sistemas numéricos (**binario, octal, decimal y hexadecimal**).
* ➕ La **aritmética binaria**.
* 🔠 Los **códigos digitales**.
* 🔌 Las principales **compuertas lógicas**.

> 📌 **¿Por qué es importante?** Estos conocimientos son necesarios para comprender cómo funciona internamente una computadora y cómo se representa la información mediante circuitos electrónicos.

---

## 🔢 2. Sistemas Numéricos

Un sistema numérico es un conjunto de símbolos y reglas que permite representar cantidades. En electrónica digital se utilizan principalmente cuatro sistemas:

| 🌐 Sistema | 📌 Base | 🔤 Dígitos utilizados |
| :--- | :---: | :--- |
| **Binario** | 2 | `0` y `1` |
| **Octal** | 8 | `0` al `7` |
| **Decimal** | 10 | `0` al `9` |
| **Hexadecimal** | 16 | `0` al `9` y `A` al `F` |

---

### 🟢 2.1 Sistema Decimal
Es el sistema que utilizamos normalmente en nuestra vida cotidiana. Su base es **10** y utiliza diez dígitos.

* **Ejemplo de descomposición:**
  $$\begin{aligned} 253 &= 2 \times 100 + 5 \times 10 + 3 \times 1 \\ &= 200 + 50 + 3 \end{aligned}$$

---

### 🔵 2.2 Sistema Binario
Es el sistema utilizado por las computadoras y los circuitos digitales. Su base es **2** y solamente utiliza los números `0` y `1`. Cada dígito binario recibe el nombre de **bit**.

* **Ejemplo de conversión a decimal:**
  $$\begin{aligned} 1011_2 &= 1 \times 8 + 0 \times 4 + 1 \times 2 + 1 \times 1 \\ &= 8 + 0 + 2 + 1 \\ &= 11_{10} \end{aligned}$$

---

### 🔄 2.3 Conversión de Decimal a Binario
Para convertir un número decimal a binario se divide sucesivamente entre **2** y se anotan los residuos. Finalmente, se leen los residuos **desde abajo hacia arriba**.

> 📝 **Ejemplo:** Convertir el número $25$ a binario.
> * $25 \div 2 = 12$, residuo **`1`**
> * $12 \div 2 = 6$, residuo **`0`**
> * $6 \div 2 = 3$, residuo **`0`**
> * $3 \div 2 = 1$, residuo **`1`**
> * $1 \div 2 = 0$, residuo **`1`**

🎯 **Resultado:**  
$$25_{10} = 11001_2$$

---

### 🟠 2.4 Sistema Octal
Su base es **8** y utiliza los dígitos del `0` al `7`. Para convertir un número binario a octal, se agrupan los bits de **tres en tres**, comenzando desde la derecha.

> 📝 **Ejemplo:** Convertir $10011101_2$ a octal.
> 1. **Agrupación:** `010` `011` `101`
> 2. **Conversión individual:**
>    * `010` = 2
>    * `011` = 3
>    * `101` = 5

🎯 **Resultado:**  
$$10011101_2 = 235_8$$

---

### 🟣 2.5 Sistema Hexadecimal
Su base es **16**. Utiliza los números del `0` al `9` y las letras `A, B, C, D, E, F`.

| 🔟 Decimal | 🔠 Hexadecimal |
| :---: | :---: |
| 10 | **A** |
| 11 | **B** |
| 12 | **C** |
| 13 | **D** |
| 14 | **E** |
| 15 | **F** |

> 📝 **Ejemplo:** Convertir $10011101_2$ a hexadecimal agrupando los bits de **cuatro en cuatro**.
> * `1001` = **9**
> * `1101` = **D**

🎯 **Resultado:**  
$$10011101_2 = 9D_{16}$$

---

## ➕ 3. Aritmética Binaria

La aritmética binaria permite realizar operaciones matemáticas utilizando únicamente los valores `0` y `1`.

### ➕ 3.1 Suma Binaria
Las reglas principales son las siguientes:

| ⚙️ Operación | ✨ Resultado |
| :---: | :---: |
| `0 + 0` | `0` |
| `0 + 1` | `1` |
| `1 + 0` | `1` |
| `1 + 1` | `10` *(Acarreo 1)* |
| `1 + 1 + 1` | `11` *(Acarreo 1 y suma 1)* |

> 💡 **Nota:** Cuando se obtiene un resultado de dos bits, el bit de la izquierda se lleva a la siguiente columna. Esto se conoce como **acarreo**.

* **Ejemplo de operación:**

```text
     1 1   (Acarreos)
     1011
   + 0110
   ------
    10001
