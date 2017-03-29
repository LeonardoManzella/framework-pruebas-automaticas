## Framework para Pruebas Automáticas
Tecnologías Utilizadas: `Lenguaje Ruby`, `Ruby on Rails`, `Self-Modification`, `Reflection`
Sin Bases de Datos

Permite hacer pruebas sobre aplicaciones para probar que anden correctamente y no contengan fallos.
Se ejecuta a demanda y borra todo rastro de su ejecución al terminar.


### Diagrama de la Arquitectura
![alt text](https://raw.githubusercontent.com/LeonardoManzella/framework-pruebas-automaticas/master/Diagrama%20Clases.png "
Diagrama de la Arquitectura")

Para mas Proyectos, por favor ver mi LinkedIn: https://www.linkedin.com/in/leonardo-manzella-argentina


### Aserciones
Permite realizar aserciones directamente sobre todos los objetos sin ninguna preparación previa.

Ejemplos:
```ruby
erwin. edad. deberia ser mayor_a  18
7.deberia ser  7 
true. deberia ser  false                   # falla, obvio
leandro. edad. deberia ser 19
leandro. edad. deberia ser uno_de_estos  [ 7, 22, "hola"]
```

### Aserciones con Métodos Externos
Pueden utilizarse no solamente métodos del FrameWork sino también métodos propios de las clases y objetos del usuario.

Ejemplo:
```ruby
class Persona
   def viejo?
     @edad > 45
   end
End

leandro. deberia tener_edad  22 
leandro. deberia tener_edad mayor_a  20
leandro. deberia tener_edad uno_de_estos  [ 7, 22, "hola"]
nico. deberia ser_viejo
```

### Suites de Testing
Detecta automáticamente los tests y las clases que son suites de testing o no, mediante convencion de nombres o por especificar al ejecutar tests.

Permite:
1. Correr un test específico de una suite
1. Correr una suite de tests  en particular
1. Correr todas las suites  que se hayan importado al contexto

### Mocking
Poder reemplazar (de forma temporal) la implementación de un método de cualquier clase por una sección de código que resulte más conveniente en el momento, muy útil en pruebas que incluyan llamadas a bases de datos o métodos sin implementar aun.

### Spying
Espiar un objeto permite modificar su comportamiento durante los tests pero, en lugar de reemplazar la lógica que el método ejecuta, se mantiene la lógica original agregando además la capacidad de analizar a posteriormente las interacciones con el objeto durante la ejecución del test
