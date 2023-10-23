# Lab Report 2

## Part 1
Code
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int count = 0;

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].contains("s"))
            {
                count++;
                return (count + "." + parameters[1] + "\n");
            }
            return "404";
        }
        else return "Not Found!";
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

### Screenshot:
1) With "/add-message?s=Hello"
<img width="951" alt="Screenshot 2023-10-22 at 8 49 01 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/62367567-6b15-4167-b0ca-1df2f3d0c096">


> * The "handleRequest" is the called method.
> * The "URI url" is the argument that is related to the field. The "count" is the values of the relevant fields of the class.  
> * The "count" was "0" after initialization and it changed to "1" when the first element of the split contain "s"

2) With a path to a directory as an argument
   
<img width="939" alt="Screenshot 2023-10-22 at 8 50 47 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/b14f9ced-e01d-4382-a167-f07a5fb1f1a6">


> * The "handleRequest" is the called method.  
> *  The "URI url" is the argument that is related to the field. The "count" is the values of the relevant fields of the class.  
> * "The 'count' was '1' before the operation, and it changed to '2' when the first element of the split of the added string contained 's'

       
## Part 2

<img width="448" alt="Screenshot 2023-10-22 at 10 34 53 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/3849be54-ba4c-4ecc-b9f7-e8401e94cf30">

<img width="770" alt="Screenshot 2023-10-22 at 10 31 36 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/eb5ab178-f534-4f58-adf0-1fb481e6b593">

<img width="1362" alt="Screenshot 2023-10-22 at 10 45 01 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/b4e9d0ec-4b2c-46e3-b626-9afec9fdaf01">


## Part 3

In Week 2 and 3 of the lab, I learned how to set up and run a web server on my own computer. I learned how to generate SSH keys and set up passwordless access to a remote server, which can save time and improve security. This involved using commands like "ssh-keygen", "mkdir", and "scp". 
