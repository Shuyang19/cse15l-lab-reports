# Lab Report 2
## Part 1
The code for my SearchEngine:
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList; 

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> str = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Number: %d", num);
        } else if (url.getPath().equals("/increment")) {
            num += 1;
            return String.format("Number incremented!");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("count")) {
                    num += Integer.parseInt(parameters[1]);
                    return String.format("Number increased by %s! It's now %d", parameters[1], num);
                }
                else if (parameters[0].equals("s")) 
                {
                    str.add(parameters[1]);
                    return String.format("String added");
   
                }
            }
            else if (url.getPath().contains("search")) 
                {
                    String strlist = "";
                    String[] parameters = url.getQuery().split("=");
                    if (parameters[0].equals("s"))
                    {
                        for (int i = 0; i < str.size(); i++)
                        {
                        if (str.get(i).contains(parameters[1]))
                        {

                            strlist = strlist + str.get(i) + "; ";
                        }
                        
                        }
                        return strlist;
                        
                    } 
                
                }
            return "404 Not Found!";
        }
    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
-Below are the screenshots of the URL in the browser and the page's response:
add:

![Image](2.1.png)

This one I call the ```handleRequest(URI url)```method in the code, created a new stringlist str; and under the situation ```url.getPath().contains("/add")```, it satisfied 
```
else if (parameters[0].equals("s")) 
{
    str.add(parameters[1]);
    return String.format("String added");
}

```
-so that the word "pineapple" are now in the str list by using the add() method, and the page will tell you that "String added". I also added "apple" and "banana".
Query:

![Image](2.2.png)
![Image](2.3.png)
![Image](2.4.png)

-Above are the screenshots of search, with different querys ```s=app; s = na; s = a``` separately. 
-This one is also call the method ```handleRequest(URI url)```, and satisfy the if statemetn: ```else if (url.getPath().contains("search"))```;
```
{
    String strlist = "";
    String[] parameters = url.getQuery().split("=");
    if (parameters[0].equals("s"))
    {
        for (int i = 0; i < str.size(); i++)
        {
            if (str.get(i).contains(parameters[1]))
            {
                strlist = strlist + str.get(i) + "; ";
            }
                        
        }
        return strlist;
                        
    } 
                
}
 ```
-It will create a new empty string strlist, and finding out whether the elements in the str stringlist (which are we added previously) contains the string after "=" in the URL(which is the word we search for). Every element contains the searching word will be added to the strlist String with a semicolon, and finally it will dispaly the strlist, which contains all the elements satisfying our searching.
