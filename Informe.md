# Informe del Proyecto de Optimización: Minimización de f(x,y) = (x²-1)² + (y²-2)²

## 1. Definición de la Función, Dominio y Signo

### 1.1 Definición de la Función

La función objetivo a minimizar es:

$$f(x,y) = (x^2 - 1)^2 + (y^2 - 2)^2$$

Esta función es una composición de funciones polinomiales de grado cuatro.

### 1.2 Dominio

El dominio de la función es:

$$D_f = \mathbb{R}^2$$

La función está definida para todos los pares ordenados $(x, y) \in \mathbb{R}^2$, ya que no existen restricciones algebraicas (como divisiones por cero, raíces de números negativos, o logaritmos de números no positivos).

### 1.3 Signo de la Función

Dado que $f(x,y)$ es la suma de dos términos elevados al cuadrado:

$$f(x,y) = \underbrace{(x^2 - 1)^2}_{\geq 0} + \underbrace{(y^2 - 2)^2}_{\geq 0} \geq 0$$

Por lo tanto:

$$f(x,y) \geq 0 \quad \forall (x,y) \in \mathbb{R}^2$$

La función alcanza su valor mínimo global de 0 cuando ambos términos son simultáneamente cero:

$$x^2 - 1 = 0 \quad \text{y} \quad y^2 - 2 = 0$$

## 2. Análisis de las Variables de la Función

### 2.1 Tipo de Variables

Las variables $x$ e $y$ son **variables continuas** que toman valores en el conjunto de los números reales $\mathbb{R}$.

- **Continuas**: Ambas variables pueden tomar cualquier valor real dentro de su dominio, sin restricciones de discreción o valores enteros.
- **No acotadas**: No existen límites superiores o inferiores para los valores que pueden tomar $x$ e $y$.

### 2.2 Independencia de las Variables

Las variables $x$ e $y$ son **independientes** entre sí, ya que la función se puede escribir como la suma de dos funciones separables:

$$f(x,y) = g(x) + h(y)$$

donde:
- $g(x) = (x^2 - 1)^2$
- $h(y) = (y^2 - 2)^2$

Esta separabilidad implica que el comportamiento de la función respecto a $x$ es independiente del valor de $y$ y viceversa.

## 3. Análisis de Continuidad y Diferenciabilidad

### 3.1 Continuidad

La función $f(x,y)$ es **continua** en todo su dominio $\mathbb{R}^2$.

**Justificación**: $f(x,y)$ es una composición y suma de funciones polinomiales, las cuales son continuas en $\mathbb{R}$. Específicamente:

- $x^2$, $y^2$ son funciones polinomiales continuas
- $(x^2 - 1)$ y $(y^2 - 2)$ son continuas (suma/resta de funciones continuas)
- $(x^2 - 1)^2$ y $(y^2 - 2)^2$ son continuas (composición de funciones continuas)
- La suma de funciones continuas es continua

### 3.2 Diferenciabilidad

La función $f(x,y)$ es **infinitamente diferenciable** (clase $C^{\infty}$) en todo $\mathbb{R}^2$.

**Justificación**: Las funciones polinomiales son diferenciables en todo su dominio, y la composición y suma de funciones diferenciables es diferenciable. Podemos calcular derivadas parciales de cualquier orden.

## 4. Gradiente: ∇f(x,y)

El gradiente de la función es el vector de derivadas parciales de primer orden:

$$\nabla f(x,y) = \left[\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right]$$

### 4.1 Cálculo de las Derivadas Parciales

**Derivada parcial respecto a x**:

$$\frac{\partial f}{\partial x} = \frac{\partial}{\partial x}[(x^2 - 1)^2 + (y^2 - 2)^2]$$

Aplicando la regla de la cadena:

$$\frac{\partial f}{\partial x} = 2(x^2 - 1) \cdot 2x = 4x(x^2 - 1)$$

**Derivada parcial respecto a y**:

$$\frac{\partial f}{\partial y} = \frac{\partial}{\partial y}[(x^2 - 1)^2 + (y^2 - 2)^2]$$

Aplicando la regla de la cadena:

