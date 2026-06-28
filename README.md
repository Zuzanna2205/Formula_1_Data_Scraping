# Formula_1_Data_Scraping
As the 2024 Formula 1 season comes to an end, now is the perfect time to take a closer look at the data
gathered during the 24 races of the season. This analysis focuses primarily on drivers—their successes
and failures—but also examines constructors and other elements that are crucial to the world of Formula
1.
## Data Sources
The data used in this project comes from three different sources:
1. **Ergast API:** Accessed through the ```ergast-py``` library, which offers comprehensive data about the
Formula 1 2024 season.
2. **Wikipedia API:** Accessed via the ```wikipediaapi``` library, providing structured information from
Wikipedia.
3. **StatsF1 Website:** A rich repository of Formula 1 data available at StatsF1. This data was collected
using the BeautifulSoup library for web scraping.
## Ethical Considerations Regarding Data Sources
### 1. Ergast API
As mentioned on the Ergast website under the Terms & Conditions section, the API may be used for
“personal, non-commercial applications and services including educational and research purposes.”
Moreover, it is prohibited to charge money for applications or services that utilize this API, and each user
is obligated to use it responsibly in accordance with the rules and regulations provided on the website.
The purpose of this project is strictly educational, and no money will be charged to recipients of this
project. Furthermore, every use of the Ergast-py API was carefully analyzed in terms of compliance with
the regulations to ensure that all rules are respected—particularly the rules limiting API calls to no more
than 4 requests per second and 200 requests per day.
Taking into account all the aspects listed above, I (as the author) do not have any ethical objections to
the use of the API in this project and firmly believe that it aligns with both the letter and the spirit of the
regulations governing its use.
### 2. Wikipedia API
As stated on the official Wikimedia Foundation website in the "API Terms" section, they provide an
official set of APIs that are publicly available to “promote free knowledge.” Additionally, for individuals
interested in using Wikipedia APIs, a comprehensive set of guidelines is available. These guidelines
include, for example, respecting request limits and ensuring that requests are sent sequentially rather
than in parallel.
This project clearly falls under the category of promoting knowledge. While using the Wikipedia API, I
have taken great care to adhere to these guidelines and utilize the API as recommended by its creators.
Furthermore, I believe that my use of the API aligns with the ethical principles outlined by the Wikimedia
Foundation and my personal ethics. I find this use to be free from any ethical or moral controversy.
### 3. StatsF1.com Website
Before gathering data, the ```robots.txt``` file was carefully reviewed to ensure compliance with the
website's guidelines. The file explicitly permitted access to all catalogues and subcatalogues for all users
except for a few specified bots. Since no restrictions were mentioned that would prohibit data extraction
using BeautifulSoup, I concluded that accessing the data in this manner aligns with the website's policies.
Therefore, I find no ethical objections to using BeautifulSoup for this purpose.
## Dataset
The dataset created for this research ```df_f1_final_data``` contains 23 rows. Each row corresponds to
one driver who participated in the 2024 Formula 1 season. The DataFrame includes the following
variables:
## Variables from Ergast_py API

**Position** (type: ```int```):
The overall position of the driver in the 2024 season.

**Driver_Name** (type: ```string```):
The driver’s full name.

**Points** (type: ```float```):
The number of points collected by the driver throughout the 2024 season.

**Wins** (type: ```int```):
The number of races won by the driver during the season.

**Constructor** (type: ```string```):
The name of the team the driver competed for in 2024.

**Positions** (type: ```list[int]```):
A list of positions achieved by the driver in all 24 races, ordered chronologically (note: some drivers
did not participate in every race, so their lists are shorter than 24).

**Grids** (type: ```list[int]```):
A list of starting grid positions for each race, ordered chronologically (note: some drivers did not
participate in every race, so their lists are shorter than 24).

**Statuses** (type: ```list[string]```):
A list indicating the race status (finished/not finished) for each race in 2024 (note: some drivers did
not participate in every race, so their lists are shorter than 24).

**Top_10_Finishes_Count** (type: ```int```):
The number of races in which the driver finished in the top 10. This is important because drivers
earn points only for the top 10 finishes.

**Total_Races_Count** (type: ```int```):
The number of races each driver participated in during the 2024 season, based on the Positions
variable.

**Top_10_Finish_Percentage** (type: ```float```):
The percentage of races in which the driver finished in the top 10 ( Top_10_Finishes_Count /
Total_Races_Count * 100%). This provides a fair metric for comparing drivers' performances,
accounting for differences in participation.

**Finished_Races_Count** (type: ```int```):
The number of races completed by the driver in the season, based on the Statuses variable.

**Finished_Races_Percentage** (type: ```float```):
The percentage of races completed by each driver, based on the Finished_Races_Count variable.

**Most_Frequent_Starting_Position** (type: ```int```):
The most common starting grid position for the driver, based on the Grids variable.

**Pole_Positions_Count** (type: ```int```):
The number of pole positions achieved (i.e., starting a race in 1st place), based on the Grids
variable.

**Won_At_Least_One_Race** (type: ```int```):
A binary variable indicating whether the driver won at least one race ( 1 = yes, 0 = no ), based
on the Positions variable.
Variables from Wikipedia API

**Driver_Name** (type: ```string```):
The driver’s full name.

**Wiki_Summary** (type: ```string```):
The first 100 characters of the driver’s Wikipedia summary.

**Wiki_URL** (type: ```string```):
The URL of the driver’s Wikipedia page.

**Wiki_Categories** (type: ```list[string]```):
Categories listed on the driver’s Wikipedia page.

**Wiki_Languages_Count** (type: ```int```):
The number of languages the driver’s Wikipedia page is available in.

**Processed_Wiki_Summary** (type: ```string```):
A processed version of the Wikipedia summary, converted to lowercase and stripped of non-words.

**Word_Frequency** (type: ```dictionary```):
A count of each word in the Processed_Wiki_Summary .

**Most_Common_Wiki_Word** (type: ```string```):
The most frequently occurring word in the Processed_Wiki_Summary .

**Most_Common_Wiki_Word_Count** (type: ```int```):
The number of times the most common word appears in the Processed_Wiki_Summary .
Variables from StatsF1 Website

**Driver_Name** (type: ```string```):
The driver’s full name.

**Championship_Titles** (type: ```int```):
The number of championship titles the driver has won.

**Is_Champion** (type: ```int```):
A binary variable indicating whether the driver has won a championship title ( 1 = yes, 0 = no ).

**First_GP_Year** (type: ```string```):
The year the driver first participated in Formula 1.

**Years_Of_Experience** (type: ```int```):
The number of years the driver has participated in Formula 1, based on the First_GP_Year
variable.

**Nationality** (type: ```string```):
The driver’s nationality.

**Driver_Number** (type: ```int```):
The driver’s official racing number.
