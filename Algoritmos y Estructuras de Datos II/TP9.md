	# Ejercicio 1
**a.** Probabilidad de caer dentro del círculo.  
El área del círculo es πr2\pi r^2πr2, y el área del cuadrado es (2r)2=4r2(2r)^2 = 4r^2(2r)2=4r2.  
Por lo tanto, la probabilidad de caer dentro del círculo es:

P=Aˊrea del cıˊrculoAˊrea del cuadrado=πr24r2=π4.P = \frac{\text{Área del círculo}}{\text{Área del cuadrado}} = \frac{\pi r^2}{4r^2} = \frac{\pi}{4}.P=Aˊrea del cuadradoAˊrea del cıˊrculo​=4r2πr2​=4π​.

**b.** Tiro de nnn dardos, contando kkk en el círculo.  
La proporción kn\frac{k}{n}nk​ se aproxima a π4\frac{\pi}{4}4π​. Esto es útil para estimar π.

**c.** Algoritmo para estimar π\piπ:

1. Generar nnn pares de coordenadas (x,y)(x, y)(x,y) dentro del cuadrado [−r,r]×[−r,r][-r, r] \times [-r, r][−r,r]×[−r,r].
2. Verificar cuántos puntos caen dentro del círculo x2+y2≤r2x^2 + y^2 \leq r^2x2+y2≤r2.
3. Calcular π\piπ usando π≈4⋅kn\pi \approx 4 \cdot \frac{k}{n}π≈4⋅nk​.
![[Pasted image 20241118235250.png]]
```
import random

def estimar_pi(n):
    dentro_circulo = 0
    for _ in range(n):
        x = random.uniform(-1, 1)
        y = random.uniform(-1, 1)
        if x**2 + y**2 <= 1:
            dentro_circulo += 1
    return 4 * (dentro_circulo / n)

# Ejemplo de prueba
n = 100000
pi_estimado = estimar_pi(n)
print(f"Estimación de π con {n} puntos: {pi_estimado}")

```

---
# Ejercicio 2
**a.** Algoritmo `ComparaciónAleatoria`:
```
import random

def comparacion_aleatoria(arr1, arr2, iteraciones):
    n = len(arr1)
    if n != len(arr2):
        return False

    for _ in range(iteraciones):
        indice = random.randint(0, n - 1)
        if arr1[indice] != arr2[indice]:
            return False
    return True

```

**b.** Categorías de algoritmos probabilistas:

- **i.** Si se generan n\sqrt{n}n​ índices sin repetición, el algoritmo es **Monte Carlo**, ya que existe una probabilidad no nula de error en la respuesta.
- **ii.** Si se generan nnn índices con repetición, sigue siendo **Monte Carlo** por la probabilidad de error.
- **iii.** Si se generan nnn índices sin repetición, es **Las Vegas**, ya que garantiza una comparación exhaustiva cuando termina.
![[Pasted image 20241118235432.png]]
# Ejercicio 3
**a.** Algoritmo para calcular ϕ\phiϕ (MTTF):

1. Generar nnn simulaciones, donde en cada simulación:
    - Sortear el tiempo de vida de cada panel Ti∼U[1000,5000]T_i \sim U[1000, 5000]Ti​∼U[1000,5000].
    - Ordenar los tiempos y tomar el tercero menor (cuando fallan al menos 3 paneles).
2. Calcular ϕ\phiϕ como el promedio de estos tiempos críticos.
![[Pasted image 20241118235506.png]]

```
import random

def calcular_mttf(n):
    tiempos_falla = []
    for _ in range(n):
        paneles = [random.uniform(1000, 5000) for _ in range(5)]
        paneles.sort()
        tiempos_falla.append(paneles[2])  # Fallan al menos 3 paneles
    return sum(tiempos_falla) / n

# Ejemplo de prueba
n = 100000
mttf_estimado = calcular_mttf(n)
print(f"MTTF estimado con {n} simulaciones: {mttf_estimado} horas")

```