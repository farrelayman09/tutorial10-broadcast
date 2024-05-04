# Tutorial 10 Timer
Farrel Ayman Abisatyo  <br>
2206828916 <br>
Advanced Programming B <br>

## Reflection
### 1. Experiment 1.2: Understanding how it works.

<img src= "assets/images/Screen Shot 2024-05-04 at 18.43.05.png" width="600px"> <br>

First i ran two tabs, one being server and one being the client using ```cargo run --bin server``` 
and ```cargo run --bin client```. After, that i experimented by typing "hello!"  in the client side. It
is visible that after i entered in my message, the output is also shown in the server side.
After that I tried running a second client on another terminal window. Then i typed in "howdee!" in
the first client. After I pressed enter, the message is also show in the second the client side
indicating that clients can successfully chat with each other. The mechanism behind this is that the message will be sent to the server and 
the server will continue to forward it to all clients currently connected to it.  
