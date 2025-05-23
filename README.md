# Q-Learning en MountainCar-v0 con Gym

Este proyecto implementa el algoritmo de **Q-Learning** para resolver el problema de control del entorno **MountainCar-v0** en la biblioteca **Gym**.  
Para más información, puedes visitar el siguiente [enlace a la documentación oficial de MountainCar-v0 en Gym](https://www.gymlibrary.dev/environments/classic_control/mountain_car/).

## Descripción

En este proyecto, se entrena un agente utilizando el algoritmo de Q-Learning para aprender a controlar un automóvil en una montaña. El objetivo es aprender a mover el automóvil hacia la cima de la montaña utilizando una política basada en recompensas y penalizaciones.

### Entorno

El entorno utilizado es **MountainCar-v0** de Gym, donde el agente debe mover un automóvil hacia la cima de una montaña. El espacio de acciones tiene tres posibles opciones:
- **0**: Acelerar hacia la izquierda.
- **1**: No hacer nada.
- **2**: Acelerar hacia la derecha.

El espacio de observación es de dos dimensiones:
- **0**: Posición de la montaña en el eje X (entre -1.2 y 0.6).
- **1**: Velocidad del automóvil (entre -0.07 y 0.07).

## Objetivo

El objetivo es que el agente aprenda a maximizar la recompensa a través de **Q-Learning**, el cual ajusta la política del agente para seleccionar la mejor acción en cada estado. La implementación incluye:

- Discretización del espacio de estados.
- Inicialización y actualización de la **Q-table**.
- Visualización de la política aprendida durante el entrenamiento.

## Fórmula de Q-Learning

La actualización de los valores Q sigue esta fórmula:

# New Q(s, a) = Q(s, a) + α [ R(s, a) + γ max Q(s', a') - Q(s, a) ]

Donde:

- **New Q(s, a)**: Nuevo valor Q para el estado `s` y acción `a`.
- **Q(s, a)**: Valor Q actual para el estado `s` y acción `a`.
- **α (alpha)**: Tasa de aprendizaje (Learning Rate).
- **R(s, a)**: Recompensa por tomar la acción `a` en el estado `s`.
- **γ (gamma)**: Tasa de descuento (Discount Rate), que mide la importancia de las recompensas futuras.
- **max Q(s', a')**: Máximo valor esperado de recompensa futura para el siguiente estado `s'` al tomar la mejor acción `a'`.

### Resumen visual de los elementos de la fórmula:

| Elemento | Significado |
|:---|:---|
| **New Q(s, a)** | Nuevo valor Q para el estado y acción |
| **Q(s, a)** | Valores actuales de Q |
| **α** | Tasa de aprendizaje |
| **R(s, a)** | Recompensa obtenida por la acción en el estado |
| **γ** | Tasa de descuento |
| **max Q(s', a')** | Máxima recompensa futura esperada |

## Instalación

Para ejecutar este proyecto, necesitarás tener instalado **Python** y algunas librerías. Puedes instalar las dependencias utilizando el archivo `environment.yml`:

```bash
conda env create -f environment.yml
