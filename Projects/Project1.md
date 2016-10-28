Ryan Tillis - Global Active Power Time Series - Exploratory Data Analysis - Coursera
================
<a href="http://www.ryantillis.com"> Ryan Tillis </a>
10/27/2016

Exploratory Graphing - Global Active Power
------------------------------------------

``` r
download <- download.file("https://d396qusza40orc.cloudfront.net/exdata%2Fdata%2Fhousehold_power_consumption.zip",destfile = "temp")
unzip("temp")
unlink("temp")
```

``` r
hpc <- read.table("household_power_consumption.txt", sep = ";", header = TRUE, na.strings = "?")

hpc$dt <- strptime(paste(hpc$Date, hpc$Time), "%d/%m/%Y %H:%M:%S")

hpc$Date <- as.Date(hpc$Date, "%d/%m/%Y")

hpc_sub <- subset(hpc, Date >= as.Date("2007-02-01") & Date <= as.Date("2007-02-02"))
```

``` r
hist(hpc_sub$Global_active_power, col = "red", xlab = "Global Active Power (kilowatts)", ylab = "Frequency", main = "Global Active Power", breaks = 13, ylim = c(0,1200), xlim = c(0, 6))
```

![](Project1_files/figure-markdown_github/plot1-1.png)

``` r
plot(hpc_sub$dt, hpc_sub$Global_active_power, type = "l", xlab = "", ylab = "Global Active Power (kilowatts)")
```

![](Project1_files/figure-markdown_github/plot2-1.png)

``` r
plot(hpc_sub$dt, hpc_sub$Sub_metering_1, type = "l", xlab = "", ylab = "Energy sub metering")

points(hpc_sub$dt, hpc_sub$Sub_metering_2, type = "l", col = "red")

points(hpc_sub$dt, hpc_sub$Sub_metering_3, type = "l", col = "blue")

legend("topright", lty = 1, col = c("black", "red", "blue"), legend = c("Sub_metering_1", "Sub_metering_2", "Sub_metering_3"))
```

![](Project1_files/figure-markdown_github/plot3-1.png)

``` r
par(mfrow=c(2,2))

par(mar=c(4,4,4,4))

plot(hpc_sub$dt, hpc_sub$Global_active_power, type = "l", xlab = "", ylab = "Global Active Power (kilowatts)")

plot(hpc_sub$dt, hpc_sub$Voltage, type = "l", xlab = "datetime", ylab = "Voltage")

plot(hpc_sub$dt, hpc_sub$Sub_metering_1, type = "l", xlab = "", ylab = "Energy sub metering")

points(hpc_sub$dt, hpc_sub$Sub_metering_2, type = "l", col = "red")

points(hpc_sub$dt, hpc_sub$Sub_metering_3, type = "l", col = "blue")

legend("topright", lty = 1, col = c("black", "red", "blue"), legend = c("Sub_metering_1", "Sub_metering_2", "Sub_metering_3"), bty = "n", cex = 0.8)

plot(hpc_sub$dt, hpc_sub$Global_reactive_power, type = "l", xlab = "datetime", ylab = "Global_reactive_power")
```

![](Project1_files/figure-markdown_github/plot4-1.png)

<hr>
See more at <a href="http://www.ryantillis.com"> my website. </a>

<hr>