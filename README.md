# international_results_project

According to the original compiler of the data, there are 47,960 results of international soccer/football matches from 1872 - 2024. The person that compiles the data updates it regularly with many of the updates taking place in recent weeks as additional matches take place. 

# Data Dictionary

## results.csv
| Column Name  | Data Type | Description
|--------------|-----------|---------------
| 'date'       | Date      | Match date
| 'home_team'  | Object    | 

## shootouts.csv

## goalscorers.csv






results.csv includes the following columns:
- date - date of the match
- home_team - name of the home team
- away_team - name of the away team
- home_score - the final score of the home team(includes extra time, but excludes any penalty shootouts.)
- away_score - the final away team score(includes extra time, but excludes any penalty shootouts.)
- tournament - the name of the tournament
- city - the name of the city or town of the match
- country - the name of the country where the match was played
- neutral - A TRUE/FALSE column that identifies in the match was played at a neutral stadium

shootouts.csv include the following columns
- tournament - the name of the tournament
- city - the name of the city or town of the match
- country - the country where the match was played
- neutral - A TRUE/FALSE column that identifies if the match took place a neutral stadium

goalscorers.csv - includes the following columns
- date - the date of the match
- home_team - the name of the home team
- away_team - the name of the away team
- team - the name of the team scoring the goal
- scorer - name of the player scoring the goal
- own_goal - whether the goal was an own-goal
- penalty - whether the goal was a penalty


The project initially analyzes the number of countries that have participated in the World Cup tournament and counts the win and loss totals of the countries.

There is a list that has the number of shootouts per country and a graph to display those results. 


