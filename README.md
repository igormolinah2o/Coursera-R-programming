# Coursera-R-programming
Module 2 DATA SCIENTIST SPECIALIZATION
WEEK 3 QUIZ
1) Take a look at the 'iris' dataset that comes with R. The data can be loaded with the code:
library(datasets)
data(iris)
A description of the dataset can be found by running
?iris
There will be an object called 'iris' in your workspace. In this dataset, what is the mean of 
'Sepal.Length' for the species virginica? Please round your answer to the nearest whole number.
(Only enter the numeric result and nothing else.)
--- ANSWER: 7 ---
> library(datasets)
> data(iris)
> ?iris
> head(iris)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa

> tapply(iris$Sepal.Length, iris$Species, mean)
    setosa versicolor  virginica 
     5.006      5.936      6.588 
# Using Apply to aggregate column means

2) Continuing with the 'iris' dataset from the previous Question, what R code returns a vector 
of the means of the variables 'Sepal.Length', 'Sepal.Width', 'Petal.Length', and 'Petal.Width'?
> apply(iris,1, mean)
  [1] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
 [38] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
 [75] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
[112] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
[149] NA NA
There were 50 or more warnings (use warnings() to see the first 50)
> rowMeans(iris[,1:4])
  [1] 2.550 2.375 2.350 2.350 2.550 2.850 2.425 2.525 2.225 2.400 2.700 2.500 2.325 2.125 2.800 3.000 2.750 2.575
 [19] 2.875 2.675 2.675 2.675 2.350 2.650 2.575 2.450 2.600 2.600 2.550 2.425 2.425 2.675 2.725 2.825 2.425 2.400
 [37] 2.625 2.500 2.225 2.550 2.525 2.100 2.275 2.675 2.800 2.375 2.675 2.350 2.675 2.475 4.075 3.900 4.100 3.275
 [55] 3.850 3.575 3.975 2.900 3.850 3.300 2.875 3.650 3.300 3.775 3.350 3.900 3.650 3.400 3.600 3.275 3.925 3.550
 [73] 3.800 3.700 3.725 3.850 3.950 4.100 3.725 3.200 3.200 3.150 3.400 3.850 3.600 3.875 4.000 3.575 3.500 3.325
 [91] 3.425 3.775 3.400 2.900 3.450 3.525 3.525 3.675 2.925 3.475 4.525 3.875 4.525 4.150 4.375 4.825 3.400 4.575
[109] 4.200 4.850 4.200 4.075 4.350 3.800 4.025 4.300 4.200 5.100 4.875 3.675 4.525 3.825 4.800 3.925 4.450 4.550
[127] 3.900 3.950 4.225 4.400 4.550 5.025 4.250 3.925 3.925 4.775 4.425 4.200 3.900 4.375 4.450 4.350 3.875 4.550
[145] 4.550 4.300 3.925 4.175 4.325 3.950
> append(iris[,1:4],2,mean)
Error in !after : invalid argument type
> apply(iris[,1:4],2,mean)
Sepal.Length  Sepal.Width Petal.Length  Petal.Width 
    5.843333     3.057333     3.758000     1.199333 
> apply(iris,2,mean)
Sepal.Length  Sepal.Width Petal.Length  Petal.Width      Species 
          NA           NA           NA           NA           NA 
Warning messages:
1: In mean.default(newX[, i], ...) :
  argument is not numeric or logical: returning NA
2: In mean.default(newX[, i], ...) :
  argument is not numeric or logical: returning NA
3: In mean.default(newX[, i], ...) :
  argument is not numeric or logical: returning NA
4: In mean.default(newX[, i], ...) :
  argument is not numeric or logical: returning NA
5: In mean.default(newX[, i], ...) :
  argument is not numeric or logical: returning NA
> apply(iris[,1:4],1,mean)
  [1] 2.550 2.375 2.350 2.350 2.550 2.850 2.425 2.525 2.225 2.400 2.700 2.500 2.325 2.125 2.800 3.000 2.750 2.575
 [19] 2.875 2.675 2.675 2.675 2.350 2.650 2.575 2.450 2.600 2.600 2.550 2.425 2.425 2.675 2.725 2.825 2.425 2.400
 [37] 2.625 2.500 2.225 2.550 2.525 2.100 2.275 2.675 2.800 2.375 2.675 2.350 2.675 2.475 4.075 3.900 4.100 3.275
 [55] 3.850 3.575 3.975 2.900 3.850 3.300 2.875 3.650 3.300 3.775 3.350 3.900 3.650 3.400 3.600 3.275 3.925 3.550
 [73] 3.800 3.700 3.725 3.850 3.950 4.100 3.725 3.200 3.200 3.150 3.400 3.850 3.600 3.875 4.000 3.575 3.500 3.325
 [91] 3.425 3.775 3.400 2.900 3.450 3.525 3.525 3.675 2.925 3.475 4.525 3.875 4.525 4.150 4.375 4.825 3.400 4.575