$$\frac{\partial f}{\partial y} = 2(y^2 - 2) \cdot 2y = 4y(y^2 - 2)$$

### 4.2 Gradiente

Por lo tanto, el gradiente es:

$$\nabla f(x,y) = \begin{bmatrix} 4x(x^2 - 1) \\ 4y(y^2 - 2) \end{bmatrix}$$

## 5. Matriz Hessiana

La matriz Hessiana $H_f(x,y)$ contiene las derivadas parciales de segundo orden:

$$H_f(x,y) = \begin{bmatrix} 
\frac{\partial^2 f}{\partial x^2} & \frac{\partial^2 f}{\partial x \partial y} \\
\frac{\partial^2 f}{\partial y \partial x} & \frac{\partial^2 f}{\partial y^2}
\end{bmatrix}$$

### 5.1 Cálculo de las Derivadas de Segundo Orden

**Derivada segunda respecto a x**:

$$\frac{\partial^2 f}{\partial x^2} = \frac{\partial}{\partial x}[4x(x^2 - 1)] = 4(x^2 - 1) + 4x \cdot 2x = 4x^2 - 4 + 8x^2 = 12x^2 - 4$$

**Derivada segunda respecto a y**:

$$\frac{\partial^2 f}{\partial y^2} = \frac{\partial}{\partial y}[4y(y^2 - 2)] = 4(y^2 - 2) + 4y \cdot 2y = 4y^2 - 8 + 8y^2 = 12y^2 - 8$$

**Derivadas cruzadas**:

$$\frac{\partial^2 f}{\partial x \partial y} = \frac{\partial}{\partial y}[4x(x^2 - 1)] = 0$$

$$\frac{\partial^2 f}{\partial y \partial x} = \frac{\partial}{\partial x}[4y(y^2 - 2)] = 0$$

### 5.2 Matriz Hessiana

$$H_f(x,y) = \begin{bmatrix} 
12x^2 - 4 & 0 \\
0 & 12y^2 - 8
\end{bmatrix}$$

La matriz Hessiana es **diagonal**, lo que confirma la independencia de las variables.

## 6. Análisis de Convexidad

### 6.1 Condiciones de Convexidad

Una función es convexa si su Hessiana es semidefinida positiva (todos sus valores propios son no negativos) en todo su dominio.

### 6.2 Valores Propios de la Hessiana

Dado que la Hessiana es diagonal, sus valores propios son simplemente los elementos de la diagonal:

$$\lambda_1 = 12x^2 - 4$$
$$\lambda_2 = 12y^2 - 8$$

### 6.3 Análisis de Convexidad

Para que la función sea convexa globalmente, necesitamos que ambos valores propios sean no negativos para todo $(x,y) \in \mathbb{R}^2$:

$$\lambda_1 = 12x^2 - 4 \geq 0 \Rightarrow x^2 \geq \frac{1}{3} \Rightarrow |x| \geq \frac{1}{\sqrt{3}}$$

$$\lambda_2 = 12y^2 - 8 \geq 0 \Rightarrow y^2 \geq \frac{2}{3} \Rightarrow |y| \geq \sqrt{\frac{2}{3}}$$

**Conclusión**: La función **NO es convexa globalmente** en $\mathbb{R}^2$, sino que es convexa solo en la región:

$$R = \left\{(x,y) : |x| \geq \frac{1}{\sqrt{3}} \text{ y } |y| \geq \sqrt{\frac{2}{3}}\right\}$$

En las regiones donde $|x| < \frac{1}{\sqrt{3}}$ o $|y| < \sqrt{\frac{2}{3}}$, la función es **no convexa** (cóncava localmente).

### 6.4 Implicaciones

La no convexidad global implica que:
- Pueden existir múltiples mínimos locales
- Los métodos de optimización basados en gradiente podrían converger a diferentes soluciones dependiendo del punto inicial
- Se requiere un análisis cuidadoso de los puntos críticos

## 7. Determinación del Mínimo Teórico

### 7.1 Puntos Críticos

Los puntos críticos se encuentran donde el gradiente es cero:

$$\nabla f(x,y) = \begin{bmatrix} 4x(x^2 - 1) \\ 4y(y^2 - 2) \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

