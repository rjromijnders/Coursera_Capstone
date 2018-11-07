# The Battle of Neighborhoods
## Introduction
AMSTERDAM COFFEE wants to open a new coffee shop somewhere in Toronto, Canada. However, for it to be profitable they want to explore which neighborhood would be most suitable. Therefor the aim of this project is to find the best neighborhood for opening a new coffee shop.

We try to answer the following research question:
> What neighborhood is most suitable for opening a new coffee shop?

The best neighborhood for opening a new coffeeshop is defined as the Toronto neighborhood where the occurence of coffee shops is not in the top three venues, and that is closest to the city center.

## Data
The first part of our data consists of the different postal codes, borough and neighborhoods in Toronto. This information is scraped from a <a href="https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M">Wikipedia page</a>. 

The second part of the data  comprises the geographical coordinates for each neighborhood. This data is obtained from a .csv file, and is processed with pandas *csv_read* method.

To plot the nearby venues on the map of Toronto, data is collected via the Foursquare API. The data concerns all kinds of venues in the Toronto area, and is structured per borough and per neighborhood.
