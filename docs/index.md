## Summary

AlbuQuirky is an online art gallery for Android devices. Artists, crafters, builders, and creators of all sorts in the Albuquerque area can use it to display and offer for sale the things they make to other Albuquerque residents. It will also serve as an online showroom for their creations in perpetuity.

After creating an account, users will be able to create galleries for their art. For those so inclined, they will also be able to offer these art pieces for sale, though all purchases and transactions will take place outside the app. Buyers are also able to commission artists for unique custom pieces, and each artist can specify a number of waitlist slots for commissions, which the app will keep track of and notify the next user "in-line" to have their commission reviewed by the artist for consideration. For those that have sold a product, the app will allow the seller to choose how the buyer will receive their purchase - currently, options include parcel shipping through UPS and/or FedEx, as well as delivery by the artist or pick-up by the buyer, with delivery scheduling handled in the app.

## Team Roster

* Tyler Baum
* Ricky Garcia
* John Jaramillo
* Justin Kelly

## Intended users

* People who like to sell things in flea markets or on the street, but are unable to due to COVID-19.

    > As an Albuquerque jewelrymaker, I need a service that can provide resiliency to my handmade jewelry business so that I can continue selling locally in case another lockdown happens.

* People who want accountability and security when dealing with customers or selling services.

    > As a creator of unique art products, getting cheated on a sale can cost me a lot of my time and money. I need a service that has ways of preventing dishonest conflicts between me and my buyers built in, so I can protect myself from potential theft.

* People who want to be able to provide supporting products to the things they sell.

    > As a painter, I need a service that will allow me to sell prints long after my one-of-a-kind paintings have been sold, so that I can get more value out of my work.

* People whose products are too cumbersome to display publicly.

    > As a custom furniture maker, I need an app that allows me to schedule deliveries for my purchased wares so I don't have to drag them around town displaying them.

## Client component

* **Functionality**

    * Unauthenticated users will be able to browse and search for artists, view item galleries, and read comments and feedback left to artists by other users.
    * Users will be able to create a profile, making them an authenticated user. This allows them to comment on items, rate artists, and request commissions.
    * Through the options menu, a user will be able to display and get feedback on the things they've made, as well as manage commissions.
    * The seller will be able to add items to their profile, which will function as an art gallery. All products they have ever posted will be listed on their profile, which allows users to buy them (by contacting the user to arrange the purchase), comment on them, and even commission the artist for them.
    * Sellers can also list lesser products that are related to a gallery item, like prints for one-off paintings or spare hardware for a furniture piece.
    * Sellers can choose to either deliver the product to the customer themselves, allow the customer to pick up their purchases, or offer shipping.
        * If they choose delivery, they can schedule a time and place to deliver the item. Both the seller and the buyer must agree, and the app will automatically notify the buyer when the seller is at the delivery location. It will not mark the item delivered until both devices confirm the delivery has occurred to everyone's satisfaction.
        * If they choose pickup, they can schedule a time and place to pick up the item. Both the seller and the buyer must agree, and the app will automatically notify the seller when the buyer is at the pickup location. It will not mark the item picked up until both devices confirm the pickup has occurred to everyone's satisfaction.
        * If they choose shipping, the app will automatically calculate shipping costs based on package dimensions and weight using an API service.
    * The seller can choose to accept commissions. This will use a waitlist (which persists even when commissions are closed), with a number of positions set by the seller that autofill on a first-come, first-served basis. If someone withdraws from the waitlist, an item is marked complete, or is rejected by the seller, the waitlist will advance and notify the next person on the waitlist (who can either submit their commission request or choose to withdraw from the waitlist). If commissions are switched off, the waitlist is preserved for the commissions the seller has committed to, but nothing advances beyond the incomplete slots. Completed slots are closed and shut.
        * Example: A seller wants to do three commissions. The first three waiters on the waitlist automatically populate the freshly-opened commission slots (if applicable). If rejected or withdrawn by either party, the waitlist will shift up to fill the empty slots. When the first slot is marked complete, it will close, and the waitlist will not shift, unless the seller opens up additional waitlist slots.

* **Persistent data**

    * Information about accepted scheduled pick up or delivery times, commission details, and shipping details will be stored locally in case of loss of connection to data/internet services, so that they can still be honored as agreed upon.
    
* **Device/external services**

    * Device Services
        * This app will use the [Camera](https://developer.android.com/guide/topics/media/camera#:~:text=%20Camera%20API%20%201%20Saving%20media%20files.,fields%20that%20require%20permission.%20LENS_POSE_REFERENCE%20LENS_INFO_HYPERFOCAL_DISTANCE...%20More%20) to take photos of items to sell.
        * This app will use the user's preferred [Calendar](https://developers.google.com/calendar/) app to schedule delivery and pick-up times.
    * External Services
        * [Google Maps API](https://developers.google.com/maps/documentation/android-sdk/overview) will be used to set delivery and pick-up locations. The app will still be able to function if access to this service is unavailable - scheduling deliveries and pick-ups will simply be suspended until access is restored.
        
## Server component

* **Functionality**

    * Currently, there is one planned role for authenticated accounts on the server:
        * Users browsing without an account do not have a role, so they only have access to search and browse artists, view galleries, and read comments and feedback.
        * Authenticated accounts will be able to do everything an unauthenticated user can do as well as comment on items, rate artists, purchase items for sale, request commissions, list items in their gallery, and open commissions, in addition to all of the privileges they had before as an unauthenticated user.
    * The server will store all information on the accounts, gallery items, products, and feedback.
    * The server will keep track of an artist's waitlist and send notifications to the waiters.
    * The server will handle all notifications to the users regarding pick-up and delivery.
    * The server will handle calculating shipping details using the chosen API(s) and generating labels for the seller, as well as notifications for the buyer.

* **Persistent data**

    * Customer accounts
    * Gallery items and products
    * Comments, rating, and other feedback
    
* **External services**

    * Either the [FedEx](https://www.fedex.com/en-us/developer.html) or [UPS](https://www.ups.com/us/en/services/technology-integration/developer-api.page) API (or both) will be used to manage the shipping. The app will still be able to function if access to this service is unavailable, but will be unable to accurately calculate shipping costs or permit the seller to print shipping labels.
    * [jBCrypt](https://www.mindrot.org/projects/jBCrypt/) will be the one-way salted hash function used to handle authentication. The app will be unable to permit users to sign in if this service were to become unavailable, though artist galleries would still be viewable, as would anything else that does not require an account.
    
## Current Implementation State

* 

## Wireframe

## Server-Side Design and Implementation

* [Entity-Relationship Diagram](entity-relationship.md)
* [Data Model Implementation](data-model-implementation.md)

## Client-Side Design and Implementation

* 

## Authentication SCheme

## Stretch goals/possible enhancements 

* Currently, payment buttons will be a placeholder and will not function as intended. I would like to eventually add payment through the app itself using [Square](https://developer.squareup.com/docs/sdks/java) or [Stripe](https://stripe.com/docs/api).
* I would like to incorporate social media integration, allowing sellers and buyers alike to post about products on Facebook, Twitter, and Instagram, and have it link back to the product page.
* I would like to possibly incorporate all three major shipping service providers as opposed to just one.
* I would like to add the option for sellers to sell their products as an auction as opposed to just a direct sale.
* I would like to add the option for users to favorite art pieces.