# DATA-TRANSFORMATION-BASIC-STATISTICS-AND-VISUALISATION-IN-R
Task 1: Data transformation 
Dataset used for this task: who in the tidy package – This is a dataset containing
tuberculosis (TB) cases broken down by year, country, age, gender, and diagnosis
method. Note that this is a dataset embedded in package tidy so there is no need to
import it from anywhere else.
You are asked to transform the who dataset by following 6 steps:
1.  Gather together all the columns from new_sp_m014 to newrel_f65
o Use pivot_longer()
o We do not know what those values represent yet, so we give them the
generic name as "key" (hint: names_to)
o We know the cells represent the count of cases, so we use the variable
“cases” (hint: values_to)
o There are a lot of missing values in the current representation, so for now we
use values_drop_na just so we can focus on the values that are present.
o Name the new dataset who1
2.  Make variable names consistent
Instead of newrel we have new_rel. It is hard to spot this here but if you do not fix it,
we will get errors in subsequent steps.
o Use stringr::str_replace() in strings: replace the characters “newrel” with
“new_rel”.
o Name the dataset who2
3.  Run the following code
whο3 <- who2 %>% separate(key, c("new", "type", "sexage"), sep = "_")
Now you get a dataset who3. Comment this line of code. What is the purpose of
using %>%.
4.  Separate sexage into sex and age: Use the function separate(). Name the
dataset who4
5.  Print the first 5 rows and the last 5 rows of the dataset who4 to the
screen.
6.  Export who4 as an csv file and save it in your local directory.

7.  Task 2: Basic Statistics for Data Science in R
For this task, we’ll use the built-in R dataset named "Nile" - no need to download
any data.
Q1. Compute the mean, median, mode, variance and standard deviation of the dataset (5
marks)
Q2. Compute how “spread out” the data are. Here you need to calculate the minimum,
maximum and range .
Q3. Calculate the interquartile (IQR) range (1 mark). Use the function quantile() to
measure quantiles for the same dataset, and comment on the difference and relation of
these two functions. 
Q4. Use the in-built R basic functions (no need to import any library) to create a
histogram. Make sure you add the following arguments: 
main: Figure it out what the dataset is about, and then add a title for this plot to reflect
what the Nile dataset is about (avoid label it as Nile) as well as the type of the plot
created.
xlab: Add a meaningful label for the x axis
ylab: Add a meaningful label for the y axis
col: set a colour of the bars
Q5. Use qqnorm() and qqplot()to produce quantile-quantile plot.
You will need to set the reference line colour as red, and its width as 2 (2 marks).
Interpret the plot (what are the points, and what is the purpose of the line?) and comment
on normality of the dataset .
Q6. Use plot() to further explore the dataset including arguments such as xlab, ylab, main
and type.

Task 3 :Visualisation with ggplot2 
Dataset
The dataset mpg used in this task is a data frame and can be found in the package
ggplot2 (aka ggplot2::mpg).
For all three tasks, you will need to provide
• code used to generate the plot
• high resolution plot with title, and labels for x, y axes
• answers to questions based on plot interpretation
Q1. Plot and explain: Which vehicle brand (or manufacturer), offers the best mpg in both
city and in the highway? 
Q2. Plot and explain: Which type of car, regarding their displ range (size of engine) has
the lowest mpg in the city categorised by the vehicle type (e.g., compact, suv or 2seaters
defined in the variable class)? Display the resulting plot categorised by the vehicle type. (6
marks) Hint: facet_wrap() for the categorisation
Q3. Plot and explain: Which type of car, regarding their displ range (size of engine) has
the best mpg performance in both city and highway? Display the resulting plot categorised
by the number of cylinders and the drive type (the type of drive train, where f = front-wheel
drive, r = rear wheel drive, 4 = 4wd). You are a buyer who wants a high litre engine vehicle
and drives mostly in the highway, which type of car would you choose? 
Hint: facet_grid() for the categorisation
