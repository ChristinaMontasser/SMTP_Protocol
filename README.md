# SMTP (Multiple servers):

# Definention:
 The Simple Mail Transfer Protocol (SMTP) is an internet standard communication protocol for electronic mail transmission. 
  
# Project Description

  ▪ We will use TCP sockets and threads.

  ▪ Multiple Servers and Multiple clients can all connect at the same time. 

      ➢ We just need one class for the server and one class for the client and run each of them multiple times. 
      ➢ Each server should state at the beginning its name (ex. Yahoo, Gmail) and port number. 
      ➢ Each client should state at the beginning server port number
  ▪ Each server should have a folder saved on the machine with its name (ex. Gmail). 

      ➢ This folder is created automatically when the server boots up and states its name for the first time. 
      ➢ If the name already exists, no new folder will be created. 
  ▪ Each server folder should have a file called ‘credentials’ contains the username and password for each user.
 
  ▪ Each server folder has multiple sub-folders for users. 

      ➢ Each sub-folder is named with username (ex. user1).
      ➢ Each sub-folder should have a file named ‘inbox’ where the received emails are saved. 
  ▪ When the client runs, there are two options. 

    i. Register. 
      ➢ The client registers with a new email (ex. user1@gmail.com) and password. 
      ➢ A sub-folder will be created automatically in the server folder. 
      ➢ The ‘inbox’ file will be also created automatically in this sub-folder. 
      ➢ The username (ex.user1) and password are saved in the ‘credentials’ file.   
    ii. Login. 
      ➢ No need to create a sub-folder as it already exists. 
      ➢ No need to create ‘inbox’ file as it already exists. 
      ➢ The username and password should be checked in the ‘credentials’ file. 
      
  ▪ A client can send a new email with content (MAIL FROM, RCPT TO, DATA)

      ➢ This email is firstly sent to the sender server. 
      ➢ The sender server forwards this email to the recipient server. 
      ➢ The recipient server saves this email in the ‘inbox’ file placed in the recipient subfolder. 
      
# Test Case
 
  **Server console**

      ➢ Output: Please enter the server name and port number.
      ➢ Input: gmail.com 
      ➢ Input: 5000 
      ➢ Output: Gmail server with port number ‘5000’ is booted up.
  
   **Client console**

      ➢ Output: Please enter server port number. 
      ➢ Input: 5000 
      ➢ Output: 220  gmail.com // A message from server. 
      ➢ Output: Please choose ‘REGISTER or ‘LOGIN’ or ‘QUIT’. 
      ➢ Input: REGISTER 
      ➢ Output: Please enter an email and a password. 
      ➢ Input: user1@gmail.com // Send this to the server. 
      ➢ Input: 123 // Send this to the server. 
      ➢ Output: HELLO user1@gmail.com // Send this to the server. 
      ➢ Output: 250 Hello user1, pleased to meet you // A message from server. 
      ➢ Output: Please choose ‘SEND’ or ‘QUIT’. 
      ➢ Input: SEND 
      ➢ Output: MAIL FROM user1@gmail.com // Send this to the server. 
      ➢ Output: Server: 250 user1@gmail.com...Sender ok // A message from server. 
      ➢ Output: RCPT TO // Send this to the server. 
      ➢ Input: user1@yahoo.com // Send this to the server. 
      ➢ Output: Server: 250 user1@yahoo.com...Recipient ok // A message from server. 
      ➢ Output: DATA // Send this to the server. 
      ➢ Output: Server: Please enter the body of your email ended by ‘&&&‘ // A message from server. 
      ➢ Input: Dear, // Send this to the server. 
      ➢ Input: How are you? // Send this to the server. 
      ➢ Input: &&& // Send this to the server. 
      ➢ Output: Server: 250 Message accepted for delivery // A message from server. 
      ➢ Output: Please choose ‘SEND’ or ‘QUIT’. 
      ➢ Input: QUIT // Send this to the server. 
      ➢ Output: Server: 221 gmail.com closing connection // A message from server. 
 
 
