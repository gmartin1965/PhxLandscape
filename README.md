## General

- To View on GitHub Pages, use the following url...
  - https://gmartin1965.github.io/PhxLandscape/
- Upon Login
  - If the User has access to more than one Organization, big buttons will display to allow the User to choose the Organization to work with during this Session. Then…
  - If the User has access to Crew Features and also to Admin Features, that User will see 2 big buttons.
    - Click Admin to put yourself into Admin mode.
    - Click the Crew Button to put yourself into Crew mode and do things a Driver of a Crew would do.</br></br>

## Admin Mode

- Dashboard UI
  - Map (Toggle Between Assets and Properties)
    - The idea is that this will be a Card on the UI that will show a map of the service area for the company. Two toggles...
      - Assets View will show the bubbles indicating where all of the Assets tracked by the company are located. Trucks, Trailers, Heavy Equipment, Mowers, etc.
      - Properties View will show bubbles indicating where all of the Properties are located. These are the Properties the company performs work for.
  - Crew Status (Today Only)
    - Listing of all Crews and an indication of their current "status".
      - Property currently working on
      - Open Work Order Count
      - Remaining Property Count,
      - Open Alert Count
  - KPI Section (Key Performance Indicators)
    - Number of Crews
      - This may be some indication of the Number of Crews working today / Number of Crews the company has defined. The goal would be something in the high 90's I would imagine. Not sure about this one.
    - Ahead/Behind Schedule
      - Count of Crews Ahead of Schedule
      - Count of Crews Behind Schedule
      - Aggregate Time Behind Schedule
    - Revenue Metric
      - 3 Graph Options
        - Revenue for Today and Trend Graph of Revenue each of last 30 Days
        - Revenue This Week and Trend Graph of Revenue each of last 90 Days
        - Revenue for This Month and Trend Graph of Revenue each of last 12 Months
        - Revenue This Month compared to Revenue Same Month Last Year
    - Outstanding/Overdue Work Orders
      - Work Orders Outstanding Count
      - Work Orders Resolved Count
      - These 2 may be combined into a graph (circle or pie of some sort)
  - Alerts
    - Listing of Alerts
    - Toggle Options to show Resolved/Unresolved/All
    - For Unresolved Alerts, order by oldest to newest
    - For Resolved Alerts, order by newest to oldest
  - Work Orders (Tickets)
    - Day, Week, Month Options
    - Toggle for Completed/Pending/All
    - For Pending Work Orders, order by oldest to newest
    - For Completed Work Orders, order by newest to oldest
  - Route List (Pick a Day)
    - List will include one row for each Route that is scheduled for the chosen day
    - List item will show
      - Driver Name
      - Property Name
      - Elapsed Time for the Route
      - Remaining Estimated Time for the Route</br></br>
- Crew Setup
  - List Crews - from this list User will be able to...
    - Manage a Crew
    - Create a New Crew</br></br>
- Labor Resource
  - List Resources (Workers) - from this list User will be able to...
    - Edit a Resource
    - Create a New Resource</br></br>
- Master Route Setup
  - List Master Routes - from this list User will be able to...
    - Edit a Master Route
    - Create a New Master Route
    - Question
      - Can an Area belong to more than one Master Route?</br></br>

<div style="page-break-after: always"></div>

- Daily Route Setup
  - List the Daily Routes for a given Date
    - The list should have a selector that allows User to choose a different day
  - Edit the Route
  - Create a new Daily Route
    - Create New has the option to make a copy based on one of the Master Routes</br></br>
- Asset Setup
  - List All Assets
    - List should have a selector that allows the User to filter down to specific "types" of Assets
    - List should have a "search" feature as well
  - Edit an Asset
  - Add a New Asset</br></br>
- Work Orders (Tickets)
  - Listing of all Work Orders (For a Given Day)
    - User should be able to choose a different day
    - User should be able to toggle on or off so he can see only Completed or Pending
  - Edit a Work Order
  - Create a New Work Order</br></br>
- Customer Master
  - List of all Customers
    - Search Feature Needed to quickly filter this list
  - Edit a Customer
    - Edit UI should list the Properties associated with this Customer.
    - Ability to directly "edit" the Property from this UI is needed.
      - When editing a Property, UI should list the Areas associated with this Property.
        - Ability to directly "edit" the Area from this UI is needed.
  - Add a New Customer</br></br>

<div style="page-break-after: always"></div>

- Property Master (Possibly not needed. Navigation to a Property should possibly occur by using the Customer UI described above.)
  - Listing of all Properties
    - Search Feature needed to quickly filter this list
  - Edit a Property
    - When editing a Property, UI should list the Areas associated with this Property.
      - Ability to directly "edit" the Area from this UI is needed.
  - Create a New Property

---

## Crew Mode

- Crew Track will ultimately be a native "mobile application" rather than a responsive web site.</br></br>
- Vehicle Selection - the User must tell the application which Vehicle he is driving today.
  - A pick list seems appropriate.
    - The list will show the last 3 Vehicles the User was driving
    - A mechanism will be provided that will allow a search if the Vehicle is not among the last 3 driven by that User
    - Once Login and Vehicle Selection is complete, the User will then see the Dashboard.</br></br>
- Dashboard
  - Banner for Unresolved Alerts
  - Listing of Today's Route
    - This will be a List that shows the Properties this Crew is expected to work today. The list will be retrieved by sending Today's Date and the user_id of the logged in user as params.</br></br>
- Alert Manager
  - User can see a listing of Alerts (Descending by Date)
    - Toggle for "Unresolved, Resolved, All"
  - Most likely, the Alerts feature will be a Header/Detail database relationship. Each Alert will be a Header row and the back and forth conversation to resolve the Alert will make up the Detail rows.
  - Question: Will Alerts be attached to Customers, Properties, Areas, Assets, etc.? Or, will they simply be assigned to Drivers?
    - Best approach may be to attach the Alert to the Customers, Properties, Areas, Assets, etc. And, also to a Driver. If a Driver is covering for another Driver, and he rolls up to Property 123 and that Property has an Alert, he should see it. Even if he is not the "normal" Driver. Or, if a Vehicle is due for an Inspection or needs to come back to the Maintenance Warehouse for whatever reason, any Driver in that Vehicle needs to see the Alert until it is resolved.</br></br>
- Work Order
  - Listing of Work Orders
    - User can toggle between Open/Closed/All
    - Initial Criteria for the list is all work orders that are associated with Properties that are part of a Route owned by this Driver ID.
    - Search Feature
      - Possibly, keep it simple says maybe not. Because the Criteria is very limiting to begin with, adding UI complexity of search may not be best idea.
  - Work Orders will also appear in the Drill Down when a User starts to "work" a Property on the Route. This is more a listing of all of this Driver's Work Orders.</br></br>
- Crew List
  - List of all Crew Members
    - Meant to provide the Driver with a quick glance of who the members of his team are.
    - Also provides photos of team members and phone numbers.

<div style="page-break-after: always"></div>
