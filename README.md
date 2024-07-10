# Chi Squared Test

In this section, we will explore how to determine the correlation between two categorical variables and assess their significance.
Here is the data that we have consist of 50 rows:

<img width="819" alt="chi-1" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/3f330a4d-2c8b-4a92-a88c-ee1d6e645bae">

We'll examine the correlation between 'age status' and 'drink' to assess their mutual significance. To analyze this, we will conduct a chi-squared test manually (by hand) and by using Python.

# Manually (By Hand)

First, we need to summarize the data into frequency distributions for each group. This step makes it easier to calculate.

<img width="1073" alt="chi-2" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/ce42512c-1746-42ed-8417-1c3d3f7a7dc4">

**Expected Value**<br>
The chi-squared test determines the significance between two variables by comparing them to their expected values. Expected values indicate the frequencies we would anticipate in each cell of a contingency table if there were no association between the variables (i.e., if they were independent). The formula for expected value is provided below.

<img width="742" alt="chi-3" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/b45d9256-fd4a-460d-9b60-6ea338a20cdc">

If you find the formula confusing, consider this example: 

<img width="1154" alt="chi-3 copy" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/ab567cc0-56ba-4b40-b50a-79c1b44c5a99">

Suppose we want to find the expected value of adults who drink coffee. We use the total number of coffee drinkers (R<sub>i</sub>), total number of adults (C<sub>j</sub>), and the overall total number of observations (N).

We calculate the expected value for each group:<br>
•	Adults who drink coffee<br>
•	Adults who drink milk<br> 
                              ⋮<br>
•	Teens who drink milk<br>
•	Teens who drink soda<br>

<img width="1116" alt="chi-4" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/70b6efb9-b62b-4405-a52c-7d31d89138df">

Here’s the expected value for each group. 

<img width="1434" alt="chi-5" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/50d23fda-903b-4504-ab21-d0b170601aa9">

These expected values allow us to compare them with the observed values. Some values may significantly differ from the expected values, while others may closely align.

Next, we compute the chi-squared value using the following formula:

<img width="1435" alt="chi-6" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/ccddfecc-dd50-4b3f-854c-24f07533d251">

This formula compares each observed value with its corresponding expected value. Finally, we sum these values to obtain the chi-squared statistic.

<img width="1206" alt="chi-8" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/1307a73b-9f76-447a-bd1a-e8742a7fe980">

To determine the significance of the chi-square test, we compare the calculated chi-square value with the critical chi-square value. 
- If the chi-square value is greater than or equal to the critical chi-square value, we reject the null hypothesis, indicating a significant correlation between the variables.
- If the chi-square value is less than the critical chi-square value, we fail to reject the null hypothesis, suggesting no significant correlation between the variables.

To obtain the critical chi-square value, we first need to determine the degrees of freedom (df) using this formula:

<img width="1267" alt="chi-9" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/bcf68527-d600-4623-ae4e-defe6109d8bc">
<img width="1435" alt="chi-10" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/4962465b-f80f-4993-a703-faefac112471">

So the degrees of freedom (df) that we have is 2 and using a significance level of 0.05, the critical chi-square value is 5.991. Since our calculated chi-square value exceeds 5.991, we reject the null hypothesis, indicating a significant correlation between the variables.

<img width="833" alt="chi-11" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/9f70604c-929a-495f-a462-12c11079e695">

# By Python

In Python, we can use the `crosstab()` function from the pandas library to transform data into a frequency table. To create this table, we call the `crosstab` function and pass the variables for which we want to find the significance. 

<img width="332" alt="Screenshot 2024-07-10 at 06 57 27" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/268f3cab-553b-412c-b0e6-cbcd4a2d42d7">

The `margins` parameter determines whether to add totals for each group. Setting `margins=False` means no subtotal row or column is added, whereas `margins=True` includes subtotals. In our example, we set `margins=False`, so there are no subtotals. We save this frequency table in the `data_crosstab` variable.

Next, we can simultaneously find the expected frequencies, chi-square value, degrees of freedom, and p-value using the `chi2_contingency` function from the `scipy.stats` library.

<img width="617" alt="Screenshot 2024-07-10 at 07 01 07" src="https://github.com/selbydiva/chi-squared-test/assets/154320650/203d68df-338b-4f98-8de3-c7bad6d87a93">

Significance can be determined by comparing the chi-square value with the critical chi-square value, as in the manual method, or more conveniently by looking at the p-value.

- If the p-value is less than the significance level, we reject the null hypothesis, indicating a significant correlation between the variables.
- If the p-value is greater than or equal to the significance level, we fail to reject the null hypothesis, suggesting no significant correlation between the variables.

Since our p-value result is less than the significance level (0.05), we reject the null hypothesis, indicating a significant correlation between the variables.














