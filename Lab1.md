1. Створити змінні базових (atomic) типів. Базові типи: character, numeric, integer, complex, logical.
integer, complex, logical.
> char <- 'character'  
> numeric <- 4.14  
> int <- 1L  
> complex <- 5 + 5i  
> logical <- TRUE  
2. Створити вектори, які: містить послідовність з 5 до 75; містить числа 3.14, 2.71, 0, 13; 100 значень TRUE.
> v <- c(5:75)  
> [1]  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
[26] 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54
[51] 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75  
> v1 <- c(3.14, 2.71, 0, 13)  
> [1]  3.14  2.71  0.00 13.00  
> v2 <- c(100, TRUE)  
> [1] 100   1  
3. Створити наступну матрицю за допомогою matrix, та за допомогою cbind або rbind
> x <- c(0.5, 1.3, 3.5)  
> y <- c(3.9, 131, 2.8)  
> z <- c(0, 2.2, 4.6)  
  >c <- c(2, 7, 5.1)  
> rbind(x, y, z, c)  
> [,1]  [,2] [,3]  
x  0.5   1.3  3.5  
y  3.9 131.0  2.8  
z  0.0   2.2  4.6  
c  2.0   7.0  5.1  
4. Створити довільний список (list), в який включити всі базові типи.
> list_data <- list('char', 4.14, 5L, TRUE, 5i)  
> [[1]]  
[1] "char"  

[[2]]  
[1] 4.14  

[[3]]  
[1] 5  

[[4]]  
[1] TRUE  

[[5]]  
[1] 0+5i  
5. Створити фактор з трьома рівнями «baby», «child», «adult».  
> data_factor <- c('baby', 'child', 'adult')  
> factor_data <- factor(data_factor)  
> [1] baby  child adult  
Levels: adult baby child  
6. Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. Знайти кількість значень NA.
> v3 <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)  
> min(which(is.na(v3)))  
> [1] 5  
7. Створити довільний data frame та вивести в консоль.
> data_frame <- data.frame(id = c(1:5), digits = c(1:5))  
> print(data_frame)  
> id digits  
1  1      1  
2  2      2  
3  3      3  
4  4      4  
5  5      5  
8. Змінити імена стовпців цього data frame.
> colnames(data_frame) <- c("new_id", "new_digit")  
 new_id new_digit  
1      1         1  
2      2         2  
3      3         3  
4      4         4  
5      5         5  
