# ![](https://cdn-icons-png.flaticon.com/64/2445/2445320.png) CINEMA APP ![](https://cdn-icons-png.flaticon.com/64/2445/2445320.png)

It is an app that allows users to order movie tickets, view available movie sessions, and view their shopping cart. The application is built on Hibernate and Spring frameworks, using REST, SOLID, KISS, DRY principles, Three-Tier architecture:
1. Controllers - user interaction with the program: sending requests and receiving responses;
2. Services - business logic;
3. Data access object (DAO) - interaction of the program with the database.

For easier relations with the application, you can use the following Postman collection: [collection](https://www.postman.com/spacecraft-explorer-61698248/workspace/cinema-app/collection/27153723-05ae1d13-0b1b-4c20-82a4-dfa65e83b91f?action=share&creator=27153723)

### 📌 GETTING STARTED
- Install JDK, Tomcat, MySQL
- Clone this repository
- Create an empty schema in DB
- Update fields `YOUR_DRIVER, YOUR_DATABASE_URL, YOUR_USERNAME, YOUR_PASSWORD` with your data in `db.properties` (resources package) file
- Replace SQl dialect according to your version of MySQL
- Build the project using Maven (`mvn clean install`)
- Deploy the WAR file to Tomcat
- Configure Tomcat Artifact: war-exploded artifact, Application context: "/"
- Run the project
- Login with the following credentials depending on the role: `ADMIN: login - admin@i.ua, password - admin123; USER: login - bob@i.ua, password - bob123` or register a new one by sending a POST request to `/register` endpoint

### 🎉 FEATURES
- In the role of `USER` you can :
   - view a list of movies
   - view a list of cinema halls
   - view available movie sessions
   - create shopping cart
   - add tickets to the shopping cart
   - view shopping cart
   - make an order
   - view order history
- In the role of `ADMIN` you can:
   - view the list of movies and add a movie to the list
   - delete movie session by id
   - view the list of movie sessions and add a movie session to the list
   - find user by email



### 🗂 STRUCTURE
- config - app's configuration
- controller - controllers for endpoints:
  - `POST /login` - authentication
  - `GET /logout` - logout
  - AuthenticationController:
      - `/register` - new user registration
  - CinemaHallController:
      - `GET /cinema-halls/` - show all cinema-halls
      - `POST /cinema-halls/` - add a new cinema hall
  - MovieController: 
      - `GET /movies/` - show all movies
      - `POST /movies/` - add a new movie
  - MovieSessionController: 
      - `GET /movie-sessions/available/` - show all available movie sessions
      - `POST /movie-sessions/` - add a new movie session
      - `PUT /movie-sessions/${id}/` - update a movie session by id
      - `DELETE /movie-sessions/${id}` - delete a movie session by id
  - OrderController:
      - `GET /orders/` - show user's order history
      - `POST /orders/complete` - complete order
  - ShoppingCartController:
      - `GET /shopping-carts/by-user/` - show all tickets added to user's shopping cart
      - `PUT /shopping-carts/movie-sessions/` -  update shopping cart by movie session id
  - UserController:
      - `GET /users/by-email/` - show user's information by email
- dao - Data Access Object interfaces and their implementations
- dto - Data Transfer Object
- exception - custom DataProcessingException
- lib - email and password validators with custom annotations
- model - models that represent entities in the database
- service - services and their implementations that embody business logic
- util - contains a DateTime pattern
- resources - files with database configuration

### 🛠 TECHNOLOGIES
- JDK `v.17.0.2` 
- Maven `v.3.10.1`
- Spring Core `v.5.3.20`
- MySql `v.8.0.22`
- Hibernate `v.5.6.14.Final`
- Hibernate Validator `v,6.1.6.Final`
- Jackson core `v.2.14.1`
- Javax annotation `v.1.3.2`
- Java Servlets API `v.4.0.1`
- Tomcat `v.9.0.73`


### 📩 Contact
[Mariana Polishchuk](https://www.linkedin.com/in/mariana-polishchuk-42b049206/) <br>
tonksmaryan@gmail.com