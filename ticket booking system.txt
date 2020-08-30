import time
import uuid


# An endpoint to book a ticket using a user’s name, phone number, and timings
#assuming there are 4 shows going on different times
ticket_timings = ["15:00","13:00","11:00","12:00"]
def user():
    name = input("enter your name")
    phonenumber = int(input("enter your mobile number"))
    timings = str(input("enter timings in HH:MM format"))
    date = str(input("enter Date of movie"))
    number_of_tickets = 0
    if timings == "15:00" and number_of_tickets<20:
        number_of_tickets += 1
        user.total_number_of_tickets_3 = number_of_tickets
        print(uuid.uuid4())
        file()

    elif timings == "13:00" and number_of_tickets<20:
        number_of_tickets += 1
        user.total_number_of_tickets_1 = number_of_tickets
        print(uuid.uuid4())
        file()

    elif timings == "11:00" and number_of_tickets<20:
        number_of_tickets += 1
        user.total_number_of_tickets_11 = number_of_tickets
        print(uuid.uuid4())
        file()

    elif timings == "12:00" and number_of_tickets<20:
        number_of_tickets += 1
        user.total_number_of_tickets_12 = number_of_tickets
        print(uuid.uuid4())
        file()
    else:
        print("Enter correct timings")
        user()

def file():
    if timings in ticket_timings:
        text = input(user.name,user.phonenumber,user.timings)
        with open("box office.txt", "a") as f:
            a = f.write(text)
    else:
        print("write valid input")
        user()

 # An endpoint to view the user’s details based on the ticket id.
def open():
     f = open("box office.txt", "rt")
     id = input("enter the unique id of ticket")
     print(f.readline((id)))
     f.close()

# An endpoint to view all the tickets for a particular time.
def viewtickets():
    enter_the_admin_password = int(input("Enter the password"))
    if enter_the_admin_password == 12345678:
        which_timings = input("enter the timings you want to see the count")
        if which_timings == "15:00":
            print(user.user.total_number_of_tickets_3)
        elif which_timings == "12:00":
            print(user.user.total_number_of_tickets_3)
        elif which_timings == "11:00":
            print(user.user.total_number_of_tickets_3)
        elif which_timings == "13:00":
            print(user.user.total_number_of_tickets_3)
        else:
            print("enter correct timings")
            viewtickets()
    else:
        print("Please write the correct admin password")
        viewtickets()


# An endpoint to update a ticket timing.
# An endpoint to delete a particular ticket.

def mangager():
     permisson = input(" y for change the timings:\n n for remove the timings :\n v for view the total movies\n").casefold()
     if permisson == "y":
         print(ticket_timings)
         time_to_change = int(input("enter the ticket timing index you want to update"))
         updatetimings = input("enter the timings in HH:MM format")
         ticket_timings[time_to_change] = updatetimings
         print(ticket_timings)
     elif permisson == "n":
         want = input("do you want to remove timings")
         print(ticket_timings)
         time_to_delete = str(input("enter the ticket timing you want to delete"))
         ticket_timings.remove(time_to_delete)
         print(ticket_timings)
     elif permisson=="v":
         viewtickets()



# Mark a ticket as expired if there is a diff of 8 hours between the ticket timing and current time.
def timings():

    ticket_time = timings()
    Date = user.date
    time_string = time.strftime(" %d/%H/%M", ticket_time)
    time_list= time_string.split('/')

    time_list = [int(i) for i in time_list]

    print(time_string)
    print(time_list)
    i=0
    while  i < 100000000:

        i = i+1

    current_time = time.localtime() # get struct_time
    currenttime_string = time.strftime("%y/%m/%d / %H/%M/%S", current_time)
    currenttime_list= currenttime_string.split('/')
    currenttime_list = [int(i) for i in currenttime_list]

    print(time_string)
    print(currenttime_list)
    if currenttime_list[3] - time_list[3] > 8 | currenttime_list[2] - time_list[2] >0 | currenttime_list[1] - time_list[1] >0 | currenttime_list[0] - time_list[0]:
        print("time exceeded 8 hrs")
    else :
        print("valid ")

def main():
    print("###############  WELCOME TO BOXOFFICE  #############")
    who_you_are = input("Are you a customer or manager:").casefold()
    if who_you_are == "customer":
        user()
    elif who_you_are == "manager":
        enter_the_admin_password = int(input("Enter the password"))
        if enter_the_admin_password == 12345678:
            mangager()
        else:
            print("Please write the correct admin password")
            main()
main()


