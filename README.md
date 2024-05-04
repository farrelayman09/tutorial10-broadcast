# Tutorial 10 Timer
Farrel Ayman Abisatyo  <br>
2206828916 <br>
Advanced Programming B <br>

## Reflection
### 1. Experiment 1.2: Understanding how it works.

<img src= "assets/images/Screen Shot 2024-05-04 at 18.43.05.png" width="750px"> <br>

First i ran two tabs, one being server and one being the client using ```cargo run --bin server``` 
and ```cargo run --bin client```. After, that i experimented by typing "hello!"  in the client side. It
is visible that after i entered in my message, the output is also shown in the server side.
After that I tried running a second client on another terminal window. Then i typed in "howdee!" in
the first client. After I pressed enter, the message is also show in the second the client side
indicating that clients can successfully chat with each other. The mechanism behind this is that the message will be sent to the server and 
the server will continue to forward it to all clients currently connected to it.  

### 2. “Experiment 2.2: Modifying port”

<img src= "assets/images/Screen Shot 2024-05-04 at 19.02.18.png" width="750px"> <br>
From the image above, it can be seen that the program can run just as well as 
before. This is because as long as the client and server agree on the same port to listen to,
it will run correctly. I do this by also altering the code that control the server's port to

```
let listener = TcpListener::bind("127.0.0.1:8080").await?;
    println!("listening on port 8080");
```
However if we only alter the client side's port and not the server's as well, the result in the image below will occur.


<img src= "assets/images/Screen Shot 2024-05-04 at 19.02.44.png" width="750px"> <br>
In this example, I only alter the client's port to 8080 while the server is still at 2000.
This can result in an unsuccessful network connection establishment because the target server of 2000 
is not currently accepting connections.

### 3. “Experiment 2.3: Small changes, add IP and Port”
<img src= "assets/images/Screen Shot 2024-05-04 at 19.30.48.png" width="750px"> <br>

It can be seen that I've modified the client's side to show my custom source message. I did this by
having a piece of code in the client.rs line 23 which is ```println!("Farrel's Computer - From server: {}", text);```
in place of the older println. This way, the terminal will show my string as the custom source message. I've also
added this code in server below line 24, which is ```bcast_tx.send(format!("{addr} : {text}"))?;```

The bcast_tx is a Sender part of a broadcast channel. The line bcast_tx.send(format!("{addr} : {text}"))?; 
sends a message to this broadcast channel.
The format!("{addr} : {text}") creates a formatted string that combines the client's address (addr) 
with the message content (text). 
This would then represent a message client sends to the server.



