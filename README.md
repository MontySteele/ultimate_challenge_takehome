# ultimate_challenge_takehome

Here is my work for the Ultimare Data Science Challenge detailed in 'ultimate_data_science_challenge.pdf'.

### Take home challenge summary, part 1

In this part of the take-home challenge, I was given a json file, 'logins.json', containing login data for a group of users. I was asked to aggregate this user login data into 15-minute time intervals and perform exploratory data analysis to find trends in the login data.

My work is available in the file 'Ultimate_challenge_takehome_p1.ipynb'. 

### Part 1 results

I found that login counts are increasing over time in this dataset, increasing from January onward and seeming to peak in mid-March, although there is little data for February. 

Logins were lowest on Monday, gradually rising to a peak on Saturday and then dipping slightly on Sunday. On an hourly bases, logins follow a cyclical pattern of peaking around noon and midnight and being lowest in the morning and evening.

## Plots of my data. showing hourly, per-weekday, weekly and monthly data trends.

|                 |                 |
| -------------  | -------------   |
| ![Hourly data.](graphs/hourlyData.png?raw=true "Hourly data")| ![Per-weekday data.](graphs/weekdayData.png?raw=true "Per-weekday data") |
| ![Weekly data.](graphs/weeklyData.png?raw=true "Weekly data")| ![Monthly data.](graphs/MonthlyData.png?raw=true "Monthly data")   |

### Take home challenge summary, part 2

In this part of the take-home challenge, I was given a hypothetical business experiment and asked to find a metric that would explain whether this experiment was successful, as well as how to analyze and interpret my chosen metric to make business recommendations.

### Part 2 results

In this project, the goal of the Ultimate managers is to encourage drivers to spend their time in both cities, not just one or the other. We want a metric that will tell us if drivers are spending their time in both cities. This metric should rate poorly if the drivers spend all their time in one city, and highly if they are equally dividing their time between the two cities.

We will begin assuming that all rides begin in one of the two cities. Then we can easily get a metric, G_rides, which is the percent of all rides that begin (passenger is picked up) in Ultimate Gotham. I chose Ultimate Gotham for this bit, but either city could be used - the math is the same.

We will then calculate a new metric, Equality, calculated using G_rides. Equality = (100% - 2*abs(G_rides - 50%)).

Equality reflects the distribution of how drivers spend their time between the cities. If all of a drivers' rides begin in Ultimate Gotham, G_rides = 100% and Equality = 0%. Likewise, if all of a drivers' rides begin in Ultimate Metropolis, G_rides = 0% and Equality = 0%. If rides between the two cities are equally balanced, G_rides = 50% and Equality = 100%.

I like Equality because the value of Equality is intuitive after being calculated. A low Equality is bad, a high Equality is good, and there is a straightforward linear relationship that governs Equality.

As a practical experiment, I would offer occasional promotions that give full reimpursements to drivers for toll fares. This promotion would occasionally be phased in and out, which would allow me to compare the value of Equality during multiple separate time phases. That way I can avoid having my data thrown off by special events that may drive up interest in cross-city traffic in only one time period, and give greater statistical robustness to my analysis.

For example. I might offer this toll reimbursement on alternating weeks so that I can compare the values of Equality with and without the promotion. Once the data is collected, I can calculate the value of Equality for every driver who drove during this period. Assuming some large number of drivers were active during multiple periods, I can then track changes in the value of Equality with and without the promotions among this group of drivers. I can conduct significance tests to find the confidence interval that my promotion is successfully increasing Equality as well as the average increase in Equality when the promotion is active.

I would interpret my results by seeing whether there is a statistically significant increase in the value of Equality during the period when the promotion is active, as well as quantifying the change. by multiplying the average driver's increase Equality by the average number of rides during the promotion period, I can get a measurement of how many additional rides were started in their opposite city because of the promotion.

Example: (Equality increases by 20%) * (15 average rides) = 3 additional rides started in their less-commonly-visited city.

In addition, it would be important to track the total amount of available drivers, the average number of rides started per driver and the average amount of revenue earned per driver during this experiment. While the goal of this experiment is technically not to make a profit, it would be rather self-defeating to create a promotion that succeeds in increasing the equality of rides between cities but also loses money overall on reimbursing toll costs, or that somehow diminishes availability by reducing the number of available drivers overall.

### Take home challenge summary, part 3

In this part of the take-home challenge, I was given a json file, 'ultimate_data_challenge.json', containing data from a group of users that signed up in a particular month. I was asked to explore this data, create a model that could predict 6-month user retention and then make recommendations based on my model.

My work is available in the file 'Ultimate_challenge_takehome_p3.ipynb'. 

### Part 3 results

I found that 37.6% of the users in the dataset were retained
