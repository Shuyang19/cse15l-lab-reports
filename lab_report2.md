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
I simpliy copy paste the original code from NumberServer and add my own code.
In the "/add" situation, the original code is 
```
if (parameters[0].equals("count")) {
                    num += Integer.parseInt(parameters[1]);
                    return String.format("Number increased by %s! It's now %d", parameters[1], num);
                }
```
