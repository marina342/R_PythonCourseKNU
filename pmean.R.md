1. Написати функцію pmean, яка обчислює середнє значення (mean) забруднення сульфатами або нітратами серед заданого переліка
моніторів. Ця функція приймає три аргументи: «directory», «pollutant», «id». Directory – папка, в якій розміщені дані, pollutant – вид забруднення, id – перелік моніторів. Аргумент id має значення за замовчуванням 1:332. Функція повинна ігнорувати NA значення.
>pmean <- function(directory, pollutant, id = 1:332) {
  path <- paste("c:/rpog_data_specdata", directory, sep = '/')
  file <- list.files(path, full.names = TRUE)
  
  data <- data.frame()
  
  for (i in id) {
    data <- rbind(data, read.csv(file[i]))
  }
  
  mean(data[[pollutant]],na.rm = TRUE)
  
}
2. Написати функцію complete, яка виводить кількість повних спостережень (the number of completely observed cases) для кожного файлу. Функція приймає два аргументи: «Directory» та «id» та повертає data frame, в якому перший стовпчик – ім’я файлу, а другий – кількість повних спостережень. 
>complete <- function(directory, id = 1:332) {
  path <- paste("c:/rpog_data_specdata", directory, sep = '/')
  file <- list.files(path, full.names = TRUE)
  
  data <- data.frame()
  ids <- c()
  nobs <- c()
  
  for (i in id) {
    data <- read.csv(file[i])
    ids <- c(ids,as.numeric(data[1,]$ID))
    n <- complete.cases(data$sulfate) & complete.cases(data$nitrate)
    nobs <- c(nobs,as.numeric(length(n[n==TRUE])))
  }
  
  result_data <- data.frame(ids,nobs)
  
  colnames(result_data) <- c("id","nobs")
  
  result_data
}

3. Написати функцію corr, яка приймає два аргументи: directory (папка, де знаходяться файли спостережень) та threshold (порогове значення, за замовчуванням дорівнює 0) та обчислює кореляцію між сульфатами та нітратами для моніторів, кількість повних спостережень для яких більше порогового значення. Функція повинна повернути вектор значень кореляцій. Якщо ні один монітор не перевищує порогового значення, функція повинна повернути numeric вектор довжиною 0. Для обчислення кореляції між сульфатами та нітратами використовуйте вбудовану функцію «cor» з параметрами за замовчуванням. 
>corr <- function(directory, threshold = 0) {
  path <- paste("c:/rpog_data_specdata", directory, sep = '/')
  file <- list.files(path, full.names = TRUE)
  
  c = numeric(length = 0)
  
  for(i in 1:length(file)){
    dat <- read.csv(file[i])
    s <- complete.cases(dat$sulfate) 
    n <- complete.cases(dat$nitrate)
    ss <- dat$sulfate 
    ns <- dat$nitrate
    b <- s & n
    ss <- ss[b]
    ns <- ns[b]
    ss <- ss[!is.na(ss)]
    ns <- ns[!is.na(ss)]
    if(length(b[b==TRUE]) > threshold){
      c = c(c,cor(ns, ss))
    }
    else{
      next
    }
  }
  
  c
  
}
