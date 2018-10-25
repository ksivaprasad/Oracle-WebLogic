# Oracle-WebLogic

## Configuring the server

1. Install and Start oracle weblogic server. 
2. Go to web logic console throgh http://localhost:7001/console
3. Go to 'Environment > Servers'. Click new to create new server. Name the server and set the port and hit 'finish'. 
   (In my case am using AdminServer)
4. Go to 'Messaging > JMS Servers'. Click new and name it TestJMSServer. 
   4.1. In the 'Persistent Store' field click 'Create a new Store' button.
   4.2. Choose type as 'File Store' and hit next.
   4.3. name it as 'TestFileStore' and choose the target as 'AdminServer' and hit 'OK'
        (NB: Leave the file store creation if you already have one)
5. Now choose the file store created from the drop down and hit next.
6. Choose the target as 'AdminServer' and hit finish.
7. Go to 'Messaging > JMS Modules'. Click new and name it TestSystemModule and hit 'next'.
8. Choose the target as 'AdminServer' and hit 'next'.
9. Tick the checkbox 'Would you like to add resources to this JMS system module?' and hit finish.
10. It will open the page to add resources to the module. If you didn't checked it you can get this page by choosing your JMS module fom the list
11. Click new and choose 'Connection Factory' and hit next.
    11.1. Set the Name and JNDI Name as '/com/test/weblogic/base/cf'. Then hit next and choose the target as AdminServer and hit finish.
12. Click new and choose 'Distributed Queue' and hit next.
    12.1. Set the Name and JNDI Name as '/com/test/weblogic/base/dq'. Then hit next and choose the target as AdminServer and hit finish.
13. Click new and choose 'Distributed Topic' and hit next.
    13.1. Set the Name and JNDI Name as '/com/test/weblogic/base/dt'. Then hit next and choose the target as AdminServer and hit finish.
    
    

## Running the program

1. First run the QueuePost.java to send messages to the queue.
2. Run the QueueReader.java to read messages from the queue.

3. To test the queue
  3.1. In the Server console go to 'Messaging > JMS Modules > TestSystemModule > /com/test/weblogic/base/dq > Monitoring'.
  3.2. Coose your destination and hit 'View Messages'. The messages in the queue will be appeared here unless it is not read