Esto requiere:

$$4x(x^2 - 1) = 0 \quad \Rightarrow \quad x = 0 \text{ o } x = \pm 1$$

$$4y(y^2 - 2) = 0 \quad \Rightarrow \quad y = 0 \text{ o } y = \pm\sqrt{2}$$

### 7.2 Lista de Puntos Críticos

Combinando todas las posibilidades, obtenemos 9 puntos críticos:

1. $(0, 0)$
2. $(0, \sqrt{2})$
3. $(0, -\sqrt{2})$
4. $(1, 0)$
5. $(1, \sqrt{2})$
6. $(1, -\sqrt{2})$
7. $(-1, 0)$
8. $(-1, \sqrt{2})$
9. $(-1, -\sqrt{2})$

## 8. Análisis de los Puntos Críticos

### 8.1 Clasificación mediante el Criterio de la Hessiana

Para clasificar cada punto crítico, evaluamos la Hessiana en cada punto y analizamos sus valores propios.

**Punto (0, 0)**:

$$H_f(0,0) = \begin{bmatrix} -4 & 0 \\ 0 & -8 \end{bmatrix}$$

Valores propios: $\lambda_1 = -4 < 0$, $\lambda_2 = -8 < 0$ → **Máximo local**

$$f(0,0) = (0-1)^2 + (0-2)^2 = 1 + 4 = 5$$

**Punto (0, ±√2)**:

$$H_f(0, \pm\sqrt{2}) = \begin{bmatrix} -4 & 0 \\ 0 & 16 \end{bmatrix}$$

Valores propios: $\lambda_1 = -4 < 0$, $\lambda_2 = 16 > 0$ → **Punto silla**

$$f(0, \pm\sqrt{2}) = (0-1)^2 + (2-2)^2 = 1$$

**Punto (±1, 0)**:

$$H_f(\pm 1, 0) = \begin{bmatrix} 8 & 0 \\ 0 & -8 \end{bmatrix}$$

Valores propios: $\lambda_1 = 8 > 0$, $\lambda_2 = -8 < 0$ → **Punto silla**

$$f(\pm 1, 0) = (1-1)^2 + (0-2)^2 = 4$$

**Punto (±1, ±√2)**:

$$H_f(\pm 1, \pm\sqrt{2}) = \begin{bmatrix} 8 & 0 \\ 0 & 16 \end{bmatrix}$$

Valores propios: $\lambda_1 = 8 > 0$, $\lambda_2 = 16 > 0$ → **Mínimo local**

$$f(\pm 1, \pm\sqrt{2}) = (1-1)^2 + (2-2)^2 = 0$$

### 8.2 Resumen de la Clasificación

| Punto | Tipo | f(x,y) |
|-------|------|--------|
| $(0, 0)$ | Máximo local | 5 |
| $(0, \sqrt{2})$ | Punto silla | 1 |
| $(0, -\sqrt{2})$ | Punto silla | 1 |
| $(1, 0)$ | Punto silla | 4 |
| $(-1, 0)$ | Punto silla | 4 |
| $(1, \sqrt{2})$ | **Mínimo global** | **0** |
| $(1, -\sqrt{2})$ | **Mínimo global** | **0** |
| $(-1, \sqrt{2})$ | **Mínimo global** | **0** |
| $(-1, -\sqrt{2})$ | **Mínimo global** | **0** |

## 9. Análisis del Óptimo

### 9.1 Mínimos Globales

La función tiene **cuatro mínimos globales** con el mismo valor:

$$x^* \in \{(1, \sqrt{2}), (1, -\sqrt{2}), (-1, \sqrt{2}), (-1, -\sqrt{2})\}$$

$$f(x^*) = 0$$

### 9.2 Interpretación Geométrica

Estos cuatro mínimos corresponden a las cuatro combinaciones de signos que satisfacen:
- $x^2 = 1 \Rightarrow x = \pm 1$
- $y^2 = 2 \Rightarrow y = \pm\sqrt{2}$

La existencia de múltiples mínimos globales es consistente con la estructura simétrica de la función y su no convexidad en ciertas regiones.

### 9.3 Características del Óptimo

