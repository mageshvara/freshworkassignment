# freshworkassignment Mageswaran R (svce)

Freshworks –Backend Assignment
Build a file-based key-value data storethat supports the basic CRD (create, read, and delete) operations. This data store is meant to be used as a local storage for one single process on one laptop. The data store must be exposed as a library to clients that can instantiate a class and work with the data store.

The data store will support the following functional requirements.
1.It can be initialized using an optional file path. If one is not provided, it will reliably create itself in a reasonable location on the laptop.
2.A new key-value pair can be added to the data store using the Create operation. The key is always a string -capped at 32chars. The value is always a JSON object-capped at 16KB.
3.If Create is invoked for an existingkey, an appropriate error must be returned.
4.A Read operation on a key can be performed by providing the key, and receiving the value in response, as a JSON object.
5.A Delete operation can be performed by providing the key.
6.Every key supports setting a Time-To-Live property when it is created. This property is optional. If provided, it will be evaluated as an integer defining the number of seconds the key must be retained in the data store. Once the Time-To-Live for a key has expired, the key will no longerbe available for Read or Delete operations.
7.Appropriate error responses must always be returned to a client if it uses the data store in unexpected ways or breaches any limits.

The data store will also support the following non-functional requirements.

1.The size of the file storing data must never exceed 1GB.
2.More than one client process cannot be allowed to use the same file as a data store at any given time.
3.A client process is allowed to access the data store using multiple threads, if it desires to. Thedata store must therefore be thread-safe.
4.The client will bear as little memory costs as possible to use this data store, while deriving maximum performance with respect to response times for accessing the data store.

Language i have used NODEJS

Go through the code.js,index.js file and output folder that are attached here with in order to understand clearly how 
the code works and how to perform operations in this.

steps:
  The CRD (create,read,delete) operation performing functions are present in index.js file.
  In code.js file i have imported the index.js file so from here we can make use of those functionality that present in the index file.
  The first step is to import index.js functions:
      var { create,read,delete1} = require('./index');
  The second step is to create a new key-value pair for that we use create function:
     Note:we have to pass parameters like key,value and timestamp value.
    --var create1 = create("magesh",10,20000);
          magesh-is the key
          10 is the value
          2000 is the timestamp      
      using this command the create function in index.js get executed and the key get stored in data.json.
           index.js:
           function create(key,value,timestamp)
           {
           }
           data.json:
          {"magesh":{"value":10,"timestamp":1606881772088}}
      Note: the key must contain only alphabets and also its length should not exceed 32
   The third step is to read the value of the key for this provide the key as a parameter to the read function.
       Note:provide the key as a parameter that already exist or else it display error msg like "Key not found"
     --var read1=read("magesh");
     This will invoke the read function in index.js file.which returns the key value.
         function read(key)
         {
             returns value; 
         }
   The final step is to perform delete opertation here we has to provide the key as the parameter.
         Note:provide the key as a parameter that already exist or else it display error msg like "Key not found"
    --var deletekey1=delete1("magesh");
         This will invoke the delete function in index.js file.which deletes the key in data.json and return a msg like 
         "Key successfully deleted".
       function delete1(key)
         {
             returns "Key successfully deleted"; 
         }        
 I have provided the output screen shots for the better understaning.
