# The Battle of Neighborhoods
## Introduction
AMSTERDAM COFFEE wants to open a new coffee shop somewhere in Toronto, Canada. However, for it to be profitable they want to explore which neighborhood would be most suitable. Therefor the aim of this project is to find the best neighborhood for opening a new coffee shop.

We try to answer the following research question:
> What neighborhood is most suitable for opening a new coffee shop?

The best neighborhood for opening a new coffeeshop is defined as the Toronto neighborhood where the occurence of coffee shops is not in the top three venues, and that is closest to the city center.

## Data
The first part of our data consists of the different postal codes, borough and neighborhoods in Toronto. This information is scraped from a <a href="https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M">Wikipedia page</a>. After processing the data will be in the format of a pandas dataframe with the PostalCode, Borough, and Neighborhood for each record.

The second part of the data  comprises the geographical coordinates for each neighborhood. This data is obtained from a .csv file, and is processed with pandas *csv_read* method. After processing the data will be in the format of a pandas dataframe with the PostalCode, Latitude, Longitude for each record. The dataframe is merged with the former to obtain a pandas dataframe consisting of PostalCode, Borough, Neighborhood, Latitude, Longitude for each record.

To plot the nearby venues on the map of Toronto, data is collected via the Foursquare API. The data concerns all kinds of venues in the Toronto area, and is structured per borough and per neighborhood. The result is a pandas dataframe with Neighborhood, Neighborhood Latitude, Neighborhood Longitude, Venue, Venue Latitude, Venue Longitude, Venue Category for each category.

## Methodology
Methodology section which represents the main component of the report where you discuss and describe any exploratory data analysis that you did, any inferential statistical testing that you performed, and what machine learnings were used and why.

## Results
Results section where you discuss the results.

## Discussion
Discussion section where you discuss any observations you noted and any recommendations you can make based on the results.

## Conclusion
Conclusion section where you conclude the report.
