>file <- read.csv(file="c:/hw1_data.csv", header=TRUE, sep=",")
1. Які назви стовпців файлу даних?
>colnames(file)
2. Виведіть перші 6 строк фрейму даних
>head(file, 6)
3. Скільки спостерігань (строк) в дата фреймі?
>nrow(file)
4. Виведіть останні 10 строк дата фрейму.
>tail(file, 10)
5. Як багато значень «NA» в стовпці «Ozone»?
>ozone_vector <- file[, "Ozone"]
>length(which(!is.na(ozone_vector)))
6. Яке середнє (mean) стовпця «Ozone». Виключити «NA» значення.
>mean(ozone_vector,na.rm = TRUE)
7. Виведіть частину набору даних (subset) зі значенням «Ozone» > 31 та «Temp» > 90. Яке середнє (mean) значень «Solar.R» в цьому наборі даних (subset)?
>res <- file[(file[,1]>31 & file[,4]>90),]
>solar_r_vector <- file[, "Solar.R"]
>mean(solar_r_vector,na.rm = TRUE)
8. Яке середнє значення (mean) для «Temp» для червня («Month» дорівнює 6)?
>temp_june <-file[,(file[,4]=6)]
>mean(temp_june,na.rm = TRUE)
9. Яке максимальне значення «Ozone» для травня («Month» дорівнює 5)?
>ozone_may <-file[,(file[,1]=5)]
>max(ozone_may)
