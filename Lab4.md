>file <- read.csv(file="c:/hw1_data.csv", header=TRUE, sep=",")  
1. Які назви стовпців файлу даних?
>colnames(file)  
[1] "Ozone"   "Solar.R" "Wind"    "Temp"    "Month"   "Day"  
2. Виведіть перші 6 строк фрейму даних
> head(file, 6)  
Ozone Solar.R Wind Temp Month Day  
1    41     190  7.4   67     5   1  
2    36     118  8.0   72     5   2  
3    12     149 12.6   74     5   3  
4    18     313 11.5   62     5   4  
5    NA      NA 14.3   56     5   5  
6    28      NA 14.9   66     5   6  
3. Скільки спостерігань (строк) в дата фреймі?
> nrow(file)  
[1] 153  
4. Виведіть останні 10 строк дата фрейму.
> tail(file, 10)  
Ozone Solar.R Wind Temp Month Day  
144    13     238 12.6   64     9  21  
145    23      14  9.2   71     9  22  
146    36     139 10.3   81     9  23  
147     7      49 10.3   69     9  24  
148    14      20 16.6   63     9  25  
149    30     193  6.9   70     9  26  
150    NA     145 13.2   77     9  27  
151    14     191 14.3   75     9  28  
152    18     131  8.0   76     9  29  
153    20     223 11.5   68     9  30  
5. Як багато значень «NA» в стовпці «Ozone»?
> ozone_vector <- file[, "Ozone"]  
> length(which(!is.na(ozone_vector)))  
[1] 116  
6. Яке середнє (mean) стовпця «Ozone». Виключити «NA» значення.
> mean(ozone_vector,na.rm = TRUE)  
[1] 42.12931  
7. Виведіть частину набору даних (subset) зі значенням «Ozone» > 31 та «Temp» > 90. Яке середнє (mean) значень «Solar.R» в цьому наборі даних (subset)?
> res <- file[(file[,1]>31 & file[,4]>90),]  
> solar_r_vector <- file[, "Solar.R"]  
> mean(solar_r_vector,na.rm = TRUE)  
[1] 185.9315  
8. Яке середнє значення (mean) для «Temp» для червня («Month» дорівнює 6)?
> temp_june <-file[,(file[,4]=6)]  
> mean(temp_june,na.rm = TRUE)  
[1] 15.80392  
9. Яке максимальне значення «Ozone» для травня («Month» дорівнює 5)?
> ozone_may <-file[,(file[,1]=5)]  
> max(ozone_may)  
[1] 9  
