# Indian-Railway-Ticket-Reservation-System

**SETUP**
1. CREATE DATABASE Railway_DB;
2. USE Railway_DB;
3. Create tables and run all the alter commands as given in Tables file (as it is)
4. Create all procedures from Procedures files
5. Create Trigger from Triggers file
6. Populate all the tables using the dataset file. It insert values into some tables and calls procedures for the rest. Cancellations table is populated through trigger trg_after_refund_payment.

**USAGE OF PROCEDURES**

1. **get_train_by_city_names**: In this procedure we will be providing names of the city from where we have to go that is source city to where that is detonation city. This procedure will print list of all trains going from source city to destination city, along with train id,source station name,destination station name,source departure timr,destination arival time,total available seats.
2. **get_trains_by_city_names**: This procedure takes source and destination station cities as inputs and outputs all available trains between the given cities with the  number of available seats. This uses the route, stations and seats tables.
3. **calculate_fare_with_concession**: This procedure calculates the fare given passenger_id (to calculate concession), train_id, class_type (1AC, 2AC, 3AC, General), seat_status (Normal or RAC), source_station_id and destination_station_id. Fare is calculates as base_rate * duration_in_minutes * (1 - concession_amount). Here, concession_amount is a percentage of the base rates according to respective concession categories.
4. **book_ticket**: It books the tickets, changes the availability_status of the seats respectively (Booked or RAC) and moves the passenger to waitlist in case the seat is not available and books the ticket as "WAITLISTED". It inputs passenger_id, train_id, route_id, start_station_id, destination_station_id, class_type (1AC, 2AC, 3AC, General), seat_status (Normal or RAC) and travel_date. It uses tables stations, seats, waitlist, tickets, route and passengers.
5. **get_passenger_details_by_train_date**: It lists all the passengers travelling in a particular train on a  particular train. It inputs train_id, travel_date and uses the tables tickets and passengers.
6. **AddPayment**: It inputs in_ticket_id, in_payment_method ('Credit Card','Debit Card','UPI','Cash') and in_payment_status ('Successful','Pending','Failed','Refunded') and inserts all payment info including amount and payment date into the payments table.
7. **CancelTicket**: This procedure is called to cancel tickets from both confirmed and waitlisted and changes its status to "Cancelled". It adds an entry for refund to payments table and changes seats status if required and checks if a person can be waitlist to confirmed and does if possible. It inputs ticket_id.
8. **get_total_revenue**: This procedure displays the total revenue generated in a specified period of time. It inputs start and end date and time.
9. **get_train_with_max_passengers**: This procedure returns the train with maximum number of bookings.
