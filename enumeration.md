# Interface Enumeration
### java.util.enumeration
 --------
 --------
 
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
------
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
