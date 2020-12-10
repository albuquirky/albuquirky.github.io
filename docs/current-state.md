# Current State

## Current State Implementation

* The app current builds and displays the user's profile page successfully.
* They are able to update profile information (username, address, profile picture) and store the updated information to the server.
* `Product` and `Commission` entities can be created successfully using Postman.

## Known Deficiencies

* Only one page currently building and operating as intended on the client side.
* Updating `Profile` information causes the server to store strings with surrounding quotation marks.
* `Order`, `ProductOnOrder`, `Image` entities cannot be posted to the server.

## Aesthetic Improvements

* We would like to design a more intuitive GUI with the use of floating action buttons and a dedicated Options menu.
* We would like to implement pop-out windows for images, expandable `TextView` sections, and other dynamic layout features.
* We would like to make the layouts more consistent in use of cards.
* We would like to experiment with colors and layouts more to give the app its own distinct look.

## Technology Stack

### Back End

* Ubuntu Linux OS
* Apache HTTP server configured as reverse proxy (hosted on Digital Ocean)
* JRE 8
* Apache Tomcat Java application server
* Web service application, incorporating:
    * Data model
        * Embedded Apache Derby database
        * Hibernate ORM
        * Custom entity classes
        * Spring Boot Data
        * Custom data repository interfaces
    * Service controllers
        * Spring MVC
        * Custom controller classes
    * View composition & serialization
        * Jackson JSON
        * Custom view classes & interfaces
    * Authentication
        * Spring Security
        * Google Sign In (external service; see <https://developers.google.com/identity>)
        * Custom authentication verifier method for audience (client ID)
    * Testing
        * JUnit Vintage

### Front End

* Android OS
* Data model
    * SQLite
    * Room ORM
    * Custom entity and other model classes
    * Custom type converters
    * Data access object (DAO) interfaces
* Remote service interfaces
    * Retrofit
    * ReactiveX
    * Google Gson
    * Custom serializer/deserializers
* Viewmodel components
    * Android Lifecycle framework (ViewModel & LiveData)
    * Custom viewmodel classes
* View
    * Custom `RecyclerView.Adapter` and `RecyclerView.Holder` classes
    * Custom `ViewPager` classes
    * Custom layouts using Material Design
* Controller
    * Custom activity and fragment classes
* Authentication
    * Google Sign In (external service; see <https://developers.google.com/identity>)
    * Custom sign in service class
* Testing
    * Stetho
    * OkHttp logging
    * JUnit4
    * Android Espresso