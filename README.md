# Chi Squared Test

In this section, we will explore how to determine the correlation between two categorical variables and assess their significance.
Here is the data that we have consist of 50 rows:

<img width="819" alt="chi-1" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/3f330a4d-2c8b-4a92-a88c-ee1d6e645bae">

We'll examine the correlation between 'age status' and 'drink' to assess their mutual significance. To analyze this, we will conduct a chi-squared test manually (by hand) and by using Python.

# Manually (By Hand)

First, we need to summarize the data into frequency distributions for each group. This step makes it easier to calculate.

<img width="1073" alt="chi-2" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/ce42512c-1746-42ed-8417-1c3d3f7a7dc4">

**Expected Value**
The chi-squared test determines the significance between two variables by comparing them to their expected values. Expected values indicate the frequencies we would anticipate in each cell of a contingency table if there were no association between the variables (i.e., if they were independent). The formula for expected value is provided below.

<img width="742" alt="chi-3" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/b45d9256-fd4a-460d-9b60-6ea338a20cdc">

If you find the formula confusing, consider this example: 

<img width="1154" alt="chi-3 copy" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/ab567cc0-56ba-4b40-b50a-79c1b44c5a99">

Suppose we want to find the expected value of adults who drink coffee. We use the total number of coffee drinkers (R<sub>i</sub>), total number of adults (C<sub>j</sub>), and the overall total number of observations (N).

We calculate the expected value for each group:
•	Adults who drink coffee
•	Adults who drink milk 
          ⋮
•	Teens who drink milk
•	Teens who drink soda

<img width="1432" alt="chi-4" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/30fd4b50-2bb4-4348-a2da-7ebb09265183">


Here’s the expected value for each group. 

<img width="1434" alt="chi-5" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/50d23fda-903b-4504-ab21-d0b170601aa9">

These expected values allow us to compare them with the observed values. Some values may significantly differ from the expected values, while others may closely align.

Next, we compute the chi-squared value using the following formula:

<img width="1435" alt="chi-6" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/ccddfecc-dd50-4b3f-854c-24f07533d251">








