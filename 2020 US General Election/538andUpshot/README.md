# Methodology 

FiveThirtyEight has a tendency to be quite transparent with their data, and it can be easily downloaded either from their own GitHub repository or in this case, at the end of their "[2020 Election Forecast](https://projects.fivethirtyeight.com/2020-election-forecast/)" page. The file used is "Presidential Poll Averages 2020". The other set of information needed, was the final results of the Election, and for that I used [The New York Times](https://www.nytimes.com/interactive/2020/11/03/us/elections/results-president.html?searchResultPosition=10)' one. The calculation was made on 4 December 2020, and thus it is possible that in some states, or at national levels, the margins may have slighty changed, given some ballots were still being counted. But we're talking in a possible range of ±0.1-point change.

In order to decide if their prediction was correct or not, I went with [Dhrumil Mehta](https://youtu.be/TambSayfCOE?t=404)'s numbers: ±4-points statewide, and ±3-point national.
At the end of their 2020 Election Forecast, FiveThirtyEight allows the readers to download two sets of data: Polls and Model outputs. The file that was used for the averages was the one with the presidential poll averages, and the final results come from The New York Times. The margin of error, to decide if the prediction was correct or not, comes from FiveThirtyEight and is situated at a 4-point margin at state level.
To give a fair comparison, the error has be done between the 14-key states calculated by the NYT.

## What each column means

Here, I'll explain what each column, in the [CSV file](./538_vs_Upshot_error_margin.csv) in that same folder, means.

- The first one is the name of the state (in alphabetical order), and it includes both national estimates and Nebraska and Maine's districts (except for Nebraska's 3rd district).
- The second is the average percentage given to Donald Trump
- The third is the average percentage given to Joe Biden
- The fourth is the difference between Trump minus Biden
- The fifth is the the actual result's difference for Donald Trump (if negative, it means he lost the state)
- The sixth is the difference between columns 4 and 5
- The Seventh and eighth show who FiveThirtyEight predicted to win and who actually won
- The ninth is the polling difference the New York Times had if their polling was as wrong as 2016
- The tenth and thirteenth shows if it was accurate
- The eleventh is to show it more easily if it was in the ±4-point range in a state level
- The twelfth shows the NYT's poll average without corrections

