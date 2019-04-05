# Tarea-03
3 Herencia.

## 1.  Define: Clase Base, Clase Derivada.
### Clase Base
Una clase base es aquella que no dependen ninguno de sus atributos u objetos de la clase de alguna otra clase, se podría decir que en términos de herencia, seria la clase padre, la clase que se mantiene fija, en el aspecto de herencia.
Es también por así llamarlo la clase principal de un programa, seria la clase primaria sin incluir la clase main en donde se corre todo el programa en si.
Las clases pueden heredar de otra clase. Para conseguir esto, se coloca un signo de dos puntos después del nombre de la clase al declarar la clase y se denomina la clase de la cual se hereda (la clase base) después del signo de dos puntos, del modo siguiente:

```csharp
public class A
{
    public A() { }
}
 
public class B : A
{
    public B() { }
}
```

### Clase Derivada
Son clases que dependen de las clases bases, ya que algunos de sus métodos son también heredados, y muchas veces, el compilador arrojara  malos resultados, ya que al ser dependientes estas clases, a veces podrán generar errores lógicos.

![alt text](http://3.bp.blogspot.com/-846HSVPHRT8/V2IhLkIQmRI/AAAAAAAABeA/VgM9jUDJRv0uR_dx_DpU5QyGaJUYoQVZQCK4B/s1600/1.png)

Como ya habia mencionado anteriormente la clase base es también conocida como la clase padre de la cual se van a heredar algunas propiedades.

![alt text](http://www.sc.ehu.es/sbweb/fisica/cursoJava/fundamentos/herencia/herencia1.gif)

En esta la clase base es Figura, la cual es la clase principal y las clases son algunas figuras en especifico las cuales heredaran de ella.
## 2.  Haz un diagrama UML donde se muestre la relación de herencia entre las  clases Figura, Recangulo y Circulo como vimos en clase.
![alt text](file:///C:/Users/salaz/Downloads/UML.jpeg)

## 3. Indica cuales son las clases base y las derivadas.
Como ya habia mos mencionado anteriormente la clase base es la clase de la cual se hereda, esta muchas veces es conocida como clase "padre" y sus hijas o hijos son las clases que derivan de él, en este caso "clases derivadas".
La clase base es "Figura" y sus clases derivadas son "Circulo" y "Rectangulo". 

Claro que al definir la clase base como figura sabemos que puede ser cualquier otra figura también asi como rombo, elipce, triangulo, pentágono, etc. 

## 4. ¿Que es herencia simple y herencia múltiple? ¿En c# se puede hacer herencia múltiple?
Antes de definir lo que es una herencia simple y una múltiple vamos a definir el concepto de lo que es una herencia en general.
**Herencia** Es una propiedad que permite que los objetos sean creados a partir de otros ya existentes, obteniendo características (métodos y atributos) similares a los ya existentes. Es la relación entre una clase general y otra clase mas especifica. Es un mecanismo que nos permite crear clases derivadas a partir de clase base, Nos permite compartir automáticamente métodos y datos entre clases subclases y objetos.

Por ejemplo: Si declaramos una clase párrafo derivada de un clase texto todos los métodos y variables asociadas con la clase texto son automáticamente heredados por la subclase párrafo.

### Herencia simple
Herencia simple, esta es la herencia más útil y típica., la que se puede encontrar en cualquier lenguaje moderno como Java o C#. La herencia simple, consiste en que una clase puede heredar la implementación de una sola clase base. 

La herencia simple consiste en cuando una clase, hereda a una clase hijo, y a solo una le hereda sus atributos, es igual al concepto general de herencia, con la limitante de solo poder heredar de una clase padre a una clase hijo, y solo a una clase hijo.

### Herencia múltiple 
Consiste en la utilización de las propiedades de una clase a varias clases mas, lo que significa que en esta propiedad una sola clase padre puede heredarle atributos, u objetos de esta a varias clases hijo sin ninguna limitación entre ellas.

![alt text](https://www.glosarioit.com/GloImg/Herencia.PNG)

En la herencia múltiple aparecen ambigüedades, como en el ejemplo de encima: si la clase Músico heredaba de Persona y Trabajador, y la clase Trabajador heredaba de Persona. Existirían las siguientes reglas:
```csharp
MusicoEstudiante : Persona, Músico, Trabajador
```
```csharp
Músico : Persona, Trabajador
```
```csharp
Trabajador: Persona
```
Si un compilador está mirando la clase MusicoEstudiante necesita saber si debe juntar las características iguales o si deben estar separadas. Por ejemplo, tendría sentido unir las características "Edad" de Persona para MusicoEstudiante. La edad de una persona no cambia si le consideras una Persona, un Trabajador o un Músico. Sin embargo, tendría sentido separar la característica "Nombre" de Persona y Músico si los músicos usan un nombre artístico diferente de su nombre real. Las opciones de juntar y separar son válidas según el contexto, y sólo el programador sabe qué opción es correcta para la clase que está diseñando.

***Cada lenguaje de programación trata estos problemas de herencia repetida de diferente forma:***

**1. C++** requiere que el programador establezca de qué clase padre vendrá la característica a usar. Por ejemplo con "Trabajador::Persona.Edad". C++ no soporta herencia repetida explícita porque no habría forma de indicar qué superclase usar.
CLOS permite al programador control total del método de combinación, y si no es suficiente, el protocolo de metaobjetos ofrece al programador formas de modificar la herencia, envío de métodos, instanciación de clases, y otros mecanismos internos sin afectar a la estabilidad del sistema.

**2. Eiffel** permite al programador explicitar si junta o separa características que son heredadas de superclases. Eiffel juntará características automáticamente si tienen el mismo nombre e implementación. El programador tiene la opción de renombrar las características para separarlas. Eiffel también permite explicitar herencia repetida como A: B, B.

**3. Logtalk** soporta tanto interfaces como multi-herencia de implementación, permitiendo declarar alias de métodos que ofrecen renombrar y acceder a métodos que quedarían ocultados por el mecanismo de resolución de conflictos convencional.

**4. Perl** usa la lista de clases para heredar de una lista ordenada. El compilador usa el primer método que encuentra mediante búsqueda en profundidad por la lista de superclases.

Un punto importante es que en C# no se permite realizar herencia múltiple, al principio puede sonar una desventaja pero es importante mencionar que gracias a ello no hay ambiguedad y permite a las clases implementar múltiples interfaces.



## 5. Escribe el programa de Figura como vimos en clase, donde agregues varios tipos de figuras a una lista y recorre la lista llamando a un metodo de las figuras, además :

            5.1 Se sobrecarguen los constructores y se acceda a los constructores de la clase base 

            5.2 Explica para que nos sirve la palabra base

           5.3  Haz el método Dibuja() que sea virtual y redefinelo en solo una de las clases derivadas.  
           
```csharp

using System;
using System.Collections.Generic;

namespace tarea2figuras
{
 class Vector2D
    {
        public int x, y;
        public Vector2D(int x, int y)
        {
            this.x=x; this.y=y;
        }
        public override string ToString()
        {
            return String.Format("{0},{1}", x, y);
        }
    }
    abstract class Figura
    {
        public Vector2D position;
        public string fill ,border;

        public Figura():this( new Vector2D(100, 100))
        {
        
        }
        
        public Figura(Vector2D pos)
        {
            position= pos;
            fill= "white";
            border= "black";
        }

        public abstract void Dibuja();
    }

    class Circulo : Figura
    {
     private int radio;
     public Circulo(Vector2D pos, int radio):base(pos)
     {
         this.radio= radio;
     }
     public Circulo():base()
     {
         this.radio= 10;
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un circulo en {0} de color {1}", position, fill);
     }
    }
 
    class Rectangulo : Figura
    {
     
     public Rectangulo(Vector2D pos):base(pos)
     {
         
     }
     public Rectangulo ():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un rectangulo en {0} de color {1}", position, fill);
     }
    }

    class Cuadrado : Figura
    {
     
     public Cuadrado(Vector2D pos):base(pos)
     {
         
     }
     public Cuadrado ():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un cuadrado en {0} de color {1}", position, fill);
     }
    }

     class Triangulo : Figura
    {
     
     public Triangulo(Vector2D pos):base(pos)
     {
         
     }
     public Triangulo ():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un triángulo en {0} de color {1}", position, fill);
     }
    }

     class Rombo : Figura
    {
     
     public Rombo(Vector2D pos):base(pos)
     {
         
     }
     public Rombo ():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un rombo en {0} de color {1}", position, fill);
     }
    }


     class Elipse : Figura
    {
     
     public Elipse(Vector2D pos):base(pos)
     {
         
     }
     public Elipse ():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un elipse en {0} de color {1}", position, fill);
     }
    }

     class Pentagono : Figura
    {
     
     public Pentagono(Vector2D pos):base(pos)
     {
         
     }
     public Pentagono ():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un pentágono en {0} de color {1}", position, fill);
     }
    }


     class Hexagono : Figura
    {
     
     public Hexagono(Vector2D pos):base(pos)
     {
         
     }
     public Hexagono():base()
     {
        
     }

     public virtual void Dibuja() 
     {
         Console.WriteLine("Se dibuja un hexágono en {0} de color {1}", position, fill);
     }
    }
    class Program
    {
        static void Main(string[] args)
        {
            List<Figura> figuras= new List<Figura>();
            figuras.Add(new Circulo());
            figuras.Add(new Rectangulo(new Vector2D(200,200)));
            figuras.Add(new Cuadrado(new Vector2D(300,300)));
            figuras.Add(new Triangulo(new Vector2D(400, 400)));
            figuras.Add(new Rombo(new Vector2D(500,500)));
            figuras.Add(new Elipse(new Vector2D(600,600)));
            figuras.Add(new Pentagono(new Vector2D(700,700)));
            figuras.Add(new Hexagono(new Vector2D(800,800)));
            
            foreach(Figura f in figuras)
             f.Dibuja();        
        }
    }
}
```
  ##  Implementación de base
  La palabra :base explicado de manera resumida es aquella que llama a la clase principal o también conocida como clase padre, para que de esta manera pueda dar un estado inicial a los objetos.
  
  ![alt text](http://2.bp.blogspot.com/-dijqSc9D2AE/UhFf-wgOhXI/AAAAAAAAADc/wv01wowYyIo/s1600/H3.jpg)
  
La palabra clave base se utiliza para obtener acceso a los miembros de la clase base desde una clase derivada:

- Realice una llamada a un método de la clase base reemplazada por otro método.

- Especifique a qué constructor de la clase base se debe llamar para crear instancias de la clase derivada.

  
  
