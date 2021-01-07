# (PART) DataCamp {-} 

# Introduction to R

<https://learn.datacamp.com/courses/free-introduction-to-r>

<span style="color:teal;font-weight:bold">(Note: If you do [Introduction to R for Finance](https://learn.datacamp.com/courses/introduction-to-r-for-finance) instead, change the title of this bookdown chapter above and change the DataCamp chapter titles below. Whichever version of Intro to R you do, delete this note)</span>



## Intro to basics
#Modulo %% get the remainder
#Assign Variables x <- etc
#Add Variables together with operations
my_apples <- 5
my_oranges <- 6
my_apples + my_oranges -> my_fruit
my_fruit
#check class with class(etc.)



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



## Matrices


## Factors


## Data frames


## Lists