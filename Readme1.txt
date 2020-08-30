##########################WELCOME TO BOX OFFICE#######################
we use python for this application
we also use to libraries 
I) Time
II) uuid

1)This question mainly deals with the ticket system of a cinema 

2)It takes and stores data collected from users
●for this we made a function called "user" in which data is being taken by user and store in box office file
●it also has a condition that max tickets for a show is 20
●we also add a unique id to each ticket

3)It also generate unique id for a particular tickets
●uuid is a python libraries in which randon specific id generated every time

4)An endpoint to update a ticket timing.
●for this we make a function "manger" in which a manager can login by entering correct password
●can also update timings of the show
●even they can remove show 

5)An endpoint to view all the tickets for a particular time.
●for this there is a function "file" you can write and ride file from there for a particular id

6)An endpoint to delete a particular ticket.

7)An endpoint to view the user’s details based on the ticket id.

8)Mark a ticket as expired if there is a diff of 8 hours between the ticket timing and current
time.
●for this we have a function "timings" in which we can take data from user
●convert into list
●subtract it from actual date, if it is greater then 8 then it is in valid otherwise valid data 

9)Maximum ticket for a show can be 20 not more then that.

