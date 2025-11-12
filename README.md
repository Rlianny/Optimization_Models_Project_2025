# Proyecto de Optimización: Minimización de f(x,y) = (x²-1)² + (y²-2)²

## Descripción del Proyecto

Este proyecto implementa y compara dos métodos de optimización para encontrar el mínimo de la función objetivo:

**f(x,y) = (x²-1)² + (y²-2)²**

Los métodos implementados son:
- **Descenso del Gradiente (Gradient Descent)**: Método de primer orden basado en el gradiente
- **BFGS (Broyden-Fletcher-Goldfarb-Shanno)**: Método cuasi-Newton de segundo orden

El proyecto incluye:
- Análisis teórico completo de la función (gradiente, Hessiana, convexidad, puntos críticos)
- Implementación en Python de ambos métodos
- Framework de experimentación con configuraciones JSON
- Visualización de resultados y trayectorias de optimización
- Comparación detallada de rendimiento

## Estructura del Proyecto

```
Optimización/
├── README.md                           # Este archivo
├── Informe.md                          # Análisis teórico completo
├── Implementation/
│   ├── Methods_Implementation.ipynb   # Notebook con implementaciones
│   ├── Experiments/
│   │   ├── exp1.json                  # Configuración experimento 1
│   │   └── exp2.json                  # Configuración experimento 2
│   └── Results/
│       ├── results_exp1.json          # Resultados experimento 1
│       └── results_exp2.json          # Resultados experimento 2
```

## Instalación

### Requisitos

- Python 3.7 o superior
- python3-venv (para crear entornos virtuales)

### Paso 1: Crear un Entorno Virtual

Es **altamente recomendado** usar un entorno virtual para evitar conflictos con paquetes del sistema:

```bash
# Navegar a la carpeta del proyecto
cd /media/lianny/1AB44624B44602AD/projects/Optimización

# Crear entorno virtual
python3 -m venv venv

# Activar el entorno virtual
source venv/bin/activate
```

> **Nota**: Si obtienes un error al crear el entorno virtual, primero instala `python3-venv`:
> ```bash
> sudo apt install python3-venv python3-full
> ```

### Paso 2: Instalar Dependencias

Con el entorno virtual activado, instala las bibliotecas necesarias:

```bash
pip install numpy scipy matplotlib jupyter
```

### Versiones Recomendadas

- NumPy >= 1.19.0
- SciPy >= 1.5.0
- Matplotlib >= 3.3.0
- Jupyter >= 1.0.0

### Desactivar el Entorno Virtual

Cuando termines de trabajar:

```bash
deactivate
```

## Uso

### 1. Activar el Entorno Virtual

**IMPORTANTE**: Siempre debes activar el entorno virtual antes de trabajar con el proyecto:

```bash
# Desde la carpeta del proyecto
cd /media/lianny/1AB44624B44602AD/projects/Optimización
source venv/bin/activate
```

Verás que el prompt cambia mostrando `(venv)` al inicio.

### 2. Ejecutar el Notebook de Implementación

Con el entorno virtual activado:

```bash
cd Implementation
jupyter notebook Methods_Implementation.ipynb
```

Esto abrirá el notebook en tu navegador. Ejecuta las celdas en orden para:
1. Definir la función objetivo y su gradiente
2. Implementar los métodos de optimización
3. Ejecutar los experimentos configurados
4. Visualizar los resultados

### 2. Ejecutar Experimentos

Los experimentos se ejecutan automáticamente al correr la celda que contiene `MakeExperiments()` en el notebook.

Esta función:
- Lee las configuraciones desde `Experiments/exp*.json`
- Ejecuta ambos métodos (Gradient Descent y BFGS)
- Guarda los resultados en `Results/results_exp*.json`

### 3. Configurar Nuevos Experimentos

Para crear un nuevo experimento, añade un archivo JSON en la carpeta `Experiments/`:

