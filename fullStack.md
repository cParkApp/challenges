# cPark Full stack developer challenge (React Native, Node JS)

## Challenge

Create an app that will display the last and closest reports sent by the community to an API server.

Create a Frontend app using React Native, that will enable the user to send reports to the server and display the list of those reports, filtered by time and/or distance.

## Structure of a report

A report is a timed gospatial record. It has the following fields:

| Name      | Type          | Description                       |
|-----------|---------------|-----------------------------------|
| _id       | `ObjectID`    | Unique ID for the record          |
| title     | `String`      | Title of the record               |
| time      | `Datetime`    | Date and time of the record       |
| position  | `Coordinates` | Latitude/Longitude of the report  |

## Frontend base

The app has two views: The "Report View" and the "List of Reports". This app should be runnable directly (in one command) for the reviewer.

### Report View

Form that allows the user to send a new Report to the server. The user can only choose a title and a time for the report.

Position is retrieved using the geolocation of the phone.

### List of Reports

List of reports previously sent to the server. The list can be ordered by time (last report first) or by distance (closest first).

## Backend base

The backend is a REST API. Use Express or Restify to handle requests from the clients.
The API connects to a mongoDB server (local of remote, as you want).

There are two mandatory endpoints:

| Path                | Method  | Desciption                  |
|---------------------|---------|-----------------------------|
| `/report`           | POST    | Register a new report in DB |
| `/report/:lat/:long`| GET     | Get the list of reports     |

The list of reports depends on the position: `lat` is the latitude and `long` the longitude. We only want the reports around the user (Max 10km of distance).

## What we value

The aim of this challenge is to assess your abilities to create good functional code but also easily maintainable. Hence, it's important to follow the good practice for devlopment. We want you to follow those:

* Use ES6, React Native, Express/Restify and MongoDB
* Lint your code with ESLint and the AirBNB Standards
* Document your code (ESDoc)
* Unit test as much as possible (Stay rational here !)
* Segment your code for evolutivity and maintainability
* Clean Git commits and history
* Add a README file explaining how to launch the backend and the Frontend. It should be as simple as possible.

## Go further

Those points are bonus and will be taken into account in the evaluation of your result:

* Display reports on a map
* Dockerized API: Create a docker image for the Backend
* HTML Documentation of your code
* User Authentication using `JWT` between client and server
* Add a cache layer

## Deliverable

Send your git repo (link or ZIP file) to nicolas@seety.co.
