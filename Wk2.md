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


Here are some examples of adding a string to the server.



![image](https://user-images.githubusercontent.com/98483167/215677843-510df28b-83b8-486f-8a08-1e8c1b2eb623.png)

This screenshot shows a user entering "Hello" into the server, and the webpage displaying it as so. It first calls the handleRequest(URI url) method with the given url. IT fids that the url contains /add, so it takes the parameters of the url and adds the string to the ArrayList strings.After it adds the string, the server calls displayString(), which outputs all the strings in the ArrayList.

None of the values in the URL gets changed, only the ArrayList is appended.

If nothing is added to the URL, only displayStrings() is called.

![image](https://user-images.githubusercontent.com/98483167/215681015-e51d587b-7624-47f9-ace3-465cd77047dc.png)

This is an instance of a user adding "How are you" to the server, after "Hello" has been added. As you can see, Hello remains on the webpage, and How are you is printed after. This is because the ArrayList is only appended, and not reinitialized.


