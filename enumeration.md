# Interface Enumeration
### java.util.enumeration

### Ana Lizbeth Hernández López, Beatriz Guadalupe Hernández Rodríguez, Jesus Alfredo Andrio Rodríguez y Rebeca Gonzalez Batista
 --------
 --------

  
 Enumeration es un interfaz simple que define los métodos por los cuales puede enumerar (obtener uno a la vez) los elementos en una colección de objetos. Permite enumerar todos los elementos de cualquier conjunto de objetos. 
 
Aunque esta interfaz no está en desuso, la enumeración se considera obsoleta para el nuevo código ya que ha sido reemplazada por otras interfaces como Iterator. Sin embargo algunos métodos definidos por clases heredadas hacen uso de esta interfaz, como Vector y Propiedades, se usa por varias otras clases de API y actualmente se usa ampliamente en el código de la aplicación.

Los métodos declarados por java.util.enumeration son:

  Método | Desrcipción
------------- | -------------
boolean hasMoreElements() | Cuando se implementa, debe devolver verdadero mientras todavía hay más elementos para extraer, y falso cuando se han enumerado todos los elementos.
Object nextElement()  | Devuelve una referencia a objeto genérica, cuyo tipo hay que convertir al tipo de clase de la cual el objeto es una instancia.



----

 
 
 ## Ejemplo 1
```javasfx
import java.util.Enumeration;
import java.util.Vector;

public class Main {
    public static void main(String args[]) {
        Enumeration days;
        Vector dayNames = new Vector();

        dayNames.add("Sunday");
        dayNames.add("Monday");
        dayNames.add("Tuesday");
        dayNames.add("Wednesday");
        dayNames.add("Thursday");
        dayNames.add("Friday");
        dayNames.add("Saturday");
        days = dayNames.elements();

        while (days.hasMoreElements()) {
            System.out.println(days.nextElement());
        }
    }
}

```
-----

## Ejemplo 2

```javasfx
  public String[] getGenericRules(Vector<YassSong> data) {
        Vector<String> langs = new Vector<>();
        for (Enumeration<?> e = data.elements(); e.hasMoreElements(); ) {
            YassSong s = (YassSong) e.nextElement();
            String lang = s.getLanguage();
            if (lang == null || lang.length() < 1) {
                continue;
            }
            if (!langs.contains(lang)) {
                langs.addElement(lang);

            }
        }
        Collections.sort(langs);

        return langs.toArray(new String[langs.size()]);
    }
```