[109] 4.200 4.850 4.200 4.075 4.350 3.800 4.025 4.300 4.200 5.100 4.875 3.675 4.525 3.825 4.800 3.925 4.450 4.550
[127] 3.900 3.950 4.225 4.400 4.550 5.025 4.250 3.925 3.925 4.775 4.425 4.200 3.900 4.375 4.450 4.350 3.875 4.550
[145] 4.550 4.300 3.925 4.175 4.325 3.950
> colMeans(iris)
Error in colMeans(iris) : 'x' must be numeric

--- ANSWER: apply(iris[,1:4],2,mean) ---

3) Load the 'mtcars' dataset in R with the following code
library(datasets)
data(mtcars)
There will be an object names 'mtcars' in your workspace. 
You can find some information about the dataset by running
?mtcars
How can one calculate the average miles per gallon (mpg) by number 
of cylinders in the car (cyl)? Select all that apply.

> data(mtcars)
> ?mtcars
> head(mtcars)
                   mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
> mean(mtcars$mpg, mtcars$cyl)
Error in mean.default(mtcars$mpg, mtcars$cyl) : 
  'trim' must be numeric of length one
> sapply(mtcars,cyl, mean)
Error in match.fun(FUN) : object 'cyl' not found
> apply(mtcars,2,mean)
       mpg        cyl       disp         hp       drat         wt       qsec         vs         am       gear 
 20.090625   6.187500 230.721875 146.687500   3.596563   3.217250  17.848750   0.437500   0.406250   3.687500 
      carb 
  2.812500 
> tapply(mtcars$mpg, mtcars$cyl, mean)
       4        6        8 
26.66364 19.74286 15.10000 
> lapply(mtcars,mean)
$`mpg`
[1] 20.09062

$cyl
[1] 6.1875

$disp
[1] 230.7219

$hp
[1] 146.6875

$drat
[1] 3.596563

$wt
[1] 3.21725

$qsec
[1] 17.84875

$vs
[1] 0.4375

$am
[1] 0.40625

$gear
[1] 3.6875

$carb
[1] 2.8125

> with(mtcars, tapply(mpg,cyl,mean))
       4        6        8 
26.66364 19.74286 15.10000 
> sapply(split(mtcars$mpg, mtcars$cyl),mean)
       4        6        8 
26.66364 19.74286 15.10000 
> tapply(mtcars$cyl, mtcars$mpg, mean)
10.4 13.3 14.3 14.7   15 15.2 15.5 15.8 16.4 17.3 17.8 18.1 18.7 19.2 19.7   21 21.4 21.5 22.8 24.4   26 27.3 30.4 
   8    8    8    8    8    8    8    8    8    8    6    6    8    7    6    6    5    4    4    4    4    4    4 
32.4 33.9 
   4    4 
> split(mtcars, mtcars$cyl)
$`4`
                mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Datsun 710     22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
Merc 240D      24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
Merc 230       22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
Fiat 128       32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
Honda Civic    30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2
Toyota Corolla 33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1
Toyota Corona  21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1
Fiat X1-9      27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1
Porsche 914-2  26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2
Lotus Europa   30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2
Volvo 142E     21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2

$`6`
                mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Mazda RX4      21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag  21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
Hornet 4 Drive 21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1
Valiant        18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1
Merc 280       19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4
Merc 280C      17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4
Ferrari Dino   19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6

$`8`
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8

--- ANSWER: tapply(mtcars$mpg, mtcars$cyl, mean) // with(mtcars, tapply(mpg,cyl,mean)) 
            // sapply(split(mtcars$mpg, mtcars$cyl), mean) ---

4) Continuing with the 'mtcars' dataset from the previous Question, what is the absolute 
difference between the average horsepower of 4-cylinder cars and the average horsepower of 8-cylinder cars?
(Please round your final answer to the nearest whole number. Only enter the numeric result and nothing else.)

--- ANSWER: 126.5779 ---

> abs(mean(mtcars$hp[mtcars$cyl==4])-mean(mtcars$hp[mtcars$cyl==8]))
[1] 126.5779
#another possible answer it could be
> x <- with(mtcars, tapply(hp, cyl, mean))
> abs(x[3] - x[1])
[1] 126.5779
>new <- tapply(mtcars$hp, mtcars$cyl, mean)
>round(abs(new[3]-new[1]))
[1] 127
#Using the built in looping tapply function to aggregate and then round/abs.

5) If you run
debug(ls)
what happens when you next call the 'ls' function?
a- Execution of 'ls' will suspend at the beginning of the function and you will be in the browser.
b- The 'ls' function will execute as usual.
c- The 'ls' function will return an error.
d- You will be prompted to specify at which line of the function you would like to suspend execution and enter the browser.

--- ANSWER: a- Execution of 'ls' will suspend at the beginning of the function and you will be in the browser. ---

debug(ls)
ls()
# You will be prompted to specify at which line of the function 
# you would like to suspend execution and enter the browser.
debugonce()
# when you need to quit the status debug
# type help at the Browse[]>
# Debug walks through each block of code to identify errors and bugs.
