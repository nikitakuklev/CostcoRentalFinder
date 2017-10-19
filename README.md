## CostcoRentalFinder
Parser/crawler of Costco travel(CT) car rentals - provides a sorted list of prices/distances/travel times/locations

### How it works
It uses **requests** python library to mimic an actual client, and with appropriate parsing of cookies and other things obtains CT rental prices within a given radius of a zipcode. To speed up the crawling process, **asyncio** library is used with an executor threadpool (reimplementation with a true async network/crawler library is on the TODO list).

For each location, **GMaps distance matrix API** is then used to find the expected travel time using public transport.

Price and travel time metrics are used to rank locations, presenting a list of optimal ones to explore further.

Insipiration:  [this post](https://www.codebyamir.com/blog/pushing-price-alert-notifications-with-aws-lambda-sns-and-nodejs) (but using the newer rentalCarSearch.act page, which allows to search by zip and requires appropriate 'Csrf-token' cookie)

### Motivation
Use case - student without a car, who sometime feels like renting one for roadtrips/shopping/etc. Zipcar is the typical solution, but too expensive and limited in miles for these purposes. Exploring the various search engines, it became clear CT had good deals and more importantly aggregated many agencies together. However, since you can only compare 4 locations at a time (with hundreds in chicagoland area), and the prices swing wildly, it would be way too painful to try and find deals manually. Hence this script.

Typically, after running it, one would then use sites like autoslash to try to find better (vs Costco) coupons/codes, and book directly with rental company at one of optimal locations. AFAIK CT-price based rankings are still correct in this case, since all coupons operate on the same base fare - what is cheapest on CT will remain so with better discounts.