- **Valor óptimo**: $f^* = 0$
- **Número de soluciones óptimas**: 4 (simétricamente distribuidas)
- **Naturaleza**: Mínimos globales estrictos localmente (cada uno es el único mínimo en su vecindad)

## 10. Descripción de los Algoritmos Utilizados

### 10.1 Método del Descenso del Gradiente (Gradient Descent)

#### 10.1.1 Descripción General

El método del Descenso del Gradiente es un algoritmo iterativo de optimización de primer orden que se mueve en la dirección opuesta al gradiente para encontrar un mínimo local de una función.

#### 10.1.2 Fundamento Matemático

El gradiente $\nabla f(x)$ apunta en la dirección de mayor crecimiento de la función. Por lo tanto, el negativo del gradiente $-\nabla f(x)$ apunta en la dirección de mayor decrecimiento, lo que lo convierte en una dirección de descenso.

#### 10.1.3 Algoritmo

Dado un punto inicial $x^{(0)}$ y una tasa de aprendizaje $\alpha > 0$:

1. **Inicialización**: $k = 0$, $x = x^{(0)}$
2. **Iteración**: Mientras $\|\nabla f(x^{(k)})\| > \epsilon$ y $k < k_{max}$:
   $$x^{(k+1)} = x^{(k)} - \alpha \nabla f(x^{(k)})$$
   $$k = k + 1$$
3. **Terminación**: Retornar $x^{(k)}$ como aproximación del mínimo

#### 10.1.4 Parámetros

- **learning_rate** ($\alpha$): Controla el tamaño del paso en cada iteración
  - Valores muy grandes: Pueden causar divergencia u oscilaciones
  - Valores muy pequeños: Convergencia lenta
  - Típicamente: $0.001 \leq \alpha \leq 0.1$

- **tol** ($\epsilon$): Tolerancia para el criterio de parada basado en la norma del gradiente
  - Cuando $\|\nabla f(x)\| < \epsilon$, se considera que se ha alcanzado un punto crítico
  - Típicamente: $10^{-6} \leq \epsilon \leq 10^{-4}$

- **max_iter** ($k_{max}$): Número máximo de iteraciones para evitar bucles infinitos

#### 10.1.5 Ventajas

- Simple de implementar
- Bajo costo computacional por iteración
- Requiere solo el cálculo del gradiente (derivadas de primer orden)
- Garantiza descenso en cada iteración (con $\alpha$ apropiado)

#### 10.1.6 Desventajas

- Convergencia puede ser lenta, especialmente cerca del óptimo
- Sensible a la elección de la tasa de aprendizaje
- Puede atascarse en mínimos locales o puntos silla
- No es eficiente para funciones mal condicionadas

#### 10.1.7 Justificación de Selección

Se seleccionó este algoritmo porque:
1. **Simplicidad**: Es el método de optimización basado en gradiente más fundamental
2. **Referencia**: Sirve como línea base para comparar con métodos más sofisticados
3. **Interpretabilidad**: Su comportamiento es fácil de entender y visualizar
4. **Aplicabilidad**: Funciona bien para funciones suaves y diferenciables como nuestra función objetivo

### 10.2 Método Cuasi-Newton BFGS

#### 10.2.1 Descripción General

BFGS (Broyden-Fletcher-Goldfarb-Shanno) es un método cuasi-Newton que aproxima la matriz Hessiana inversa para encontrar direcciones de búsqueda más eficientes que el gradiente puro.

#### 10.2.2 Fundamento Matemático

Los métodos de Newton utilizan información de segundo orden (la Hessiana) para encontrar la dirección de búsqueda:

$$x^{(k+1)} = x^{(k)} - H_f^{-1}(x^{(k)}) \nabla f(x^{(k)})$$

Sin embargo, calcular y invertir la Hessiana es costoso. BFGS construye iterativamente una aproximación $B_k$ de $H_f^{-1}$ usando solo evaluaciones del gradiente.

#### 10.2.3 Algoritmo

