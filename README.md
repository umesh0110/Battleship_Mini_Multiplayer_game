# Battleship_Mini_Multiplayer_game
Multiplayer game using networking concepts and open graphics libraries

With respect to sockets:

Both the Server and Client functions were combined into a single Dialog Based program. With this design, connecting two running copies of the same program is made possible and the users don’t need two separate programs (Server and Client) for this game application. To this program sound features, bitmaps, icons can be added to make this application attractive. To implement this feature a web browser control will be better. 

In openGL: Header files used: GL/glut.h 

In socket programming: Header files used:   sys/socket.h , netinet/in.h 

User defined function:

Header files: 
 Backbone.hpp, Mix.hpp , Crypto.hpp 
 
 Algorithm for the program: 
 1. Get the user to place the ships in the grid on the right hand side. 
 2. Run the client program.
 3. If server is not found, then become the server. Else stay as the client.
 4. Take user input for the opponent’s ip address.
 5. Run the program using variable called turn. 
 6. turn=0 --sender turn=1 --reciever 
 7. server:: sending ::0ptoxNyN1 client answer ::0otpxNyN1 or 0otpxNyN2 recieve :: 1otpxNyN1 //after recieving change turn to 1 
 8. client:: sending ::1otpxNyN1 server answer ::1ptoxNyN1 or 1ptoxNyN2 recieve :: 0ptoxNyN1 //after sender ack change turn to 0 
 9. before sending or receiving the message encrypt and decrypt the message. 
 10. after about 15 steps continuously start checking if any player has won.
 If yes then screen displays win in the user screen and loose on the opponent screen
 
 
Limitations: For the socket programming: 
1. Only one port number is allowed for communication between the server and the client. So if the server program runs on a system which already uses that particular port number then the program may crash. 
2. The user should have knowledge of his/her system’s IPV4 address else the connection cannot be established.
3. The server program cannot end unless it finds a client. So if one player is ready to play but his opponent decides not to open the application then the first users program will crash. 
4. The program depends immensely on timing. It the client acknowledgement or the server acknowledgement is slow then the program may appear to be in a temporary deadlock. 

It works properly only on linux systems and executable file runs only on linux systems.

openGL library should definately be installed to run the project.

the projects runns natively on the same system i.e. "127.0.0.1", to change the ip address edit the file mix.hpp

in mix.hpp look for the comment "change ip address here" and change the ip address in the function below it into the ip address of the server/other system.
