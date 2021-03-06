# Cinema app
   ![cinema_tape](https://i.ibb.co/T8zF9wY/cinema-02-06.png)

## Project description
   The main purpose of this project is to simulate basic cinema ticket shop application with simple authentication system. It uses such popular frameworks as Spring and Hibernate Using this app allows you:
   * Add new movies.
   * Add new movie sessions.
   * Register new customers.
   * Manage current database.

## Implementation details
   Cinema app uses database to store information about movies, movie sessions, cinema halls, users and their orders.
### Following diagram shows relations between models
   ![EER_Diagram](https://i.ibb.co/ByHMqkD/cinema-app-db.jpg)

In project implemented authorization depending on user's role. There are two type of role `ADMIN` and `USER`
Project has multiple endpoints with access depended on user's role
   ### List of endpoints and required role
   * POST: /register - all
   * GET: /cinema-halls - USER/ADMIN
   * POST: /cinema-halls - ADMIN
   * GET: /movies - USER/ADMIN
   * POST: /movies - ADMIN
   * GET: /movie-sessions/available - USER/ADMIN
   * GET: /movie-sessions/{id} - USER/ADMIN
   * POST: /movie-sessions - ADMIN
   * PUT: /movie-sessions/{id} - ADMIN
   * DELETE: /movie-sessions/{id} - ADMIN
   * GET: /orders - USER
   * POST: /orders/complete - ADMIN
   * PUT: /shopping-carts/movie-sessions - USER
   * GET: /shopping-carts/by-user - USER
   * GET: /users/by-email - ADMIN

All incoming and outgoing data are converted into JSON format.
### Examples how to interact with application using Postman
* POST: /movies <br/>
`{"title" : "title", "description" : "description"}` <br/>
* PUT: /movie-sessions/{id} <br/>
`{"movieId":1, "cinemaHallId":1, "showTime":"08.02.2022 15:15"}` <br/>

## Used technologies
   * Apache Tomcat (v9.0.50)
   * MySQL
   * Hibernate
   * Spring (Core, Web, Security)
   * Maven
## Setup recommendations
1. Install MySQL.
2. Configure Apache Tomcat.
3. Create new schema in MySQL.
4. Fork and clone this project.
5. Replace `YOUR_DRIVER`, `YOUR_DATABASE_URL`, `YOUR_USERNAME`, `YOUR_PASSWORD` with your information in `db.properties` file in `src/main/resources` folder.
6. Run this app with Tomcat local server.
7. There is one already registered `ADMIN` user with username `admin@mail.com` and password `adminPass` fill free to use it, or register a new user using Postman<br/>
`POST: /register {"email" : "emai@user.com", "password" : "password", "repeatPassword" : "password"}` <br/>
8. Have fun :)
