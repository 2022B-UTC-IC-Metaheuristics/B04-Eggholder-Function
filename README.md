# B04-Eggholder-Function

La función Eggholder tiene un paisaje engañoso y es una función extremadamente difícil de optimizar debido a la gran cantidad de mínimos locales. Esto es porque se caracteriza por un plano desigual con varias docenas de mínimos locales que fácilmente engaña a los agentes de búsqueda.


![Grafo de ejemplo](eggholder.png)

## Definición Matemática 

$$f\left(x\right) = -\left(x_2+47\right)\ sin\left(\sqrt{\|x_2 + \frac{x_1}{2} + 47\|}\right)-x_1\ sin\left(\sqrt{\|x_1-\left(x_2+47\right)\|}\right)$$


## Definición de la función objetivo en python y ejemplo
precision = 0.001
rango_entero = 512
bits_enteros, bits_decimales = calcular_bits(rango_entero, precision)

def egg_holder(solution,bits_enteros, bits_decimales,precision):
    variables = decodificar_solución(solution,bits_enteros,bits_decimales,precision)
    x , y = variables[0], variables[1]
    return -(y + 47) * sin(sqrt(abs(x/2 + (y + 47)))) - x * sin(sqrt(abs(x - (y + 47))))

fn = functools.partial(egg_holder,bits_enteros = bits_enteros, bits_decimales = bits_decimales, precision=precision)

##Tip
Utiliza el archivo utils.py para poder probrarlo, ya que necesita algunas funciones como la de decodificar arreglo, calcular bits y convertir a binario.

## Dominio de Entrada

La funcion tiene una codificación binaria.

La función generalmente se evalúa en el cuadrado
$$x_i\in[-512,512],\ para\ cada\ i=1,2$$

## Ejemplos de soluciones iniciales
(x, y) = (512, 404.2319)

(x, y) = (-465.2287, 394.2319)

(x, y) = (100, -100)

## Mínimo Global

$$f\left(x^*\right)=-959.6407,\ donde\ x^\* = \left(512,404.2319\right)$$

## Características

La función es continua.

La función es no convexa.

La función se define en el espacio de 2 dimensiones.

La función es multimodal.

La función es diferenciable.

La función no es separable.

La función no es aleatoria.

La función no es paramétrica.

## Más Información

[EggHolder Function](https://www.sfu.ca/~ssurjano/egg.html)
