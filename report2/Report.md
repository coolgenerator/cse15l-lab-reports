# Lab Report 2 - Servers and SSH Keys (Week 3)
## Part 1
### Code
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> stringList = new ArrayList<>();

    String convertListToString(ArrayList<String> list){
        // Convert List to string in the format of "1. Hello"
        String res;
        for(int i = 1; i <= list.length; ++i)
            res += i + ". " + list(i-1) + "\n";
        return res;
    }

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return convertListToString(this.stringList);
        } else if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")){
                stringList.add(parameters[1].toString);
            }
            
            return convertListToString(this.stringList);
        } else {
            return "404 Not Found!";
        }
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
### Result
![Image](message_2.png)
It calls `main(String[])` function, then `handleRequest(URL)` method is called, and then `convertListToString(ArrayList<String>)`.

Arguments, values and changes:

`handleRequest(URI)`

+ Argument: url
+ Value: `new URI("https://127.0.0.1:4000/add-message?s=How%20are%20you")`
+ Change(s): 

`convertListToString(ArrayList<String>)`

+ Argument: list
+ Value: `["Hello", "How are you"]`

![Image](message_4.png)
It calls `main(String[])` function, then `handleRequest(URL)` method is called, and then `convertListToString(ArrayList<String>)`.

The request url `https://127.0.0.1:4000/add-message?s=http://google.com` is passed to `handleRequest()` method. And the Arraylist `["Hello", "How are you", "666", "http://google.com"]` is passed to `convertListToString()` method.

## Part 2

## Part 3