1. **Inicialización**: $k = 0$, $x^{(0)}$, $B_0 = I$ (matriz identidad)
2. **Iteración**: Para $k = 0, 1, 2, ...$:
   
   a. Calcular dirección de búsqueda: $p_k = -B_k \nabla f(x^{(k)})$
   
   b. Búsqueda de línea: Encontrar $\alpha_k$ que minimice $f(x^{(k)} + \alpha_k p_k)$
   
   c. Actualizar posición: $x^{(k+1)} = x^{(k)} + \alpha_k p_k$
   
   d. Calcular diferencias:
      - $s_k = x^{(k+1)} - x^{(k)}$
      - $y_k = \nabla f(x^{(k+1)}) - \nabla f(x^{(k)})$
   
   e. Actualizar aproximación de la Hessiana inversa (fórmula BFGS):
      $$B_{k+1} = B_k + \frac{(s_k^T y_k + y_k^T B_k y_k)(s_k s_k^T)}{(s_k^T y_k)^2} - \frac{B_k y_k s_k^T + s_k y_k^T B_k}{s_k^T y_k}$$

3. **Terminación**: Cuando $\|\nabla f(x^{(k)})\| < \epsilon$ o $k \geq k_{max}$

#### 10.2.4 Implementación

Se utiliza la implementación de `scipy.optimize.minimize` con `method='BFGS'`, que incluye:
- Búsqueda de línea robusta (condiciones de Wolfe)
- Manejo numérico estable de la actualización BFGS
- Criterios de convergencia sofisticados

#### 10.2.5 Parámetros

- **tol**: Tolerancia para convergencia del gradiente
- **max_iter**: Número máximo de iteraciones
- No requiere especificar learning_rate (se determina automáticamente mediante búsqueda de línea)

#### 10.2.6 Ventajas

- **Convergencia superlineal**: Mucho más rápida que el descenso del gradiente cerca del óptimo
- **Adaptativo**: La búsqueda de línea ajusta automáticamente el tamaño del paso
- **Curvatura**: Utiliza información de segundo orden sin calcular explícitamente la Hessiana
- **Eficiente**: Requiere menos iteraciones que métodos de primer orden
- **Robusto**: La implementación de SciPy incluye salvaguardas numéricas

#### 10.2.7 Desventajas

- Más complejo de implementar desde cero
- Mayor costo computacional por iteración (actualización de $B_k$)
- Requiere almacenar una matriz $n \times n$ (donde $n$ es la dimensión)
- Puede fallar si la función no es suficientemente suave

#### 10.2.8 Justificación de Selección

Se seleccionó BFGS porque:
1. **Eficiencia**: Es uno de los métodos cuasi-Newton más efectivos y ampliamente utilizados
2. **Estado del arte**: Representa el estándar industrial para optimización no lineal sin restricciones
3. **Comparación**: Permite contrastar un método sofisticado de segundo orden con el simple descenso del gradiente
4. **Biblioteca**: La implementación en SciPy es robusta y bien probada
5. **Aplicabilidad**: Nuestra función es suave (clase $C^{\infty}$), ideal para BFGS

### 10.3 Uso de Librerías

#### 10.3.1 NumPy

- **Propósito**: Operaciones con arrays y álgebra lineal
- **Uso**: Vectores, cálculo de normas, operaciones matriciales
- **Justificación**: Estándar de facto para computación numérica en Python

#### 10.3.2 SciPy

- **Propósito**: Algoritmos científicos avanzados
- **Uso**: Implementación de BFGS mediante `scipy.optimize.minimize`
- **Justificación**: Implementación robusta y optimizada de algoritmos de optimización

#### 10.3.3 Matplotlib

- **Propósito**: Visualización de resultados
- **Uso**: Gráficos de contorno y trayectorias de optimización
- **Justificación**: Biblioteca estándar para visualización en Python científico

## 11. Comparación de Resultados

### 11.1 Criterios de Comparación

Los métodos se comparan según:

1. **Número de iteraciones**: ¿Cuántos pasos requiere cada método para converger?
2. **Tiempo de ejecución**: ¿Cuánto tiempo toma la optimización?
3. **Valor final de la función**: ¿Qué tan cerca está del mínimo teórico?
4. **Punto final**: ¿A cuál de los cuatro mínimos globales converge?
5. **Sensibilidad al punto inicial**: ¿Cómo afecta $x^{(0)}$ al resultado?
6. **Impacto del learning rate**: (Solo para Gradient Descent) ¿Cómo afecta $\alpha$ a la convergencia?

