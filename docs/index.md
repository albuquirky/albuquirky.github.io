## Summary

AlbuQuirky is an online art gallery for Android devices. Artists, crafters, builders, and creators of all sorts in the Albuquerque area can use it to display and offer for sale the things they make to other Albuquerque residents. It will also serve as an online showroom for their creations in perpetuity.

This app was conceptualized as a response to concern for independent artists in Albuquerque. Old Town is an iconic location in this city, and there are always dozens of indepedent crafters and artists lined up along the streets and walkways of Old Town displaying and selling their work, as well as countless small shops doing the same. COVID-19 hit fast and hard, and with seemingly no end in sight, it's hard to imagine how these creators are able to get their products into the hands of those that wish to buy them. AlbuQuirky was intended as a solution to this problem, allowing local crafters a platform through which they can sell their goods.

After creating an account, users will be able to create galleries for their art. For those so inclined, they will also be able to offer these art pieces for sale. Buyers are also able to commission artists for unique custom pieces, and each artist can specify a number of waitlist slots for commissions, which the app will keep track of and notify the next user "in-line" to have their commission reviewed by the artist for consideration. For those that have sold a product, the app will allow the seller to choose how the buyer will receive their purchase &dash; either by parcel shipping through UPS and/or FedEx, or via delivery by the artist or pick-up by the buyer, with delivery scheduling and fulfillment confirmation by both parties handled in the app.

You can view a PDF version of the AlbuQuirky project summary [here](pdf/albuquirky-project-summary.pdf).

## Team Roster

