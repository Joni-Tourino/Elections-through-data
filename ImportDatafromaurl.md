While looking at the recent data for early voters in the [2020 US General Election](https://electproject.github.io/Early-Vote-2020G/index.html), I wanted to focus my research for a possible story on the two states with the highest numbers: Virginia and Wisconsin.
My primary idea is to see if somehow, I could make a comparison between 2016 and 2020’s numbers, with a daily adjustment, as the numbers come out.
Since my primary source only displays maps with the numbers of early voters, I won’t be able to use it to gather the data needed. Probably the biggest problem for doing so with each state, is that I’ll have to search for 50 (at the moment only 16) different state pages.
I found Wisconsin’s case quite interesting since they don’t seem to use CSV or XLS files, but rather display the tables directly on the website. I’ll use it to show you **a function that is specific to Google Drive**:

=IMPORTHTML

First you’ll need to open the [Elections and Voting Statistics from Wisconsin](https://elections.wi.gov/index.php/elections-voting/statistics) where you’ll find different data sets related to previous and current elections. We’ll start first with this year’s numbers which you can find under “Absentee Voting Statistics” and as you can see, it’s updated every day. For the purposes of this tutorial, the search I made was for the date 09/30/20 (in the US, the month comes first). But if you prefer, you can use another date.

Once you created a new spreadsheet on Google Drive, you’ll have to type the following fuction (preferably on the first row and column):

=IMPORTHTML("https://elections.wi.gov/node/7142"; "table"; 1)

- **The first entry** is for the url
- **the second** is for the type of structure (either a list or a table)
- **the last one** is the index (= which table, if there’s more than one, you want to copy). In this scenario, there’s only one table to copy, so you'll have to enter 1.

Then you want to do the same but for the 2016 Election. There will be a lot of entries named “Absentee Ballot Report”, so carefully look for the last one of November 2016. This time we have more than one table. Given that the one we already copied also as a classification by county, we’ll need the fourth table.

The process is the same as before but with the according corrections both in the url and the number. It’s better to import this data on another sheet, to avoid any mix-up.

=IMPORTHTML("https://elections.wi.gov/node/4414"; "table"; 4)

Once you have those two sheets, you can compare the ballots returned between the two elections. Obviously, the 2020 is still ongoing but you can easily update it by changing part of the url in your function, without having to repeat this process every day. You won’t even have to open the page, since the structure is the same, the only thing that changes are the numbers for each county.

**The second problem** I encountered was, how do I compare the numbers if I have them on separate sheets?

**The solution is to use the VLOOKUP function.**

What I want to bring to my 2020 General Election sheet is the column named *Ballots Returned Count* to the main spreadsheet by using the VLOOKUP function:

=VLOOKUP(A2;'2016 General Election Total'!A:C;3;FALSE)

- A2 = Adams County; this is the value I want to look up
- 2016 General Election Total!A:C = this is the name of my second sheet and the columns I’m looking for, starting with the counties
- 3 = it’s the number of the column (here I have three: A, B and C) I want to bring back to my sheet
- FALSE = If you want an exact match, always write FALSE.

Last but not least, I want to see the percentage change between those two with the following function:

=SUM(NEW-OLD)/OLD

NEW is the number for 2020, whereas OLD is the number for 2016.

If you use Google’s spreadsheet, it should automatically give you the result in a percentage, otherwise make sure you change it.

And now you’re set up to daily update your spreadsheet, almost automatically, with a single change of numbers in the first url.

**The final result** should look like this one (the name of the sheet will tell you which date I used):

https://docs.google.com/spreadsheets/d/1twdxjMsA-shaF-kct8ZAfPMc-uk6rGtAnJDaI2yxHfo/edit#gid=0
