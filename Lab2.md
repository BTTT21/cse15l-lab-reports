# Lab Report 2

**Part1:**
```
# code for StringServer
import java.io.IOException;
import java.net.URI;
import java.util.*;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    List<String> str = new ArrayList<>();

    public String handleRequest(URI url) 
    {
        if (url.getPath().contains("/add-message")) 
        {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) 
            {
                str.add(parameters[1]);
                String ans = "";
                for(int i = 0; i < str.size(); i++)
                {
                    int j = i+1;
                    ans += Integer.toString(j);
                    ans += ": ";
                    ans += str.get(i);
                    ans += "\n";
                }
                return ans;
            }
        }
        return "404 Not Found!";
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
<img width="1274" alt="Screenshot 2023-10-17 at 11 40 53 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/01883310-1fc7-4ad2-8d5a-455a59a32a4a">

>The method called is handleRequest.  
>The relevant argument is URI url and the value of the argument is "localhost:9010/add-message?s=Hello". A relevent field of the class is str, which is initialed as an empty list.  
>The relevent field str changed its value by adding "Hello" to the list.

<img width="1270" alt="Screenshot 2023-10-17 at 11 41 15 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/3147f7b3-a54d-4248-bc6d-1d0fe8941f5b">

>The method called is handleRequest.  
>The relevant argument is URI url and the value of the argument is "localhost:9010/add-message?s=World". A relevent field of the class is str, and the value is "Hello" before handling the new url.  
>The relevent field str changed its value by adding "World" to the list. Now the list has length of two and two indices.

**Part2:**

><img width="503" alt="Screenshot 2023-10-17 at 8 16 41 PM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/eb757fb4-4dee-4953-95e3-3cc1d5a5e8d9">  
><img width="887" alt="Screenshot 2023-10-17 at 8 32 10 PM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/6b943199-265d-439f-a527-f464db50fcab">
><img width="790" alt="Screenshot 2023-10-17 at 8 28 28 PM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/0499125c-94ed-4d65-a128-0c954755aad4">
><img width="471" alt="Screenshot 2023-10-17 at 8 28 39 PM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/7f424d4e-2e4c-4c05-9147-d7c18832fa68">  


**Part3:**
>I think the new thing I learned in these two weeks is to create some simple servers. I created the simplest "SearchEnginee" and the "StringServer", which is quite interesting to see how they works.
