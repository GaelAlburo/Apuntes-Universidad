Links:
___
A todos los elementos que conforman una escena se les pueda aplicar transformaciones

$P' = P_{proj}*V*M*P \rightarrow$ Representación de una proyección final. Se hace en el GPU
$M \rightarrow \text{Matrices de 4X4}.$ Matriz Modelo. Se genera con GLM
$V \rightarrow$ Matriz Vista
$P_{roj} \rightarrow$ Matriz Proyeccion
 $P \rightarrow [x \space y \space z \space w=1]$  . Se declara don la estructura `Vertex` del programa en OpenGL

$M \rightarrow$ Mt, Me, Mr: Traslacion, Escala, Rotacion

Se usaran las proyecciones en perspectiva y ortogonal
- Ortogonal: Sirve para conocer bien las dimensiones del objeto
- Perspectiva: Vida real, los objetos mas lejanos se ven mas pequeños, los mas cercanos mas grandes. Permite conocer la profundidad del objeto


Con `glm` se creara la matriz modelo con las sig. instrucciones:
- `M=glm::mat(1.0);` - Genera la matriz 4x4 identidad. Permitira inicializar las operaciones con matrices
- `M=glm::translate(M, [traslaciones]`
- `M=glm::rotate(M,[angulo y eje de rotacion])`
- `M=glm::scale(M,[valor])`. Si se da un valor de 1, se tiene su tamano original. Con 3 al triple. Con 0.5 disminuye su tamano al 50%

Para generar la matriz vista se usara la funcion `V=glm::lookAt(posicion,direccion,orientacion)`

Para obtener la matriz de proyeccion:
- `P=glm::ortho()`
- `P=glm::perspective()`

___
En `update()` se aplican las matrices de transformacion

`ortho(cuanto -x, cuanto x, cuanto -y, cuanto y, campo cercano, campo lejano)`
`perspective(campo de vision, relacion de aspecto, campo cercano, campo lejano)`
- El primer valor es de 45 grados, internamente se multiplica por dos, para generar 90 grados, igual que la vista humana
- Aumentando el campo de vision se ven mas objetos

____
# Actividades
2.
Se deben modificar los valores de la posicion de la camara y el vector de vista (primer y segundo vector)

para vista superior, el vector up (tercer vector), es de x positiva. el de vista es y negativo

3 y 4. se comentan las lineas de ortho y perspective

7 se debe cambiar la matriz de escala