# Lab Report 2

## Part 1

Code
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class Handler implements URLHandler {
    int count = 0;
    StringBuilder response = new StringBuilder();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                count++;
                String message = count + ". " + parameters[1];
                response.append(message).append("\n");
                return response.toString();
            }
            return "404";
        } else {
            return "Not Found!";
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

### Screenshot:
1) With "/add-message?s=Hello"
<img width="951" alt="Screenshot 2023-10-22 at 8 49 01 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/62367567-6b15-4167-b0ca-1df2f3d0c096">


> * The "handleRequest" is the called method.
> * The "URI url" is the argument that is related to the field. The int "count", and StringBuilder "response" are the values of the relevant fields of the class.  
> * The "count" was "0" after initialization and it changed to "1" when the first element of the split contains "s"

2) With "/add-message?s=How are you"
   
<img width="1068" alt="Screenshot 2023-11-05 at 11 07 29 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/477a2d0b-b035-447f-8ef6-516e341a4e1f">



> * The "handleRequest" is the called method.  
> *  The "URI url" is the argument that is related to the field. The int "count", and StringBuilder "response" are the values of the relevant fields of the class.  
> * "The 'count' was '1' before the operation, and it changed to '2' when the first element of the split of the added string contained 's'

       
## Part 2

<img width="640" alt="Screenshot 2023-11-05 at 11 19 31 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/d5442b73-fe11-4049-a8b3-6f6bb1e4c54d">
> * The path to the private key for my SSH key for logging into ieng6 is `/home/.ssh/id_ed25519.pub`

<img width="876" alt="Screenshot 2023-11-05 at 11 27 37 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/a99b9bc0-d8c5-4f45-8300-a590a4e4e986">
> * The path to the public key for my SSH key for logging into ieng6 is `/home/linux/ieng6/cs15lfa23/cs15lfa23mt/.ssh/id_rsa.pub.`

<img width="1043" alt="Screenshot 2023-11-05 at 11 38 02 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/de91ee0e-2ad4-4eb8-ad47-a1cc0efa4cf6">
<img width="908" alt="Screenshot 2023-11-05 at 11 39 12 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/e08896f9-8fd4-4394-877f-fafa230a1670">



## Part 3

In Week 2 and 3 of the lab, I learned how to set up and run a web server on my own computer. I learned how to generate SSH keys and set up passwordless access to a remote server, which can save time and improve security. This involved using commands like `ssh-keygen`, `mkdir`, and `scp`. 