* Tyler Baum - UI/UX Design
    * [Email](mailto:tyler.baum@protonmail.com)
    * [GitHub](https://github.com/AugmenTab)
    * [LinkedIn](https://www.linkedin.com/in/thebaum)
* Ricky Garcia - Documentation and Technical Writing
    * [Email](mailto:rickyg08@msn.com)
    * [GitHub](https://github.com/rickyG08)
    * [LinkedIn](https://www.linkedin.com/in/rickyg08)
* John Jaramillo - Authorization and Security
    * [Email](mailto:jjaramillo1221@gmail.com)
    * [GitHub](https://github.com/John-Jaramillo)
    * [LinkedIn](https://www.linkedin.com/in/john-jaramillo-5172521b3)
* Justin Kelly - REST Controllers and Server Wiring
    * [Email](mailto:jmkelly2041@gmail.com)
    * [GitHub](https://github.com/Jkelly97)
    * [LinkedIn](https://www.linkedin.com/in/justin-kelly-1070311b6)

## Intended Users

* People who like to sell things in flea markets or on the street, but are unable to due to COVID-19.

    > As an Albuquerque jewelrymaker, I need a service that can provide resiliency to my handmade jewelry business so that I can continue selling locally in case another lockdown happens.

* People who want accountability and security when dealing with customers or selling services.

    > As a creator of unique art products, getting cheated on a sale can cost me a lot of my time and money. I need a service that has ways of preventing dishonest conflicts between me and my buyers built in, so I can protect myself from potential theft.

* People who want to be able to provide supporting products to the things they sell.

    > As a painter, I need a service that will allow me to sell prints long after my one-of-a-kind paintings have been sold, so that I can get more value out of my work.

* People whose products are too cumbersome to display publicly.

    > As a custom furniture maker, I need an app that allows me to schedule deliveries for my purchased wares so I don't have to drag them around town displaying them.

## Client Component

* **Functionality**

    * Users will be able to create a profile, making them an authenticated user. This allows them to create and purchase products, and request commissions.
    * Through dedicated pages, the user will be able to manage products, orders, and commissions.
    * The seller will be able to add items to their profile, which will function as an art gallery. All products they have ever posted will be listed on their profile, which allows users to buy them (by contacting the user to arrange the purchase) and commission the artist for them.
    * Sellers can also list lesser products that are related to a gallery item, like prints for one-off paintings or spare hardware for a furniture piece.
    * Sellers can choose to either deliver the product to the customer themselves, allow the customer to pick up their purchases, or offer shipping.
        * If they choose delivery, they can schedule a time and place to deliver the item. Both the seller and the buyer must agree, and the app will automatically notify the buyer when the seller is at the delivery location. It will not mark the item delivered until both devices confirm the delivery has occurred to everyone's satisfaction.
        * If they choose pickup, they can schedule a time and place to pick up the item. Both the seller and the buyer must agree, and the app will automatically notify the seller when the buyer is at the pickup location. It will not mark the item picked up until both devices confirm the pickup has occurred to everyone's satisfaction.
        * If they choose shipping, the app will automatically calculate shipping costs based on package dimensions and weight using an API service.
    * The seller can choose to accept commissions. This will use a waitlist (which persists even when commissions are closed), with a number of positions set by the seller that autofill on a first-come, first-served basis. If someone withdraws from the waitlist, an item is marked complete, or is rejected by the seller, the waitlist will advance and notify the next person on the waitlist (who can either submit their commission request or choose to withdraw from the waitlist). If commissions are switched off, the waitlist is preserved for the commissions the seller has committed to, but nothing advances beyond the incomplete slots. Completed slots are closed and shut.
        * Example: A seller wants to do three commissions. The first three waiters on the waitlist automatically populate the freshly-opened commission slots (if applicable). If rejected or withdrawn by either party, the waitlist will shift up to fill the empty slots. When the first slot is marked complete, it will close, and the waitlist will not shift, unless the seller opens up additional waitlist slots.

* **Persistent Data**

    * Information about accepted scheduled pick up or delivery times, commission details, and shipping details will be stored locally in case of loss of connection to data/internet services, so that they can still be honored as agreed upon.

* **Device/External Services**

    * Device Services
        * This app will use the [Camera](https://developer.android.com/guide/topics/media/camera#:~:text=%20Camera%20API%20%201%20Saving%20media%20files.,fields%20that%20require%20permission.%20LENS_POSE_REFERENCE%20LENS_INFO_HYPERFOCAL_DISTANCE...%20More%20) to take photos of items to sell.
        * This app will use the user's preferred [Calendar](https://developers.google.com/calendar/) app to schedule delivery and pick-up times.
    * External Services
        * [Google Maps API](https://developers.google.com/maps/documentation/android-sdk/overview) will be used to set delivery and pick-up locations. The app will still be able to function if access to this service is unavailable - scheduling deliveries and pick-ups will simply be suspended until access is restored.
        
## Server Component

* **Functionality**

    * Currently, there is one planned role for authenticated accounts on the server:
        * Users browsing without an account do not have a role, so they only have access to search and browse artists, view galleries, and read comments and feedback.
        * Authenticated accounts will be able to do everything an unauthenticated user can do as well as comment on items, rate artists, purchase items for sale, request commissions, list items in their gallery, and open commissions, in addition to all of the privileges they had before as an unauthenticated user.
    * The server will store all information on the accounts, gallery items, products, and feedback.
    * The server will keep track of an artist's waitlist and send notifications to the waiters.
    * The server will handle all notifications to the users regarding pick-up and delivery.
    * The server will handle calculating shipping details using the chosen API(s) and generating labels for the seller, as well as notifications for the buyer.

* **Persistent Data**

    * Customer accounts
    * Gallery items and products
    * Comments, rating, and other feedback

* **External Services**

    * Either the [FedEx](https://www.fedex.com/en-us/developer.html) or [UPS](https://www.ups.com/us/en/services/technology-integration/developer-api.page) API (or both) will be used to manage the shipping. The app will still be able to function if access to this service is unavailable, but will be unable to accurately calculate shipping costs or permit the seller to print shipping labels.
    * [Google OAuth 2.0](https://developers.google.com/identity/protocols/oauth2) will be used to handle authentication. The app will be unable to permit users to sign in if this service were to become unavailable, though artist galleries would still be viewable, as would anything else that does not require an account.
    * [Picasso](https://square.github.io/picasso/) will be used to handle image presentation. The app will be unable to display images for products or users if this service were to become unavailable.
    
## Wireframe

* [Wireframe](wireframe.md)

## Current Implementation State

* [Current State](current-state.md)

## Server-Side Design and Implementation

* [Server-Side Design and Implementation](server-side/index.md)

## Client-Side Design and Implementation

* [Client-Side Design and Implementation](client-side/index.md)

## Authentication Scheme

* [Authentication Scheme](authentication-scheme.md)

## Stretch Goals/Possible Enhancements 

* Currently, payment buttons will be a placeholder and will not function as intended. I would like to eventually add payment through the app itself using [Square](https://developer.squareup.com/docs/sdks/java) or [Stripe](https://stripe.com/docs/api).
* I would like to incorporate social media integration, allowing sellers and buyers alike to post about products on Facebook, Twitter, and Instagram, and have it link back to the product page.
* I would like to possibly incorporate all three major shipping service providers as opposed to just one.
* I would like to add the option for sellers to sell their products as an auction as opposed to just a direct sale.
* I would like to add the option for users to favorite art pieces.