# Modelos AR, MA y ARMA

## 1. AR(p) — Modelo Autorregresivo

El modelo **AR(p)** (*Autoregressive*) establece que el valor actual de la serie de tiempo depende de sus propios valores pasados.

La expresión general es:

$$
y_t
=
c
+
\phi_1 y_{t-1}
+
\phi_2 y_{t-2}
+
\dots
+
\phi_p y_{t-p}
+
\varepsilon_t
$$

De forma compacta:

$$
y_t
=
c
+
\sum_{i=1}^{p}
\phi_i y_{t-i}
+
\varepsilon_t
$$

---

## 2. MA(q) — Modelo de Media Móvil

El modelo **MA(q)** (*Moving Average*) establece que el valor actual de la serie depende de los **errores o choques aleatorios pasados**.

La expresión general es:

$$
y_t
=
\mu
+
\varepsilon_t
+
\theta_1 \varepsilon_{t-1}
+
\theta_2 \varepsilon_{t-2}
+
\dots
+
\theta_q \varepsilon_{t-q}
$$

De forma compacta:

$$
y_t
=
\mu
+
\varepsilon_t
+
\sum_{j=1}^{q}
\theta_j \varepsilon_{t-j}
$$

---

## 3. ARMA(p, q) — Modelo Autorregresivo de Media Móvil

El modelo **ARMA(p, q)** combina los componentes **AR(p)** y **MA(q)**.

Por lo tanto, el valor actual depende tanto de:

* los valores pasados de la propia serie de tiempo;
* como de los errores o choques aleatorios ocurridos en periodos anteriores.

La expresión general es:

$$
y_t
=
c
+
\sum_{i=1}^{p}
\phi_i y_{t-i}
+
\varepsilon_t
+
\sum_{j=1}^{q}
\theta_j \varepsilon_{t-j}
$$

---

# Significado de los parámetros y variables

|       Símbolo       | Significado                                                                                                                                |
| :-----------------: | ------------------------------------------------------------------------------------------------------------------------------------------ |
|        $y_t$        | **Valor actual de la serie de tiempo** en el instante $t$. Es la variable que el modelo intenta explicar o predecir.                       |
|         $c$         | **Término constante o intercepto** del modelo. Representa un nivel base de la serie.                                                       |
|        $\mu$        | **Media o nivel promedio** de la serie, utilizada principalmente en la representación del modelo MA.                                       |
|   $\varepsilon_t$   | **Ruido blanco o choque aleatorio** en el instante $t$. Es una perturbación impredecible, normalmente con media cero y varianza constante. |
|         $p$         | **Orden autorregresivo**. Indica cuántos valores pasados de la serie se utilizan en el modelo.                                             |
|         $q$         | **Orden de media móvil**. Indica cuántos errores o choques pasados se incorporan al modelo.                                                |
|      $y_{t-i}$      | **Valor rezagado (lag)** de la serie en el instante $t-i$. Representa un valor pasado de la variable.                                      |
| $\varepsilon_{t-j}$ | **Error o residuo pasado** correspondiente al instante $t-j$. Representa un choque ocurrido en un periodo anterior.                        |
|       $\phi_i$      | **Coeficientes autorregresivos**. Miden la magnitud y dirección de la influencia de los valores pasados de la serie sobre su valor actual. |
|      $\theta_j$     | **Coeficientes de media móvil**. Determinan cómo los errores o choques pasados influyen sobre el valor actual de la serie.                 |

---

## Interpretación intuitiva

Podemos entender los tres modelos de la siguiente manera:

### AR(p)

> **"El presente depende de mi propio pasado."**

$$
\text{Presente}
\leftarrow
\text{Valores pasados de la serie}
$$

### MA(q)

> **"El presente depende de los errores o choques del pasado."**

$$
\text{Presente}
\leftarrow
\text{Errores pasados}
$$

### ARMA(p,q)

> **"El presente depende tanto de mis valores pasados como de los errores pasados."**

$$
\text{Presente}
\leftarrow
\begin{cases}
\text{Valores pasados de la serie}\\
\text{Errores pasados}
\end{cases}
$$

---

## Resumen matemático

|     Modelo    | Dependencia principal     | Forma general                                                                                                    |
| :-----------: | ------------------------- | ---------------------------------------------------------------------------------------------------------------- |
|   **AR(p)**   | Valores pasados de $y_t$  | $\displaystyle y_t = c + \sum_{i=1}^{p}\phi_i y_{t-i} + \varepsilon_t$                                           |
|   **MA(q)**   | Errores pasados           | $\displaystyle y_t = \mu + \varepsilon_t + \sum_{j=1}^{q}\theta_j\varepsilon_{t-j}$                              |
| **ARMA(p,q)** | Valores y errores pasados | $\displaystyle y_t = c + \sum_{i=1}^{p}\phi_i y_{t-i} + \varepsilon_t + \sum_{j=1}^{q}\theta_j\varepsilon_{t-j}$ |
