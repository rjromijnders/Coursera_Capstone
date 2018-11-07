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
Neighborhood information is scraped from a Wikipedia webpage. Whenever the Borough is 'Not assigned', it is left out of the data. Whenever there is a Borough, but the Neighborhood is 'Not assigned', the Neighborhood is set to equal the Borough. If in one Postal code there exist more Neighborhoods, then these Neighborhoods are combined into one record for the Postal code (the Neighborhoods are joined together, and separated with a comma).

Geographical coordinates are obtained from a provided *.csv*-file. Dataframes are merged together.

Information about nearby venues for each Neighborhood is obtained via the Foursquare API. An additional pandas dataframe is instantiated to exist of the Neighborhood and a one-hot coded score for each Venue Category. Rows are grouped by neighborhood and by taking the mean of the frequency of occurrence of each Venue Category. The dataframe is sorted on the top 3 venues for each Neighborhood. Subsequently the records for which 'Coffee Shop' occurs in the top 3 are removed.

Using **folium** the resulting neighborhoods are plotted on a map of Toronto, from which possible locations for opening a new coffee shop are derived.

## Results
Filtering the results of the Toronto venues such that 'Coffee Shop' is not among the top 3 venues results in 17 possible location for opening a new coffee shop.
![Image of Possible Locations](https://github.com/rjromijnders/Coursera_Capstone/blob/master/Coffee_Shop_locations.jpg)

The results are plotted on the map of Toronto to visualize their respective locations:
![Image of Possible Locations](https://github.com/rjromijnders/Coursera_Capstone/blob/master/Coffee_Shop_locations_map.jpg)


## Discussion
17 possible locations for opening a new coffee shop are found by looking up information about nearby venues for the Toronto neighborhoods. The best neighborhood was defined as the Neighborhood where the occurence of coffee shops is not in the top three venues, and that is closest to the city center. Using these selection criteria the following Neighborhoods are highlighted for possible locations:
- Chinatown, 
- Grange Park,
- Kensington Market,
- Downtown Toronto

## Conclusion
Four locations are promising Neighborhoods for opening a new coffee shop: Chinatown, Grange Park, Kensington Market, Downtown Toronto. These locations were selected because of the absence of coffee shops in the top 3 venues, and the proximity to the city center. It is suggested to further research these Neighborhoods regarding -amongst others- permits for opening a new Coffee Shops, the ease of transportation (in- and outflow of coffee by trucks?) and the numbers of possible visitors.
