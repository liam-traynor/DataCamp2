# (PART) DataCamp {-} 

# Introduction to R

<https://learn.datacamp.com/courses/free-introduction-to-r>

<span style="color:teal;font-weight:bold">(Note: If you do [Introduction to R for Finance](https://learn.datacamp.com/courses/introduction-to-r-for-finance) instead, change the title of this bookdown chapter above and change the DataCamp chapter titles below. Whichever version of Intro to R you do, delete this note)</span>



## Intro to basics
### Modulo %% get the remainder
### Assign Variables x <- etc
### Add Variables together with operations
my_apples <- 5
my_oranges <- 6
my_apples + my_oranges -> my_fruit
my_fruit
### check class with class(etc.)




## Vectors
### create vector with c() the combine function
boolean_vector <- c(TRUE, FALSE, TRUE)
### can also assign numeric values
### can name vectors
my_vector <- c(35, 45)
names(my_vector) <- c("Liam", "Traynor")
### can save time by naming things vectors
### like making a days vector in stead of typing out the days of the week everytime
### Can act on vector values using operations
A_vector <- c(1, 2)
B_vector <- c(3, 4)
total_vector <- A_vector + B_vector
total_vector
### Example
### Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

### Assign to total_daily how much you won/lost on each day
total_daily <- poker_vector + roulette_vector
total_daily
### Can use greater than or less than symbols
brick_vector <- c(1, 2)
taco_vector <- c(3, 4)
sum(brick_vector) < sum(taco_vector)
### gives the response true
### can select specific items from vectors using brackets
sleep_vector <- c(6, 7, 8, 7, 8)
sleep_vector[3]
### gives the answer 8
### can specify multiple by putting [c(etc.)]
sleep_vector[c(1, 3, 5)]
### gives answer 6 8 8
### can use colon so select every value between the numbers
names(sleep_vector) <- days_vector
sleep_vector[3:5]
### brings up wednesday thursday friday 8 7 8
### can get the mean of a set of values by doing mean(etc.)
mean(sleep_vector)
### gives the answer 7.2
### can use comparison operators < for less than
### > for greater than <= for less than or equal to >= for greater than or equal to == for equal to each other != not equal to each other
sleep_vector[1:5] >= 7
### Returns with Falst True True True True
### can put vectors in brackets
selection_vector <- sleep_vector[1:5] > 7
sleep_vector[selection_vector] -> goodsleep_vector
goodsleep_vector
### returns with wednesday and friday both with values of 8



## Matrices
### Construct a matrix with 3 rows that contain the numbers 1 up to 9
matrix(1:9, byrow = TRUE, nrow = 3)
### The first argument is the collection of elements that R will arrange into the rows and columns of the matrix. Here, we use 1:9 which is a shortcut for c(1, 2, 3, 4, 5, 6, 7, 8, 9).
### The argument byrow indicates that the matrix is filled by the rows. If we want the matrix to be filled by the columns, we just place byrow = FALSE.
### The third argument nrow indicates that the matrix should have three rows.
# Box office Star Wars (in millions!)
new_hope <- c(460.998, 314.4)
empire_strikes <- c(290.475, 247.900)
return_jedi <- c(309.306, 165.8)
### Create box_office
box_office <- c(new_hope, empire_strikes, return_jedi)
### Construct star_wars_matrix
star_wars_matrix <- matrix(box_office, byrow = TRUE, nrow = 3)
star_wars_matrix
### can use vectors to name columns and rows
regions <- c("US", "non-US")
titles <- c("A New Hope", "The Empire Strikes Back", "Return of the Jedi")
colnames(star_wars_matrix) <- regions
rownames(star_wars_matrix) <- titles
star_wars_matrix
### can use rowSums() to sum row data
rowSums(star_wars_matrix) -> worldwide_vector
worldwide_vector
### returns with worldwide totals for each movie
### can bind new columns to matrices with cbind()
cbind(star_wars_matrix, worldwide_vector) -> allwars_matrix
allwars_matrix
### result is original matrix with worldwide totals added
### can add rows to matrices using rbind(etc.)
### would look like rbind(star_wars_matrix, prequel_matrix) -> all_wars_matrix
### all_wars_matrix would run with the prequel data added on
### can use colSums to sum column data
total_revenue_vector <- colSums(star_wars_matrix)
total_revenue_vector
### total revenue for the two columns is added up
### can use brackets to take data from specific parts of a matrix
### right side of the comma is for columns and the left side is for rows
star_wars_matrix[,2] -> non_us_matrix
non_us_matrix
star_wars_matrix[1:2,2] -> non_us_some
non_us_some
### that last bit only used the first two rows and the second column
### can apply mathematical operations to matrices
star_wars_matrix / 5 -> visitors
visitors
### divides all of the matrix data by 5
### can use mathematical operations to have matrices act on one another

## Factors
### The term factor refers to a statistical data type used to store categorical variables. The difference between a categorical variable and a continuous variable is that a categorical variable can belong to a limited number of categories. A continuous variable, on the other hand, can correspond to an infinite number of values.
### us the functon factor(etc.) to act on vectors
### A nominal variable is a categorical variable without an implied order. This means that it is impossible to say that 'one is worth more than the other'. For example, think of the categorical variable animals_vector with the categories "Elephant", "Giraffe", "Donkey" and "Horse". Here, it is impossible to say that one stands above or below the other. (Note that some of you might disagree ;-) ).
### In contrast, ordinal variables do have a natural ordering. Consider for example the categorical variable temperature_vector with the categories: "Low", "Medium" and "High". Here it is obvious that "Medium" stands above "Low", and "High" stands above "Medium".
### using summary(etc.) will give you a brief overview of the contents of a variable
survey_vector <- c("M", "M", "F", "F", "M")
factor_survey_vector <- factor(survey_vector)
levels(factor_survey_vector) <- c("Female", "Male")
factor_survey_vector 
summary(factor_survey_vector)
### speed_vector should be converted to an ordinal factor since its categories have a natural ordering. By default, the function factor() transforms speed_vector into an unordered factor. To create an ordered factor, you have to add two additional arguments: ordered and levels.
### Create speed_vector
speed_vector <- c("medium", "slow", "slow", "medium", "fast")

### Convert speed_vector to ordered factor vector
factor_speed_vector <- factor(speed_vector, ordered = TRUE, levels = c("slow", "medium", "fast"))

### Print factor_speed_vector
factor_speed_vector 
summary(factor_speed_vector)

## Data frames
### matrices where there is more than one type of info represented
### head() and tail()
### using str() allows you to see the structure or what is the make up of the data set
### create vectors and use them to create a data.frame()
### can use [] to get specific info from data frames
### can use $ as a short cut if you want all the data in a column
### can use subset() to get info from data frame
### subset(planets_df, subset = etc.)
### can have operators like greater than less than symbols etc. when specifying subset
### can use order() to order values

## Lists
### can make a list using list()
my_list <- list(my_vector, my_matrix, my_df)
### .
my_list
### can name items on the list
names(my_list) <- c("etc")
###  can select components using [[etc]] or with using $
### [[]] refers to the larger section of the list and you can follow that with[] to get a specific part of that sub section
### Use the table from the exercise to define the comments and scores vectors
scores <- c(4.6, 5, 4.8, 5, 4.2)
comments <- c("I would watch it again", "Amazing!", "I liked it", "One of the best movies", "Fascinating plot") 

### Save the average of the scores vector as avg_review  
avg_review <- mean(scores)

### Combine scores and comments into the reviews_df data frame
reviews_df <- data.frame(scores, comments)

### Create and print out a list, called departed_list
departed_list <- list(movie_title, movie_actors, reviews_df, avg_review)
 departed_list

## End of notes