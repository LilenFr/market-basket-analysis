# Descripción del proyecto
Este es un pequeño proyecto de análisis del carrito de compra con el objetivo de descubrir qué combinaciones de productos se compran con más frecuencia en una tienda de cosmetibles.


<img src="https://cdn-icons-png.flaticon.com/512/3957/3957674.png" alt="drawing" width="250" align="right"/>

Requisitos:
+ El dataset 'Groceries_dataset.csv'. Descargar en el siguiente <a href="https://www.kaggle.com/datasets/heeraldedhia/groceries-dataset">link</a>.<br>
+ Las librerías Pandas y Mlxtend. Ver archivo 'requirements.txt'.
+ El algoritmo A priori para el análisis del carrito de compra.

### Conceptos:
-<strong>Análisis del carrito de compra:</strong><br>

¿Qué es?<br>
Es una aplicación de ciencia de datos en markenting que mejora la experiencia del usuario y fomenta las compras, lo que agrega valor comercial directo a las empresas.<br>
Es una técnica de aprendizaje automático no supervisada porque no entrena en un conjunto de datos ni predice un resultado. Lo que hace el algoritmo es identificar relaciones entre productos y combinaciones de productoss que se compran juntos con frecuencia.

¿Para qué sirve?<br>
Esta técnica sirve para identificar combinaciones de productos que se dan con frecuencia en las transacciones.

¿Cómo lo logra?<br>
Mediante el uso de un conjunto de reglas estadísticas. Comúnmente se utiliza el algoritmo A priori.

Ejemplo:<br>
Un supermercado en donde la fórmula para bebés y los pañales siempre se venden en el mismo pasillo. De manera similar, el shampoo con el acondicionador se colocan uno cerca del otro.<br>

Los restaurantes, las tiendas minoristas y las plataformas de e-commerce utilizan con frecuencia el análisis del carrito de compra para alentar a los clientes a realizar más compras en una sola visita. 

-<strong>Algoritmo A priori:</strong>

¿Qué es?<br>
Es la técnica más común para realizar análisis del carrito de compra.

Supongamos que la mayoria de clientes de una Tienda x han comprado leche, azúcar y galletitas juntos. Esto significa que leche, azucar y galletitas es un conjunto de productos frecuente, ya que aparece en la mayoria de las compras. Entonces, si una persona agarra leche y azucar, también se le recomendarán galletitas.

¿Por qué?<br>
Porque según el algoritmo A priori, un subconjunto del conjunto de productos frecuentes también es un subconjunto de productos frecuentes.<br>
Entonces, si:<br>
<strong>conjunto de pruductos frecuente</strong> = leche, azúcar y galletitas<br>
también:<br>
<strong>subconjunto de productos frecuente</strong> = leche y azúcar<br>
<strong>subconjunto de productos frecuente</strong> = leche y galletitas<br>
<strong>subconjunto de productos frecuente</strong> = azúcar y galletitas<br>
Debido a esto, si un cliente compra solo leche, también se le recomendará azúcar y galletitas.

Componentes del algoritmo A priori:<br>

+ Support:<br>
  Evalua la popularidad general de un producto determinado. Se calcula con la siguiente fórmula:

  <strong>Support(producto1) = Transacciones donde aparece el producto 1 / Transacciones totales</strong>

  Un valor alto como resultado significa que ese producto está presente en la mayoría de compras.

+ Confidence:<br>
  Evalua la probabilidad de diferentes combinaciones de compra. Se calcula con la siguiente fórmula:

  <strong>Confidence (producto1 -> producto2) = Transacciones donde aparece p1 y p2 juntos / Transacciones donde aparece p1</strong>

  El resultado muestra cuántos usuarios que compraron el producto1 también compraron el producto2.

+ Lift:<br>
  Evalua el aumento del ratio de la venta del producto1 cuando se vende el producto2. Se calcula usando la siguiente fórmula:

  <strong>Lift = Confidence (producto1 -> producto2) / Support(producto1)</strong>

  El resultado son las probabilidades de que los clientes compren el producto2 si vendo el producto1.

<strong>Support, conficence y lift básicamente son métricas que evalúan la relevancia y la popularidad de cada combinación de productos.</strong>

Dicho todo lo anterior, ir al <a href="./2-analysis.ipynb">jupyter de análisis</a> para ver el desarrollo del proyecto.
