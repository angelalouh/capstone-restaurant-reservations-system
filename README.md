# Restaurant Reservation System App
This application was built for use by restaurant personnel to handle reservations when a customer calls, seat reservations when they arrive at the restaurant, and free up occupied tables when guests leave.

Project Prompt:
> You have been hired as a full stack developer at *Periodic Tables*, a startup that is creating a reservation system for fine dining restaurants. The Product Manager has already created 8 user stories for *Periodic Tables*, and another developer has already written the tests for each of the user stories. 

## Links
- [Live Demo](https://capstone-restaurant-reservations-system.vercel.app/)
- [API Documentation](https://github.com/angelalouh/capstone-restaurant-reservations-system-api)

## Screenshots
### Home Page/Dashboard:
![dashboard](/screenshots/dashboard.jpg)
The Dashboard, located at `/dashboard` has the following features:
- Lists all reservations for one date only. The date is defaulted to today and the reservations are sorted by time.
- Each reservation will display its status. The default status is `booked`. A "Seat" button will display for reservations that are `booked`.
- Each reservation displays an "Edit" and "Cancel" button. Only reservations with a status of `booked` can be edited. 
- Displays next, previous, and today buttons that allow the user to see reservations on other dates.
- Displays a list of all tables, sorted by name. Each table will display "Free" or "Occupied" depending on whether or not a reservation is seated at the table. Each "Occupied" table will have a "Finish" button.
- Displays any error messages returned from the API.

### Create New Reservation:
![create-reservation](/screenshots/create-reservation.jpg)
Clicking on `New Reservation` of the Menu side bar will take the user to the `/reservations/new` page. The Create Reservation page displays a form with the following required fields: first name, last name, mobile number, date of reservation, time of reservation, and the number of people in the party. Clicking on the "Submit" button will save the reservation and then display the `/dashboard` page for the date of the new reservation. Clicking on the "Cancel" button will take the user to the previous page. While attempting to create a new reservation, any error messages returned from the API will be displayed. 

### Create New Tables:
![create-table](/screenshots/create-table.jpg)
Clicking on `New Table` of the Menu side bar will take the user to the `/tables/new` page. The Create Table page displays a form with the following required fields: table name and capacity. Clicking on the "Submit" button will save the new table and then display the `/dashboard` page. Clicking on the "Cancel" button will take the user to the previous page. While attempting to create a new table, any error messages returned from the API will be displayed. 

### Seating a Reservation:
When the user clicks on the "Seat" button associated with a particular reservation, the application will take the user to the Seat Reservation page, `/reservations/:reservation_id/seat`. 
![dashboard-click-seat](/screenshots/dashboard-click-seat.jpg)
![seat-reservation](/screenshots/seat-reservation.jpg)
On this page, the user will be able to choose the table to seat the reservation at. The options from the drop-down menu are formatted such that the first part of the option name is the table's name, followed by the table's capacity. Clicking on the "Submit" button will assign the table to the reservation and then display the `/dashboard` page. Simultaneously, that reservation's status will be changed to `seated`. Clicking on the "Cancel" button will take the user to the previous page. While attempting to seat a reservation, any error messages returned from the API will be displayed. 

### Seated Reservation:
![seated-reservation](/screenshots/seated-reservation-cropped.jpg)

### Finishing an Occupied Table:
Clicking on the "Finish" button of an "Occupied" table will display the following confirmation:
![finish-reservation](/screenshots/finish-reservation-cropped.jpg)
If the user selects "OK", the system will remove the table assignment and indicate the table is now "Free" again. This action will also change that reservation's status to `finished` and the system will remove the reservation from the Dashboard. Clicking "Cancel" on the confirmation dialog will make no changes. 

### Finished Table/Reservation:
![finished-reservation](/screenshots/finished-reservation.jpg)

### Search Reservation:
Clicking on `Search` of the Menu side bar will take the user to the `/search` page.
![search-reservation](/screenshots/search-reservation.jpg)
The `/search` page will:
- Display a search box that displays the placeholder text, "Enter a customer's phone number, and a "Find" button next to the search box.
- Clicking on the "Find" button will submit a request to the server to find the reservations(s) in the database with that phone number. The server will send back all matched records and the `/search` page will display all matching reservations, regardless of status, using the same reservations list component as the `/dashboard` page.

### Found Reservations:
![found-reservation](/screenshots/found-reservation.jpg)

### No Reservations Found:
![no-reservations-found](/screenshots/no-reservations-found.jpg)
If no records are found after clicking on the "Find" button, the page will display `No reservations found.`

### Edit Reservation:
Clicking on the "Edit" button will navigate the user to `/reservations/:reservation_id/edit` page. 
![dashboard-click-edit](/screenshots/dashboard-click-edit.jpg)
![edit-reservation](/screenshots/edit-reservation.jpg)
This page will display the reservation form with the existing reservation data filled in. Clicking on the "Submit" button will save the reservation and then display the updated reservation on the `/dashboard` page. Clicking on the "Cancel" button will make no changes and the user will be taken back to the previous page.

### Edited Reservation:
![edited-reservation](/screenshots/edited-reservation.jpg)

### Cancel Reservation:
Clicking on the "Cancel" button associated with a particular reservation will display the following confirmation:
![dashboard-click-cancel](/screenshots/dashboard-click-cancel.jpg)
![cancel-reservation](/screenshots/cancel-reservation.jpg)
Clicking "OK" on the confirmation dialog will set the status of that reservation to `cancelled`, and the results on the page are refreshed. Clicking "Cancel" on the confirmation dialog will make no changes.

### Cancelled Reservation:
![cancelled-reservation](/screenshots/cancelled-reservation.jpg)

## Technology
### Built with:
- React.js, CSS, and Bootstrap

### API Interface:
- Built to interface with: [Capstone Restaurant Reservation System API](https://github.com/angelalouh/capstone-restaurant-reservations-system-api)

## Installation
1. Fork and clone this repository.
2. Run `cp ./.env.sample ./env`
3. You should not need to make changes to the `./env` file unless you want to connect to a backend at a location other than `http://localhost:5000`.
4. Run `npm install` to install project dependencies.
5. Run `npm run start` to start the frontend of the application.
