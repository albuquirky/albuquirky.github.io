# Current State

## Current State Implementation

* 

## Known Deficiencies

* 

## Testing Progress

* 

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
    * View composition &and; serialization
        * Jackson JSON
        * Custom view classes &and; interfaces
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