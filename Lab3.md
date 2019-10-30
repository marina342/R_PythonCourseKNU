1. Функція add2(x, y), яка повертає суму двох чисел
> add2 <- function(x, y) {
    sum <- sum(x, y)
    sum
}
> res <- sum(1, 2)
2. Функція above(x, n), яка приймає вектор та число n, та повертає всі елементі вектору, які більше n. По замовчуванню n = 10.
> above <- function(x, n = 10) {
     res <- which(x > n)
     res
}
> vector <- c(1:20)
>above(vector)
3. Функція my_ifelse(x, exp, n), яка приймає вектор x, порівнює всі його елементи за допомогою exp з n, та повертає елементи вектору, які відповідають умові expression. Наприклад, my_ifelse(x, “>”, 0) повертає всі елементи x, які більші 0. Exp може дорівнювати “<”, “>”, “<=”, “>=”, “==”. Якщо exp не співпадає ні з одним з цих виразів, повертається вектор x.
> my_ifelse <- function (x, exp, n) {
     if(exp == "<") {
         res <- which(x < n)
     }
     else if(exp == ">") {
         res <- which(x > n)
     }
     else if(exp == "<="){
         res <- which(x <= n)
     }
     else if(exp == ">="){
         res <- which(x >= n)
     }
     else if(exp == "=="){
         res <- which(x == n)
     }
     else res <- x
     res
}
> res <- my_ifelse(c(1:20), ">", 6)
> res <- my_ifelse(c(1:20), "o", 6)
4. Функція columnmean(x, removeNA), яка розраховує середнє значення (mean) по кожному стовпцю матриці, або data frame. Логічний параметр
removeNA вказує, чи видаляти NA значення. По замовчуванню він дорівнює TRUE.
> columnmean <- function(x, removeNA = TRUE) {
     if(removeNA == 'FALSE') {
        res <- mean(x,na.rm = FALSE)
     }
     else {
        res <- mean(x,na.rm = TRUE)
     }
     res
}
> matrix1 <- matrix(c(3, NA, -1, 4, 2, NA), nrow = 2)
> matrix2 <- matrix(c(5, NA, 0, 9, 3, 4), nrow = 2)
> result <- matrix1 * matrix2
> res <- columnmean(result, 'false')
