# Airline-Ticket-Booking-UI
# Skyline Air - Flight Booking Management System

## Overview

Skyline Air is a Salesforce Visualforce-based Flight Booking Management System that provides a modern and interactive interface for managing airline bookings.

The application allows users to:

* View available flights
* Filter flights by Domestic and International routes
* Search flights dynamically
* Calculate booking costs based on seat count
* Create flight bookings
* Edit existing bookings
* Delete bookings
* View all bookings in a dashboard layout

The UI is built using HTML, CSS, and JavaScript within a Visualforce Page and does not require any Apex Controller.

---

## Features

### Flight Dashboard

* Displays all available flights.
* Responsive card-based layout.
* Domestic and International flight classification.
* Interactive hover effects.

### Flight Search

Users can search flights by:

* Flight ID
* Departure City
* Destination City

### Flight Filtering

Available filters:

* All Flights
* Domestic Flights
* International Flights

### Booking Form

Allows users to:

* Enter Passenger Name
* Select Flight
* Enter Number of Seats
* View Real-Time Total Price

### Booking Management

Supports:

* Add Booking
* Edit Booking
* Save Booking Changes
* Delete Booking

### Price Calculation

Total booking cost is automatically calculated:

Total Price = Flight Price × Number of Seats

---

## Technology Stack

| Technology             | Usage             |
| ---------------------- | ----------------- |
| Salesforce Visualforce | Front-End Hosting |
| HTML5                  | Structure         |
| CSS3                   | Styling           |
| JavaScript             | Business Logic    |
| Salesforce Platform    | Deployment        |

---

## Flight Categories

### Domestic Flights

Examples:

* Pune → Bangalore
* Mumbai → Goa
* Delhi → Jaipur

### International Flights

Examples:

* Delhi → Dubai
* Mumbai → Singapore
* Bangalore → London

---

## Project Structure

Visualforce Page

SkylineAir.page

Contains:

* HTML Layout
* CSS Styling
* JavaScript Logic
* Flight Data
* Booking Management Functions

---

## JavaScript Functions

### renderFlights()

Displays flights based on:

* Search text
* Selected filter

### renderDropdown()

Loads all flights into the flight selection dropdown.

### updatePrice()

Calculates total booking amount.

### addBooking()

Creates a new booking and displays it in the dashboard.

### editBooking(index)

Loads booking data into the form for editing.

### saveEdit()

Updates the selected booking.

### deleteBooking(index)

Removes a booking from the dashboard.

### renderBookings()

Refreshes booking cards after add/edit/delete operations.

---

## Limitations

Current implementation stores data in JavaScript memory only.

This means:

* Bookings are not saved in Salesforce records.
* Data is lost after page refresh.
* No database persistence.

---

## Future Enhancements

Possible improvements:

* Create Custom Objects:

  * Flight__c
  * Booking__c

* Use Apex Controllers

* Store data in Salesforce Database

* Add:

  * Validation Rules
  * Passenger Email
  * Seat Availability
  * Payment Processing
  * Reports & Dashboards

---


Detailed Steps to Create This Visualforce Page in Salesforce
Prerequisites

You need:

Salesforce Developer Org or Sandbox
System Administrator access
Visualforce enabled
Step 1: Login to Salesforce
Open Salesforce.
Login using your credentials.
Switch to Lightning Experience (if not already).
Step 2: Open Visualforce Pages
Option 1: Using Setup
Click Gear Icon → Setup.
In the Quick Find box, search:
Visualforce Pages
Click Visualforce Pages.
Step 3: Create New Visualforce Page

Click:

New

Enter:

Label: Skyline Air

Name: SkylineAir

Then click:

Save
Step 4: Paste the Code

Delete the default code:

<apex:page>
</apex:page>

Paste your entire code into the editor.

Example:

<apex:page>

<!-- Your CSS -->
<style>
...
</style>

<!-- HTML -->
<div class="header">
...
</div>

<!-- JavaScript -->
<script>
...
</script>

</apex:page>

Click:

Save
Step 5: Preview the Page

Click:

Preview

Salesforce generates a URL similar to:

https://yourdomain.my.salesforce.com/apex/SkylineAir

You should see:

Skyline Air header
Booking Form
Flight Cards
Search functionality
Booking Dashboard
Step 6: Add Visualforce Page to a Lightning App
Create a Visualforce Tab

Go to:

Setup → Tabs

Under:

Visualforce Tabs

Click:

New

Select:

Visualforce Page = SkylineAir

Choose:

Tab Label = Skyline Air

Select:

Tab Style = Airplane Icon (or any icon)

Click:

Next → Save
Step 7: Add Tab to Application

Navigate to:

Setup → App Manager

Choose your Lightning App.

Click:

Edit

Go to:

Navigation Items

Move:

Skyline Air

from Available Items to Selected Items.

Save.

Step 8: Open the Application

Launch the app.

You should now see:

Skyline Air

in the navigation menu.

Click it.

The Visualforce page loads inside Salesforce.

How the Application Works Internally
Flight Data

Flights are stored inside JavaScript:

const flights = [
"F102,Pune,Bangalore,4000",
"F103,Chennai,Delhi,5500"
];

Each record contains:

Flight ID
Source
Destination
Price
Domestic Flight Logic
function isDomestic(from,to)

Checks whether both cities belong to India.

Returns:

true

or

false

Used for:

Flight badges
Flight filtering
Search Logic
(id+from+to)
.toLowerCase()
.includes(search)

Allows searching by:

Flight ID
Source City
Destination City
Booking Creation Flow

User:

Enters Name
Selects Flight
Enters Seats
Clicks Add

JavaScript:

bookings.push(...)

Stores booking in memory.

Then:

renderBookings()

updates the dashboard.

Edit Flow

When Edit is clicked:

editBooking(index)

Loads data into the form.

When Save is clicked:

saveEdit()

Updates the booking.

Delete Flow
deleteBooking(index)

Removes booking from array.

Then:

renderBookings()

refreshes the UI.

Recommended Salesforce Enhancement

For a real Salesforce project, replace the JavaScript arrays with:

Custom Objects
Flight__c
Booking__c
Apex Controller
public with sharing class SkylineAirController {
}

Benefits
Persistent data storage
SOQL querying
Security model support
Reporting and dashboards
Multi-user access
Real-world airline booking simulation

## Author
Michelle Waugh
Only used for Educational Purposes
Developed using Salesforce Visualforce, HTML, CSS, and JavaScript.

Version: 1.0

