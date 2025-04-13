# Indian-Railway-Ticket-Reservation-System

**SETUP**
1. CREATE DATABASE Railway_DB;
2. USE Railway_DB;
3. Create tables and run all the alter commands as given in Tables file (as it is)
4. Create all procedures from Procedures files
5. Create Trigger from Triggers file
6. Populate all the tables using the dataset file. It insert values into some tables and calls procedures for the rest. Cancellations table is populated through trigger trg_after_refund_payment.

**USAGE OF PROCEDURES**

**1.get_trains_by_city_names -** In this procedure we will be providing names of the city from where we have to go that is source city to where that is detonation city. This procedure will print list of all trains going from source city to destination city, along with train id,source station name,destination station name,source departure timr,destination arival time,total available seats.