```json
[
    {
        "learning_rate": 0.1,
        "tol": 1e-6,
        "max_iter": 1000,
        "x0": [0.5, 0.5]
    }
]
```

**Parámetros**:
- `learning_rate`: Tasa de aprendizaje para Gradient Descent (0.001 - 0.1)
- `tol`: Tolerancia para convergencia (típicamente 1e-6)
- `max_iter`: Número máximo de iteraciones (500 - 2000)
- `x0`: Punto inicial como lista [x, y]

### 4. Visualizar Resultados

Los resultados se visualizan automáticamente al ejecutar las celdas de visualización en el notebook:

- **Gráficos de contorno**: Muestran las curvas de nivel y las trayectorias de optimización
- **Análisis comparativo**: Tabla con iteraciones, tiempos, valores finales y distancia al óptimo

## Descripción de los Métodos

### Descenso del Gradiente

Método iterativo que se mueve en la dirección opuesta al gradiente:

```
x^(k+1) = x^(k) - α ∇f(x^(k))
```

- **Ventajas**: Simple, bajo costo por iteración
- **Desventajas**: Convergencia lenta, sensible a la tasa de aprendizaje

### BFGS

Método cuasi-Newton que aproxima la Hessiana inversa para encontrar direcciones más eficientes:

- **Ventajas**: Convergencia superlineal, ajuste automático del paso
- **Desventajas**: Mayor costo computacional por iteración

## Resultados Esperados

El mínimo teórico de la función es **f(x*) = 0** en cuatro puntos:
- (1, √2)
- (1, -√2)
- (-1, √2)
- (-1, -√2)

Los métodos deberían converger a uno de estos puntos dependiendo del punto inicial.

**Comparación típica**:
- BFGS converge en ~5-15 iteraciones
- Gradient Descent requiere ~50-500 iteraciones (dependiendo de α)
- BFGS alcanza mayor precisión en menos tiempo

## Interpretación de Resultados

### Archivo de Resultados JSON

```json
{
  "config": {...},
  "gradient_descent": {
    "x_opt": [x, y],           // Punto óptimo encontrado
    "f_opt": valor,            // Valor de f en el óptimo
    "iterations": n,           // Número de iteraciones
    "execution_time": t,       // Tiempo en segundos
    "trajectory": [[x,y], ...] // Puntos visitados
  },
  "bfgs": {...},
  "theoretical_minimum": {
    "x": [1.0, 1.414...],
    "f": 0.0
  }
}
```

### Métricas de Evaluación

1. **Iteraciones**: Menor es mejor (eficiencia)
2. **Tiempo de ejecución**: Menor es mejor (velocidad)
3. **Valor final f(x)**: Más cercano a 0 es mejor (precisión)
4. **Distancia al mínimo teórico**: ||x_opt - x*|| más pequeña es mejor

## Documentación Adicional

- **Informe.md**: Análisis teórico completo en español con:
  - Definición y propiedades de la función
  - Cálculo del gradiente y Hessiana
  - Análisis de convexidad
  - Determinación de puntos críticos
  - Descripción detallada de los algoritmos
  - Justificación de la selección de métodos
  - Comparación de resultados experimentales

## Troubleshooting

### Error: Módulo no encontrado

```bash
pip install numpy scipy matplotlib jupyter
```

### El notebook no se abre

Verifica que Jupyter esté instalado y ejecuta:

```bash
jupyter --version
```

### Convergencia lenta o no convergencia

- Ajusta el `learning_rate` (prueba valores entre 0.01 y 0.1)
- Aumenta `max_iter`
- Prueba diferentes puntos iniciales `x0`

### Resultados inesperados

- Verifica que los archivos de configuración JSON estén bien formados
- Asegúrate de que la carpeta `Results/` exista o se cree automáticamente
- Revisa el análisis teórico en `Informe.md` para entender los múltiples mínimos

## Autor
Lianny de la Caridad Revé Valdivieso
C311