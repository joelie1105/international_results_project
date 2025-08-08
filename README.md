# international_results_project

## Project Overview
This project's goal is to give the reader a quick visual of the changing size of the World Cup over the life of the tournament as it expanded, a heat map of the highest goal scorers in the World Cup with a focus on the top 20, countries that had the most matches in the history of the tournament, a block of code to check the win/loss/draw record of each country that made the World Cup, orders the most goals scored by countries in the World Cup, and lastly examines the average number of shootouts along with the number of shootouts in each World Cup tournament closing with a visual of the number of shootouts for each tournament. The closer the games get to modern time, the more information is included in the data. Because the World Cup is such a large tournament there is more data allowing for an analysis without many null values.

## Virtual Environment Directions
 | Command    |           Linux/Mac             |    Git Bash                      |
 |------------|---------------------------------|----------------------------------|
 | Create     | python3 -m venv venv            | python -m venv venv              |
 | Activate   | source venv/bin/activate        | source venv/Scripts/activate     |
 | Install    | pip install -r requirements.txt | pip install -r requirements. txt |
 | Deactivate | deactivate                      | deactivate                       |


The packages required for this program include:
    - pandas
    - numpy
    - matplotlib.pyplot
    - seaborn

## Libraries

This projects requires the libraries pandas, numpy, sqlite3, matplotlib.pyplot, matplotlib.cm, and seaborn

Jupyter Notebooks was used to provide a clean section of code blocks and organize the code in a fashion that allowed for easier reading.

Sqlite3 was used to join tables in order to checking results and shootouts in the World Cup.

Pandas was used to clean the data and alongside pythons groupby methods helped extract only World Cup games. 

For the visuals matplotlib.pyplot and seaboarn were used for plotting the cleaned data. 


## Data Dictionary

### results.csv
| Column Name  | Data Type | Description                    |
|--------------|-----------|--------------------------------|
| 'date'       | Date      | Match date                     |
| 'home_team'  | Object    | Home team for the match        |
| 'away_team'  | Object    | Away team for match            |
| 'home_score' | Int64     | Home team score                |
| 'away_score' | Int64     | Away team score                |
| 'tournament' | Object    | Name of the tournament         |
| 'city'       | Object    | City where match was played    |
| 'country'    | Object    | Country where match was played |

### shootouts.csv
| Column Name     | Data Type    | Description                          |
|-----------------|--------------|--------------------------------------|
| 'date'          | 'datetime64' | Match date                           |
| 'home_team'     | Object       | Home team for the match              |
| 'away_team'     | Object       | Away team for the match              |
| 'winner'        | Object       | Team that won the shootout           |
| 'first_shooter' | Object       | Team that went first in the shootout |

### goalscorers.csv
| Column Name     | Data Type    | Description                          |
|-----------------|--------------|--------------------------------------|
| 'date'          | 'datetime64' | Match date                           |
| 'home_team'     | Object       | Home team for the match              |
| 'away_team'     | Object       | Away team for the match              |
| 'team'          | Object       | Name of the team scoring the goal    |
| 'scorer'        | Object       | Name of the player score the goal    |
| 'minute'        | float64      | Game minute of goal scored           |
| 'own_goal'      | bool         | whether the goal was an own-goal     |
| 'penalty'       | bool         | whether the goal was a penalty       |






According to the original compiler of the data, there are 47,960 results of international soccer/football matches from 1872 - 2024. The person that compiles the data updates it regularly with many of the updates taking place in recent weeks or months as matches take place. 


