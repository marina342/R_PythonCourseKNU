1. Створити змінні базових (atomic) типів. Базові типи: character, numeric, integer, complex, logical.
integer, complex, logical.
>char <- 'character'
>numeric <- 4.14
>int <- 1L
>complex <- 5 + 5i
>logical <- TRUE
2. Створити вектори, які: містить послідовність з 5 до 75; містить числа 3.14, 2.71, 0, 13; 100 значень TRUE.
>v <- c(5:75)
>v1 <- c(3.14, 2.71. 0, 13)
>v2 <- c(100, TRUE)
3. Створити наступну матрицю за допомогою matrix, та за допомогою cbind або rbind
>x <- c(0.5, 1.3, 3.5)
>y <- c(3.9, 131, 2.8)
>z <- c(0, 2.2, 4.6)
>c <- c(2, 7, 5.1)
> rbind(x, y, z, c)
4. Створити довільний список (list), в який включити всі базові типи.
>list_data <- list('char', 4.14, 5L, TRUE, 5i)
5. Створити фактор з трьома рівнями «baby», «child», «adult».
> data_factor <- c('baby', 'child', 'adult')
> factor_data <- factor(data_factor)
6. Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. Знайти кількість значень NA.
>v3 <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
>min(which(is.na(v3)))
7. Створити довільний data frame та вивести в консоль.
> data_frame <- data.frame(id = c(1:5), digits = c(1:5))
> print(data_frame)
8. Змінити імена стовпців цього data frame.
> colnames(data_frame) <- c("new_id", "new_digit")
