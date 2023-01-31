# Lab Report 2 - Servers and Bugs (Week 3)
## Part 1

This lab was to create a web server called StringServer that keeps track of strings added to the server.

Here's the code for the server

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> strings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            
            return displayStrings();
        }else{
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    strings.add(parameters[1]);
                    return displayStrings();
                }
            }
            return "404 Not Found!";
        }
    }

    String displayStrings(){
        String s = "";

        for (String string : strings) {
            s += string + "\n";
        }

        return s;
    }

    /*
     * 
     */

    String getListofString(ArrayList<String> strings){
        String s = "";
        for (String string : strings) {
                if(s.equals(""))
                    s += string;
                else{
                    s += ", " + string;
                }
        }

        return s;
    }
}




class StringServer {
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

![image](https://user-images.githubusercontent.com/98483167/215677843-510df28b-83b8-486f-8a08-1e8c1b2eb623.png)

This screenshot shows a user entering "Hello" into the server, and the webpage displaying it as so. 
