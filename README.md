import matplotlib.pyplot as plt
import numpy as np

# Coeficientes de la función de utilidad
alpha = 0.5
beta = 0.5

# Definir la función de utilidad
def utility_function(x, y):
    return x**alpha * y**beta

# Crear datos para la curva de indiferencia
x_values = np.linspace(0.1, 5, 100)
y_values = np.linspace(0.1, 5, 100)
X, Y = np.meshgrid(x_values, y_values)
Z = utility_function(X, Y)

# Plotear la curva de indiferencia
plt.contour(X, Y, Z, levels=np.linspace(Z.min(), Z.max(), 10), cmap='viridis', linestyles='dashed')

# Marcar las cestas de consumo propuestas
x_cestas = [3, 1, 2, 4, 2]
y_cestas = [2, 4, 3, 1, 2]
plt.scatter(x_cestas, y_cestas, color='red', label='Cestas de Consumo')

# Etiquetas y título
plt.xlabel('Hamburguesas (x)')
plt.ylabel('Pizzas (y)')
plt.title('Curva de Indiferencia y Cestas de Consumo')

# Leyenda
plt.legend()

# Mostrar el gráfico
plt.show()
