### Task 7kyu:

In a small town the population is p0 = 1000 at the beginning of a year. 
The population regularly increases by 2 percent per year and moreover 50 new inhabitants per year come to live in the town. 
How many years does the town need to see its population greater or equal to p = 1200 inhabitants?

[Task link](https://www.codewars.com/kata/563b662a59afc2b5120000c6/java)

#### Solution:
```
public class Arge {
    public static int nbYear(int p0, double percent, int aug, int p) {
        int years = 0;
        while (p0 < p) {
            p0 += p0 * percent / 100 + aug;
            years++;
        }
        return years;
    }
}
```

#### Fav solution:
```
class Arge {
    static int nbYear(int p0, double percent, int aug, int p) {
        Double next = p0 + (p0 * percent / 100) + aug;
        return (next >= p)
         ? 1
         : 1 + nbYear(next.intValue(), percent, aug, p);
    }
}
```

#### Comment:
There were no interesting decisions, everyone had the same thing.


### Task 7kyu:

Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. 
The string can contain any char.

[Task link](https://www.codewars.com/kata/55908aad6620c066bc00002a/train/haskell)

#### Solution:
```
 public class XO {
    public static boolean getXO (String str) {
        int strn = str.length();
        int ocount = 0;
        int xcount = 0;
        str = str.toUpperCase();
        for (int i=0; i < strn; i++){
            if(str.charAt(i) == 'O') {
                ocount++;
            }
            if(str.charAt(i) == 'X'){
                xcount++;
            }
        }
        if (ocount == xcount){
            return true;
        }
        else {return false;}
    }
}
```

#### Fav solution:
```
public class XO {

    public static boolean getXO (String str) {

        return str.toLowerCase().replace("o","").length() ==
                str.toLowerCase().replace("x","").length();

    }
}
```

#### Comment:

They use their ready-made functions, but do not count themselves.
