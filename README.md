# Humana-Healthcare

This project looks at healthcare data fro m the HUMANA insurance company. I explore trends from Florida customer during March 2023. Using Power Query, I transformed the data to make it more useful. 

1. Created a new column to combine county name and state as one string.
2. To find the percentage of people who have Humana in each of the counties, I created another custom formula dividing COUNT by MMA TOTAL. Allowing me to easily identify overall market share. 
     --   Overall Market Share = SUM(data[Count])/SUM(data[MMA Total])   --
3. Inserted an additional slicer with a new measure using an IF statement. This lets the slicer know what color each county shold be based on the overall market share.

     Slicer Measure = IF([Overall Market Share] > 0.25, "#3CEA2C", -- if greater than 25%
                    IF([Overall Market Share] <= 0.25 && [Overall Market Share] > 0.15,  "#F0e199", -- if between 15% and 25% 
                    "#D64550" -- for all other cases (less than or equal to 15%)
                    ))

