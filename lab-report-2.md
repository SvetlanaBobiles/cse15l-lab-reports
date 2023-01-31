# CSE 15L Lab Report 2

**Code:**

import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String message = "";

    public String handleRequest(URI url) 
    {
        if(url.getPath().contains("/add-message"))
        {
            String[] arr = url.getQuery().split("=");
            if(arr[0].equals("s"))
            {
                message += arr[1] + "\n";
            }
        }

        return message;
    }
}


public class StringServer
{
    public static void main(String[] args) throws IOException 
    {
        if(args.length == 0)
        {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}