### 11.2 Experimentos Diseñados

#### Experimento 1 (exp1.json)
- **Punto inicial**: $(0.5, 0.5)$ - Cerca del origen, región no convexa
- **Learning rate**: $0.1$ - Moderado
- **Objetivo**: Evaluar convergencia desde un punto cercano al máximo local

#### Experimento 2 (exp2.json)
- **Punto inicial**: $(-1.5, -1.0)$ - Lejos del origen, más cerca de un mínimo
- **Learning rate**: $0.05$ - Más conservador
- **Objetivo**: Evaluar convergencia desde diferentes regiones del espacio

### 11.3 Análisis Esperado

**Gradient Descent**:
- Convergencia más lenta
- Muy sensible a la tasa de aprendizaje
- Puede requerir muchas iteraciones para alcanzar alta precisión
- Trayectoria en forma de zigzag en regiones mal condicionadas

**BFGS**:
- Convergencia rápida (pocas iteraciones)
- Ajuste automático del tamaño de paso
- Alta precisión en el resultado final
- Trayectoria más directa hacia el óptimo

### 11.4 Resultados de los Experimentos

Los resultados específicos se generan al ejecutar el notebook y se guardan en archivos JSON en la carpeta `Results/`. Cada archivo contiene:

```json
{
  "config": {...},
  "gradient_descent": {
    "x_opt": [...],
    "f_opt": ...,
    "iterations": ...,
    "execution_time": ...,
    "trajectory": [...]
  },
  "bfgs": {
    "x_opt": [...],
    "f_opt": ...,
    "iterations": ...,
    "execution_time": ...,
    "trajectory": [...]
  },
  "theoretical_minimum": {
    "x": [1.0, 1.4142135623730951],
    "f": 0.0
  }
}
```

## 12. Visualización del Modelo y las Instancias de los Algoritmos

### 12.1 Gráficos de Contorno

Los gráficos de contorno muestran:
- **Curvas de nivel**: Líneas de igual valor de la función $f(x,y)$
- **Trayectoria**: Puntos visitados por cada algoritmo (conectados por líneas)
- **Mínimo teórico**: Marcado con una estrella verde

### 12.2 Interpretación Visual

- **Gradient Descent** (rojo): Trayectoria más larga, pasos más pequeños cerca del óptimo
- **BFGS** (azul): Trayectoria más corta y directa
- **Curvas de nivel**: Muestran la topología de la función, incluyendo los cuatro mínimos globales

### 12.3 Información Revelada

Los gráficos permiten visualizar:
1. La naturaleza no convexa de la función en ciertas regiones
2. La estructura simétrica con cuatro mínimos
3. La presencia de puntos silla y el máximo local en el origen
4. La eficiencia relativa de cada método
5. El comportamiento de convergencia en diferentes regiones del espacio

## 13. Conclusiones

### 13.1 Sobre la Función

- La función tiene estructura cuártica no convexa globalmente
- Existen 4 mínimos globales equivalentes y varios puntos silla
- La separabilidad simplifica el análisis pero la no convexidad introduce complejidad

### 13.2 Sobre los Métodos

- **Gradient Descent**: Simple pero ineficiente, adecuado para problemas simples o como método base
- **BFGS**: Superior en casi todos los aspectos, es la elección preferida para este tipo de problemas

### 13.3 Recomendaciones

Para minimizar funciones suaves no lineales:
1. Usar métodos cuasi-Newton (BFGS) cuando sea posible
2. Probar múltiples puntos iniciales para explorar diferentes cuencas de atracción
3. Considerar la topología de la función (convexidad, múltiples mínimos)
4. Ajustar cuidadosamente los hiperparámetros en métodos de primer orden

### 13.4 Consideraciones Finales

Este estudio demuestra la importancia de:
- Análisis teórico exhaustivo antes de aplicar algoritmos
- Comparación empírica de múltiples métodos
- Visualización para entender el comportamiento de los algoritmos
- Documentación clara de decisiones y resultados
