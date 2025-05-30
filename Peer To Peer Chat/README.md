# Peer-to-Peer Chat

## About

This is a peer-to-peer chat messaging system which allows users to connect to eachother and chat. It includes features to connect to other users using their address and port, password protect rooms, and send files over the peer to peer network. It offers both a terminal interface and a html webpage interface.

## Dependencies

`pip install websockets`

If you plan to modify this code you will also need to install some sass to css compiler. I recommend the live-compiler sass extension for vscode.

## Running

Open two terminals and run the script with `python3 chat.py`. You will be asked if you want to use the frontend html interface or the terminal to run the program. If you do want to use the html interface, then indicate so by typing `y` in the terminal, and then open `index.html` in a browser of your choice. Please note that `index.html` uses the websockets library to communicate with the backend python script, and by default uses port `8765`. If you want to run using two frontend interfaces, this will have to be changed for one of the programs, so each program is running websockets on their own port.

## Features

### Connect

Connect to a user using the command `connect <address> <port>`. For example, if user2 is on localhost on port 51692, user1 would type `connect 127.0.0.1 51692`. Once connected, user1 and user2 can send messages to eachother.

### Upload a file

Upload a file so that other people can download it with `send <filepath>`. This will send a notification to everyone that you have uploaded a file. The file can be of any type. Large files are allowed and will be sent in chunks. Please note that in the frontend, when selecting a file to send from the file browser, it must be in the project directory.

### Download a file

Download a file with its file name (including any extension) `download <filename>`. If someone in the network has uploaded a file with that name, it will download with the name [datetime]_filename. The more downloads happen, the faster this is, since more peers become file hosts.

### Password protection

Users can password protect their rooms by typing `password <password>`. Users who then wish to join their room will have to enter this password.

## Video

This video shows both the terminal interface and the html frontend interface. It demonstrates the frontend interface creating a room and the terminal interface joining it and the transfer of files between the two. It also demonstrates the frontend interface joining the terminal interface's room.

https://drive.google.com/file/d/1kOOkdAZkCMQRU49zYvU-eZ-aVsnHsQqe/view?usp=sharing

## Screenshots

Chatting on the frontend
<img src="./screenshots/chatting.png?raw=true">

Transferring files on the frontend
<img src="./screenshots/uploading.png?raw=true">

Frontend landing page
<img src="./screenshots/landing.png?raw=true">

Joining a room on the frontend
<img src="./screenshots/joining.png?raw=true">

Connecting to another user in terminal
<img src="./screenshots/connection.png?raw=true">

Transferring files in terminal
<img src="./screenshots/filetransfer.png?raw=true">

Password protection in terminal
<img src="./screenshots/password.png?raw=true">

## Teamwork (Who did what)

- James: Initial python script, frontend
- Jovian: P2P file transfer
- ALan: Password protected rooms
