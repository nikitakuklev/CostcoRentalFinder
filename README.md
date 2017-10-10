## CostcoRentalFinder
Parser/crawler of Costco travel car rentals - provides a sorted list of prices/distances/locations

### How it works
It uses **requests** python library to mimic an actual client, and with appropriate parsing of cookies and other things obtains rental prices for specified options

Insipiration:  [this post](https://www.codebyamir.com/blog/pushing-price-alert-notifications-with-aws-lambda-sns-and-nodejs) (but I am using the newer rentalCarSearch.act page, which allow to search by zip, and supply appropriate 'Csrf-token' cookie)

### But why???
Because Costco has great prices, but they vary a lot due to taxes and other things, and you can only compare 4 locations at a time. This makes things easier. Also...we do what we must because we can.
