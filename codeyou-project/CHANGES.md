# Changes to the World Cup notebook

All numbers below use the same copy of the data as the original run (the June 11, 2025 version of the dataset: 48,335 matches). Every change in the notebook is marked with a `# Fix:` comment.

## 1. The World Cup join now matches on date AND both teams

- **Before:** the join that adds shootout winners to World Cup matches matched on the date only. If two shootouts happened anywhere in the world on the same day as a World Cup match, that match got copied. The table had 970 rows, and 1986, 2018, and 2022 each showed 2 extra matches (54, 66, 66).
- **After:** it matches on date, home team, and away team. The table has 964 rows, one per World Cup match (1986 = 52, 2018 = 64, 2022 = 64).
- **Check added:** the notebook prints the number of World Cup matches before the join (964) and the number of rows after (964), and stops with an error if they ever differ.
- **Why it mattered:** the extra copies quietly inflated everything built on this table: matches per country (Brazil 116 → 114), total goals (Brazil 239 → 237, Argentina 154 → 152), and the win/loss/draw records.
- The earlier "join results with shootouts" cell had the same date-only problem: it produced 4,118 rows by pairing each shootout with every match that day. It now gives 646 rows, one per shootout (one shootout, a 2011 Saare County vs. Åland Islands match, isn't in the results file).

## 2. "Shootouts per World Cup" now counts real shootouts

- **Before:** the code counted every match in each tournament and called them shootouts. It reported an average of 44.09 shootouts per World Cup and, for example, 64 shootouts in 1998.
- **After:** it counts only matches where a shootout winner is listed. There were 35 shootouts in all, an average of 1.59 per World Cup, none before 1982, and never more than 5 in one tournament (2022).
- **Why it mattered:** a reader would take the chart at face value. The bar and line charts and their titles now show real shootouts. The match counts per tournament are still printed, now with the correct label.

## 3. The count of unique countries no longer double counts

- **Before:** it added the number of different home teams to the number of different away teams, so a country that was ever both home and away was counted twice: 159 countries.
- **After:** it combines both lists first and then counts each country once: **82 countries** have played in a World Cup.
- **Why it mattered:** 159 is almost double the real number, and someone who knows soccer would spot it.

## 4. Shootout wins are now recorded correctly in the win/loss/draw records

- **Before:** one line compared the home team's *score* (a number) to the home team's *name*, which can never match. Any home team that won a shootout was recorded as a draw.
- **After:** it compares the shootout *winner* to the home team, as the next line already did for away teams.
- **Example (France, with fixes 1 and 4 together):** 1982 went from 3-2-2 to 3-3-1 (lost the semifinal on penalties), 1998 from 6-0-1 to 7-0-0 (beat Italy on penalties), and 2022 from 5-1-1 to 5-2-0 (lost the final on penalties).

## 5. Smaller cleanups

- A comment said "Example usage to get results for Brazil" but the code looks up the United States. The comment now says United States.
- Removed 11 empty code cells at the end of the notebook.
- Re-ran the whole notebook from top to bottom so every saved output and chart matches the fixed code. The five chart images were regenerated.
- For the saved run, the "Enter a country name" box was answered with France, same as the original output. When you run it yourself, it will still ask you to type a country.

## 6. Files added or updated

- `requirements.txt` (new): pandas, numpy, matplotlib, seaborn, jupyter, so `pip install -r requirements.txt` works as the README says.
- `README.md`: fixed "seaboarn" and "requirements. txt", reworded the shootouts description so it describes the fixed analysis, updated the data size line, and added a Data Source section crediting Mart Jürisoo's public dataset.
- `.gitignore`: now also ignores `your_database.db` (the notebook rebuilds it every run) and Jupyter checkpoint folders.

## Things that did not change

- Countries per tournament: 13 (1930), 16 (most of 1934–1978), 24 (1982–1994), 32 (1998–2022). This was already right.
- The top 20 scorers heat map. Leaders: Miroslav Klose 16, Ronaldo 15, Gerd Müller 14, Just Fontaine 13, Lionel Messi 13, Pelé 12, Kylian Mbappé 12.

## A note on newer data

The dataset keeps growing. With the October 2026 version, the fixed notebook still runs cleanly, but it adds the 2026 World Cup: 48 countries, 104 matches, and 4 more shootouts (39 total, average 1.70), with 86 countries overall. This repository keeps the June 2025 files so the numbers above stay the same.
