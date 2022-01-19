# Cinema app
   ![cinema_tape](https://i.ibb.co/T8zF9wY/cinema-02-06.png)
##Project description
   The main purpose of this project is to simulate basic cinema ticket shop application with simple authentication system. It used such popular frameworks as Spring and Hibernate Using this app allows you:
   * Add new movies
   * Add new movie sessions
   * Register new customers
   * Manage current database
##Implementation details
   Cinema app uses database to store information about movies, movie sessions, cinema halls, users and their orders.
### Following diagram shows relations between models
   ![EER_Diagram](https://i.ibb.co/ByHMqkD/cinema-app-db.jpg)

Project has multiple endpoints with user and admin access
   ### List of endpoints
   * POST: /register - all
   * GET: /cinema-halls - user/admin
   * POST: /cinema-halls - admin
   * GET: /movies - user/admin
   * POST: /movies - admin
   * GET: /movie-sessions/available - user/admin
   * GET: /movie-sessions/{id} - user/admin
   * POST: /movie-sessions - admin
   * PUT: /movie-sessions/{id} - admin
   * DELETE: /movie-sessions/{id} - admin
   * GET: /orders - user
   * POST: /orders/complete - user
   * PUT: /shopping-carts/movie-sessions - user
   * GET: /shopping-carts/by-user - user
   * GET: /users/by-email - admin

All incoming and outgoing data are converted into JSON format.
### Examples how to interact with application using Postman
* POST: /movies <br/>
`{"title" : "title", "description" : "description"}` <br/>
* PUT: /movie-sessions/{id} <br/>
`{"movieId":1, "cinemaHallId":1, "showTime":"08.02.2022 15:15"}` <br/>
##Used technologies
   * Apache Tomcat (v9.0.50)
   * MySQL
   * Hibernate
   * Spring (Core, Web, Security)
   * Maven
##Setup recommendations
1. Install MySQL
2. Configure Apache Tomcat
3. Create new schema in MySQL
4. Fork and clone this project
5. Replace `YOUR_DRIVER`, `YOUR_DATABASE_URL`, `YOUR_USERNAME`, `YOUR_PASSWORD` with your information in `db.properties` file in `src/main/resources` folder.
6. Run this app with Tomcat local server.
7. You can use username `admin@mail.com` and password `adminPass` to authenticate as admin
8. Have fun :)
